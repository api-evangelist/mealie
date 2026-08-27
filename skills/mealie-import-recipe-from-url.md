---
name: mealie-import-recipe-from-url
description: Import a recipe into Mealie from a public cooking-site URL, previewing the scrape first so nothing wrong gets saved.
api: Mealie API
generated: '2026-08-27'
method: generated
source: openapi/mealie-openapi.json
operations:
  - test_parse_recipe_url_api_recipes_test_scrape_url_post
  - parse_recipe_url_api_recipes_create_url_post
  - get_one_api_recipes__slug__get
  - patch_one_api_recipes__slug__patch
  - delete_one_api_recipes__slug__delete
---

# Import a recipe from a URL

Mealie's headline feature. It fetches the page, extracts schema.org/Recipe microdata,
and creates a recipe. Because the server does the fetching, this is one of the three
endpoints the project's own security documentation flags for SSRF and denial of
service — treat the URL you pass as untrusted input on the operator's behalf.

## Before you start

- Base URL is the operator's own instance plus `/api`. Mealie is self-hosted; there
  is no vendor host.
- `Authorization: Bearer <token>`, from a token minted at `/user/profile/api-tokens`.
- There is no idempotency key. If you fire this twice you get two recipes.

## Steps

1. **Preview the scrape without saving.** `POST /api/recipes/test-scrape-url`
   (`test_parse_recipe_url_api_recipes_test_scrape_url_post`) with `{"url": "..."}`.
   This returns the parsed recipe and persists nothing. Do this first — a bad scrape
   caught here costs nothing, while a bad scrape caught after step 2 requires a
   permanent delete.
2. **Check the preview.** If `name` is empty, the ingredient list is a single blob, or
   the instructions are missing, the source page has no usable schema.org/Recipe data.
   Stop and tell the user rather than saving a broken recipe.
3. **Import for real.** `POST /api/recipes/create/url`
   (`parse_recipe_url_api_recipes_create_url_post`) with
   `{"url": "...", "includeTags": true, "includeCategories": true}`. The response is
   the new recipe's **slug**, not a full object.
4. **Read it back.** `GET /api/recipes/{slug}` (`get_one_api_recipes__slug__get`) to
   confirm and to show the user what landed.
5. **Correct anything wrong.** `PATCH /api/recipes/{slug}`
   (`patch_one_api_recipes__slug__patch`) with only the fields you are changing.

## If you need to undo

`DELETE /api/recipes/{slug}` (`delete_one_api_recipes__slug__delete`). This is
**permanent** — there is no trash and no restore endpoint. Confirm with the user
before deleting anything you did not create in this session.

## Errors

- `422` — the only error the contract declares. Read `detail[].loc` for the field and
  `detail[].msg` for the reason. Do not retry unchanged.
- `409` (undeclared) — a recipe with that name/slug already exists in the group. Fetch
  the existing one by slug instead of retrying the create.
- `500` (undeclared) — on this endpoint usually means the remote site could not be
  fetched or parsed, not that Mealie is broken. Report the source URL as the problem.

## Do not

- Do not retry a failed `create/url` blindly. Check by slug first.
- Do not pass internal or private-network URLs. The project documents this endpoint as
  an SSRF vector.
