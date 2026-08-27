---
name: mealie-plan-week-and-build-shopping-list
description: Fill a week of Mealie meal plan entries and turn them into a shopping list, using the one reversal path the API actually provides.
api: Mealie API
generated: '2026-08-27'
method: generated
source: openapi/mealie-openapi.json
operations:
  - get_all_api_recipes_get
  - suggest_recipes_api_recipes_suggestions_get
  - get_all_api_households_mealplans_get
  - create_one_api_households_mealplans_post
  - create_random_meal_api_households_mealplans_random_post
  - delete_one_api_households_mealplans__item_id__delete
  - get_all_api_households_shopping_lists_get
  - create_one_api_households_shopping_lists_post
  - add_recipe_ingredients_to_list_api_households_shopping_lists__item_id__recipe_post
  - remove_recipe_ingredients_from_list_api_households_shopping_lists__item_id__recipe__recipe_id__delete_post
  - get_one_api_households_shopping_lists__item_id__get
---

# Plan a week and build the shopping list

The flow Mealie exists for. It spans two resources — meal plans and shopping lists —
and it is the one place in this API where a write has a clean, documented reverse.

## Before you start

Meal plans and shopping lists are **household**-scoped, not group-scoped. The token
you hold determines which household you are writing to; you cannot address another
household's plan.

## Steps

1. **Find candidate recipes.** `GET /api/recipes` (`get_all_api_recipes_get`) with a
   `queryFilter`. Useful filters:
   - not cooked recently: `lastMade <= "$NOW-30d"`
   - by tag: `tags.name CONTAINS ALL ["Easy"]`
   - by category: `recipeCategory.name = "Dinner"`

   Or let Mealie choose: `GET /api/recipes/suggestions`
   (`suggest_recipes_api_recipes_suggestions_get`).
2. **Check what is already planned.** `GET /api/households/mealplans`
   (`get_all_api_households_mealplans_get`) with `start_date` and `end_date` so you do
   not double-book a day.
3. **Add each entry.** `POST /api/households/mealplans`
   (`create_one_api_households_mealplans_post`) with `{"date": "YYYY-MM-DD",
   "entryType": "dinner", "recipeId": "<uuid>"}`. Use `title` and `text` instead of
   `recipeId` for a note-only entry.

   To let the household's plan rules pick: `POST /api/households/mealplans/random`
   (`create_random_meal_api_households_mealplans_random_post`).
4. **Get or create the shopping list.** `GET /api/households/shopping/lists`
   (`get_all_api_households_shopping_lists_get`); if none fits, `POST` the same path
   (`create_one_api_households_shopping_lists_post`) with `{"name": "..."}`.
5. **Add each planned recipe's ingredients.**
   `POST /api/households/shopping/lists/{item_id}/recipe`
   (`add_recipe_ingredients_to_list_api_households_shopping_lists__item_id__recipe_post`).
   Mealie consolidates matching foods across recipes for you.

   Do **not** use `POST .../recipe/{recipe_id}` — that operation is marked
   `deprecated: true` in the contract.
6. **Read the list back.** `GET /api/households/shopping/lists/{item_id}`
   (`get_one_api_households_shopping_lists__item_id__get`) and show the user
   `listItems` grouped by `labelId`.

## Reversal

This is the good news in this API:

- Added the wrong recipe's ingredients?
  `POST /api/households/shopping/lists/{item_id}/recipe/{recipe_id}/delete`
  (`remove_recipe_ingredients_from_list_...`) removes exactly that recipe's
  contribution and leaves everything else. No stated time window — it works whenever.
- Wrong meal plan entry? `DELETE /api/households/mealplans/{item_id}`
  (`delete_one_api_households_mealplans__item_id__delete`).

Note the asymmetry: removing a recipe from the list does not remove it from the meal
plan, and deleting a plan entry does not remove its ingredients from the list. Reverse
both, in that order, or the two will drift apart.

## Pagination

Every list endpoint here pages the same way: `page` and `perPage` in, `page`,
`per_page`, `total`, `total_pages`, `items`, `next`, `previous` out. `next` is a
**relative** path with no base URL — prepend the instance host before following it.
`perPage=-1` returns everything in one call.
