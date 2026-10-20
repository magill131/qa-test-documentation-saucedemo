# Test plan: SauceDemo store

## 1. Purpose

Check that a shopper can log in, add items to the cart and complete a purchase on https://www.saucedemo.com, and that errors are shown when they should be.

## 2. Scope

In scope:
- Login and logout, including the `locked_out_user`
- Adding and removing items on the inventory page, the item page and the cart
- Checkout: customer information, order overview, order confirmation
- The four special demo users (`problem_user`, `performance_glitch_user`, `error_user`, `visual_user`): the same actions as `standard_user`, with `standard_user` as the expected result

Out of scope:
- Product sorting
- Social media links in the footer
- Performance and load testing
- Security testing
- Mobile and tablet layouts
- Page layout comparison for `visual_user`

## 3. Test approach

- Manual, scripted testing. Every case in [test-cases/](test-cases/) is run in the browser and the actual result is recorded.
- Each case has a priority. High cases cover the main purchase path and login errors. Medium cases cover validation and navigation.
- A failed case gets a bug report in [bug-reports/](bug-reports/) using the template there.
- The main purchase path is also automated in the Selenium project linked in the README.

## 4. Test environment

| Item | Value |
|---|---|
| Application | https://www.saucedemo.com |
| Browser | Chromium 152 (built-in browser of the Claude desktop app); version recorded in the test summary |
| Operating system | Windows 11 |
| Test users | `standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user`, `error_user`, `visual_user` (credentials are shown on the login page) |
| Test data | Items: Sauce Labs Backpack ($29.99), Sauce Labs Bike Light ($9.99) |

## 5. Entry criteria

- The site loads and the login page is shown.
- The test cases are written and reviewed.
- A current Chromium-based browser is available.

## 6. Exit criteria

- Every case has a status other than Not run.
- Every failed case has a bug report.
- The test summary is filled in.

## 7. Risks

| Risk | Effect | Plan |
|---|---|---|
| The demo site changes without notice | Expected results go out of date | Record the date of the run in the summary and re-check failed cases |
| The site is a public demo and may be slow or down | Cases cannot be run | Retry later and note the outage in the summary |
| Expected results were drafted before the run | A case may be wrong, not the site | Check each failure against the site before filing a bug |
| One browser only | Browser-specific bugs are missed | Listed as a known gap in the summary |

## 8. Deliverables

- This test plan
- Test cases for login, cart and checkout
- Bug reports for every failed case
- A test summary

## 9. Schedule

One working session to run all cases, one to write up the bug reports and summary.
