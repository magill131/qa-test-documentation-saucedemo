# Test summary

| Item | Value |
|---|---|
| Date of run | 2026-10-19 |
| Browser | Chromium 152 (the Claude desktop app's built-in browser), Windows |
| Test users | `standard_user`, `locked_out_user`, `problem_user`, `performance_glitch_user`, `error_user`, `visual_user` |
| Cases in total | 42 |
| Pass | 31 |
| Fail | 11 |
| Not run | 0 |

| Case file | Cases | Pass | Fail |
|---|---|---|---|
| [login.md](test-cases/login.md) | 11 | 11 | 0 |
| [cart.md](test-cases/cart.md) | 8 | 8 | 0 |
| [checkout.md](test-cases/checkout.md) | 11 | 11 | 0 |
| [special-users.md](test-cases/special-users.md) | 12 | 1 | 11 |

## How the run was done

Each case was run in the browser against https://www.saucedemo.com. The steps were driven by a script that filled in fields and clicked buttons, and the page text was read back to get the actual results. It was not run by hand in Chrome. Each special-user case started from a fresh browser session (storage cleared, page reloaded).

Two cases in `cart.md` and `checkout.md` were run in a slightly different order than written:
- TC-CART-05 was first run with two items in the cart (one removed, number dropped from 2 to 1), then repeated with one item (cart empty, no number).
- TC-CHECKOUT-08 was finished with two items in the cart instead of one. The result was the same.

## Findings

`standard_user` and `locked_out_user`: all 30 cases matched the expected results.

The four special users are demo accounts that the site lists on its login page. The 11 failures below show what each one does differently from `standard_user`.

| Bug | Title | Severity | Test case |
|---|---|---|---|
| [BUG-001](bug-reports/BUG-001.md) | problem_user: every product shows the same placeholder picture | Medium | TC-SPECIAL-01 |
| [BUG-002](bug-reports/BUG-002.md) | problem_user: Add to cart does nothing for three products | High | TC-SPECIAL-02 |
| [BUG-003](bug-reports/BUG-003.md) | problem_user: Remove does nothing on the Products page | High | TC-SPECIAL-03 |
| [BUG-004](bug-reports/BUG-004.md) | problem_user: text typed in Last Name appears in First Name at checkout | High | TC-SPECIAL-04 |
| [BUG-005](bug-reports/BUG-005.md) | performance_glitch_user: login takes about 5 seconds | Medium | TC-SPECIAL-05 |
| [BUG-006](bug-reports/BUG-006.md) | error_user: Add to cart does nothing for three products | High | TC-SPECIAL-07 |
| [BUG-007](bug-reports/BUG-007.md) | error_user: Remove does nothing on the Products page | High | TC-SPECIAL-08 |
| [BUG-008](bug-reports/BUG-008.md) | error_user: Last Name is not kept at checkout | High | TC-SPECIAL-09 |
| [BUG-009](bug-reports/BUG-009.md) | error_user: Finish does nothing, the order cannot be completed | Critical | TC-SPECIAL-10 |
| [BUG-010](bug-reports/BUG-010.md) | visual_user: prices differ from standard_user and change on every login | High | TC-SPECIAL-11 |
| [BUG-011](bug-reports/BUG-011.md) | visual_user: Sauce Labs Backpack shows the placeholder picture | Low | TC-SPECIAL-12 |

## Cases changed during the run

None. No expected result needed correcting.

## Known gaps

- One browser only, and it is not Chrome
- BUG-004 and BUG-008 were seen with scripted input. Typing by hand should be checked once.
- BUG-005 was timed in a pane that may run as a background page
- The page layout for `visual_user` was not compared (window size was not reported reliably)
- No screenshots were taken, so the bug reports use page data as evidence
- Product sorting, footer links, mobile layouts, performance and security not covered
