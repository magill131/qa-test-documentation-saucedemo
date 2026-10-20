# Login and logout test cases

Application: https://www.saucedemo.com
Status values: Not run, Pass, Fail. Fill in Actual and Status when running.

| ID | Priority | Title | Steps | Expected result | Actual | Status |
|---|---|---|---|---|---|---|
| TC-LOGIN-01 | High | Valid login | 1. Open the site<br>2. Enter `standard_user` and the password shown on the page<br>3. Click Login | The inventory page opens with the title "Products" and 6 items | Inventory page opened, title Products, 6 items | Pass |
| TC-LOGIN-02 | High | Locked-out user cannot log in | 1. Enter `locked_out_user` and the password<br>2. Click Login | The login page stays open. Error: "Epic sadface: Sorry, this user has been locked out." | Error: Epic sadface: Sorry, this user has been locked out. Stayed on login page | Pass |
| TC-LOGIN-03 | High | Wrong password | 1. Enter `standard_user` and the password `wrong`<br>2. Click Login | Error: "Epic sadface: Username and password do not match any user in this service" | Error: Epic sadface: Username and password do not match any user in this service | Pass |
| TC-LOGIN-04 | Medium | Unknown username | 1. Enter `nobody` and the real password<br>2. Click Login | Same "do not match any user" error as TC-LOGIN-03 | Same do-not-match error | Pass |
| TC-LOGIN-05 | High | Both fields empty | 1. Leave both fields empty<br>2. Click Login | Error: "Epic sadface: Username is required" | Error: Epic sadface: Username is required | Pass |
| TC-LOGIN-06 | Medium | Password empty | 1. Enter `standard_user` only<br>2. Click Login | Error: "Epic sadface: Password is required" | Error: Epic sadface: Password is required | Pass |
| TC-LOGIN-07 | Medium | Username empty | 1. Enter the password only<br>2. Click Login | Error: "Epic sadface: Username is required" | Error: Epic sadface: Username is required | Pass |
| TC-LOGIN-08 | Medium | Username is case sensitive | 1. Enter `STANDARD_USER` and the real password<br>2. Click Login | The "do not match any user" error is shown | Do-not-match error shown | Pass |
| TC-LOGIN-09 | Medium | Close the error message | 1. Cause any login error<br>2. Click the X on the error message | The error message disappears | Error message disappeared | Pass |
| TC-LOGIN-10 | High | Logout | 1. Log in as `standard_user`<br>2. Open the menu and click Logout | The login page opens with empty username and password fields | Login page opened, both fields empty | Pass |
| TC-LOGIN-11 | High | Inventory page needs a login | 1. Without logging in, open https://www.saucedemo.com/inventory.html | The login page opens with an error saying you can only access `/inventory.html` when you are logged in | Redirected to login. Error: Epic sadface: You can only access '/inventory.html' when you are logged in. | Pass |
