---
name: mealie-sync-shopping-list-to-external-app
description: Keep a Mealie shopping list in sync with an external list manager using Mealie's documented `extras` key/value escape hatch and its scheduled webhook.
api: Mealie API
generated: '2026-08-27'
method: generated
source: https://docs.mealie.io/documentation/getting-started/api-usage/
operations:
  - get_all_api_households_shopping_lists_get
  - get_one_api_households_shopping_lists__item_id__get
  - update_one_api_households_shopping_lists__item_id__put
  - get_all_api_households_shopping_items_get
  - update_one_api_households_shopping_items__item_id__put
  - get_all_api_foods_get
  - update_one_api_foods__item_id__put
  - create_one_api_households_webhooks_post
  - test_one_api_households_webhooks__item_id__test_post
---

# Sync a Mealie shopping list with an external app

Mealie has no integration marketplace and no per-object custom-field system. What it
has instead is `extras` — a free-form JSON key/value map on recipes, shopping lists,
shopping list items and foods — and the docs present it as the supported way to build
exactly this kind of two-way sync.

## The pattern

Store the external system's identifier on the Mealie object. Then any time you see
that Mealie object you know which remote record it maps to, without keeping a mapping
table of your own.

The documented worked example uses Trello:

- On the shopping list: `{"trello_list_id": "5abbe4b7ddc1b351ef961414"}`
- On each item: `{"trello_card_id": "bab414bde415cd715efb9361"}`
- On a food you never want to sync: `{"trello_exclude_food": "true"}`

## Steps

1. **Find the list.** `GET /api/households/shopping/lists`
   (`get_all_api_households_shopping_lists_get`), then
   `GET /api/households/shopping/lists/{item_id}`
   (`get_one_api_households_shopping_lists__item_id__get`) for `listItems`.
2. **Stamp the list.** `PUT /api/households/shopping/lists/{item_id}`
   (`update_one_api_households_shopping_lists__item_id__put`) with `extras` set to
   your identifier map. `PUT` replaces the object — read it first and send the whole
   thing back with `extras` added, or you will blank fields you did not mean to touch.
3. **Stamp each item.** `PUT /api/households/shopping/items/{item_id}`
   (`update_one_api_households_shopping_items__item_id__put`). Same read-modify-write
   discipline.
4. **Mark foods to exclude.** `GET /api/foods` (`get_all_api_foods_get`) then
   `PUT /api/foods/{item_id}` (`update_one_api_foods__item_id__put`) with your
   exclusion flag in `extras`.
5. **Poll or be pushed.** Either poll `GET /api/households/shopping/items`
   (`get_all_api_households_shopping_items_get`) with
   `queryFilter=updatedAt >= "$NOW-1H"`, or register a webhook:
   `POST /api/households/webhooks` (`create_one_api_households_webhooks_post`) with
   `{"name": "...", "url": "https://...", "webhookType": "mealplan",
   "scheduledTime": "07:00:00", "enabled": true}`, then fire it once with
   `POST /api/households/webhooks/{item_id}/test`
   (`test_one_api_households_webhooks__item_id__test_post`) to verify the receiver.

## Know the limits before you design around this

- **The webhook is a scheduled daily meal-plan digest, not a change stream.**
  `webhookType` is an enum with one member: `mealplan`. There is no shopping-list
  webhook. Polling is the only way to see item changes promptly.
- **Webhooks are unsigned.** No HMAC header, no shared secret. Your receiver cannot
  verify a POST actually came from Mealie — put it behind a secret path or your own
  auth.
- **`extras` values are strings.** The docs' own exclusion example is `"true"`, not
  `true`. Do not expect typed round-tripping.
- **No idempotency.** Every write here is a `PUT` against a known id, so it is
  naturally idempotent — but never turn one of these into a `POST` create-and-retry.
