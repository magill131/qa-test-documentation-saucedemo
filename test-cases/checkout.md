# Checkout test cases

Application: https://www.saucedemo.com
Precondition for all cases: logged in as `standard_user`. Cases that need items use Sauce Labs Backpack ($29.99) and Sauce Labs Bike Light ($9.99).
Status values: Not run, Pass, Fail. Fill in Actual and Status when running.

| ID | Priority | Title | Steps | Expected result | Actual | Status |
|---|---|---|---|---|---|---|
| TC-CHECKOUT-01 | High | Start checkout | 1. Add Sauce Labs Backpack<br>2. Open the cart and click Checkout | The "Checkout: Your Information" page opens with First Name, Last Name and Zip/Postal Code fields | Checkout: Your Information page opened with the three fields | Pass |
| TC-CHECKOUT-02 | High | First name is required | 1. Start checkout<br>2. Leave First Name empty, fill the other fields<br>3. Click Continue | Error: "Error: First Name is required" | Error: First Name is required | Pass |
| TC-CHECKOUT-03 | High | Last name is required | 1. Start checkout<br>2. Leave Last Name empty, fill the other fields<br>3. Click Continue | Error: "Error: Last Name is required" | Error: Last Name is required | Pass |
| TC-CHECKOUT-04 | High | Postal code is required | 1. Start checkout<br>2. Leave Zip/Postal Code empty, fill the other fields<br>3. Click Continue | Error: "Error: Postal Code is required" | Error: Postal Code is required | Pass |
| TC-CHECKOUT-05 | High | Valid information goes to the overview | 1. Add Sauce Labs Backpack and open checkout<br>2. Enter a first name, last name and postal code<br>3. Click Continue | The "Checkout: Overview" page opens and lists Sauce Labs Backpack | Checkout: Overview opened and listed Sauce Labs Backpack | Pass |
| TC-CHECKOUT-06 | High | Item total is the sum of the items | 1. Add Sauce Labs Backpack and Sauce Labs Bike Light<br>2. Go to the overview | Item total: $39.98 | Item total: $39.98 | Pass |
| TC-CHECKOUT-07 | Medium | Tax and total | 1. Use the same two items as TC-CHECKOUT-06<br>2. Read the tax and total | Tax: $3.20 (8% of $39.98, rounded). Total: $43.18. | Tax: $3.20, Total: $43.18 | Pass |
| TC-CHECKOUT-08 | High | Finish the order | 1. Go to the overview with one item<br>2. Click Finish | The confirmation page shows "Thank you for your order!" | Confirmation page showed Thank you for your order! | Pass |
| TC-CHECKOUT-09 | Medium | Back home after an order | 1. Finish an order<br>2. Click Back Home | The inventory page opens and the cart icon shows no number | Inventory page opened, no cart number | Pass |
| TC-CHECKOUT-10 | Medium | Cancel on the information page | 1. Start checkout<br>2. Click Cancel | The cart page opens and the item is still in the cart | Cart page opened, item still in cart | Pass |
| TC-CHECKOUT-11 | Medium | Cancel on the overview page | 1. Go to the overview<br>2. Click Cancel | The inventory page opens | Inventory page opened | Pass |
