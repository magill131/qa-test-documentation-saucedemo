# QA test documentation: SauceDemo store

A test plan, manual test cases and bug reports for the public demo store at https://www.saucedemo.com. The same app is automated with Selenium in [saucedemo-selenium-pytest-framework](https://github.com/magill131/saucedemo-selenium-pytest-framework).

Written in VS Code with Claude Code. Every result in this repo comes from a real run against the live site on 2026-10-19. See [test-summary.md](test-summary.md) for how it was run.

## What is in here

| File | What it is |
|---|---|
| [test-plan.md](test-plan.md) | Scope, approach, environment, entry and exit criteria, risks |
| [test-cases/login.md](test-cases/login.md) | 11 login and logout cases |
| [test-cases/cart.md](test-cases/cart.md) | 8 cart cases |
| [test-cases/checkout.md](test-cases/checkout.md) | 11 checkout cases |
| [test-cases/special-users.md](test-cases/special-users.md) | 12 cases for the four special demo users |
| [bug-reports/](bug-reports/) | 11 bug reports (BUG-001 to BUG-011), using [TEMPLATE.md](bug-reports/TEMPLATE.md) |
| [test-summary.md](test-summary.md) | 42 cases: 31 pass, 11 fail, and the bugs found |

## How to read it

1. Read the test plan to see what is and is not covered.
2. Open a case file. Each row has an ID, steps, the expected result, the actual result and a status.
3. Failed cases link to a bug report in `bug-reports/`.

## How the cases were written

The expected results were drafted from knowledge of how the site behaves, then checked by running each case. Where a case was wrong and the site was right, the case would be changed and noted in the test summary. None needed changing.

## About the bugs

`standard_user` and `locked_out_user` passed all 30 cases. The 11 bugs come from the four special demo users that the site lists on its login page. Those accounts are built to misbehave, so the reports describe how each one differs from `standard_user`.
