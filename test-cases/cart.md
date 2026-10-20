# Cart test cases

Application: https://www.saucedemo.com
Precondition for all cases: logged in as `standard_user` with an empty cart.
Status values: Not run, Pass, Fail. Fill in Actual and Status when running.

| ID | Priority | Title | Steps | Expected result | Actual | Status |
|---|---|---|---|---|---|---|
| TC-CART-01 | High | Add one item | 1. On the inventory page click Add to cart on Sauce Labs Backpack | The button changes to Remove. The cart icon shows 1. | Button changed to Remove, cart showed 1 | Pass |
| TC-CART-02 | High | Add several items | 1. Add Sauce Labs Backpack<br>2. Add Sauce Labs Bike Light | The cart icon shows 2 | Cart showed 2 | Pass |
| TC-CART-03 | Medium | Remove an item on the inventory page | 1. Add Sauce Labs Backpack<br>2. Click Remove on the same item | The button changes back to Add to cart. The cart icon shows no number. | Button back to Add to cart, no cart number | Pass |
| TC-CART-04 | High | Cart lists the added items | 1. Add Sauce Labs Backpack<br>2. Click the cart icon | The cart page shows Sauce Labs Backpack with quantity 1, its description and price $29.99 | Cart page listed Backpack (qty 1, description, $29.99) and Bike Light (qty 1, $9.99) | Pass |
| TC-CART-05 | High | Remove an item in the cart | 1. Add Sauce Labs Backpack<br>2. Open the cart<br>3. Click Remove | The item disappears from the cart. The cart icon shows no number. | Item removed, cart empty, no cart number | Pass |
| TC-CART-06 | Medium | Continue shopping | 1. Open the cart<br>2. Click Continue Shopping | The inventory page opens | Inventory page opened | Pass |
| TC-CART-07 | Medium | Add from the item page | 1. Click the name Sauce Labs Backpack<br>2. On the item page click Add to cart | The button changes to Remove. The cart icon shows 1. | Item page opened, button changed to Remove, cart showed 1 | Pass |
| TC-CART-08 | Medium | Empty cart | 1. Click the cart icon without adding anything | The cart page shows no items and no cart number | Cart page showed no items and no cart number | Pass |
