# GxP Compliance Support for saas-ui-tests

## Purpose
This document describes the initial implementation to support GxP-aligned UI testing with Playwright.

## What is implemented
- Playwright now generates both an HTML report and a JSON report for each test execution.
- Test artifacts are written to a controlled directory: `test-results/`.
- A dedicated npm alias was added for reproducible GxP test runs: `npm run test:gxp`.

## Artifact locations
- HTML report directory: `playwright-report/`
- JSON results file: `test-results/playwright-report.json`
- Test artifacts (traces, screenshots, videos, output files) are stored under `test-results/`

## Recommended execution commands
- `npm run test:gxp` — execute tests and generate compliance artifacts.
- `npm test` — execute tests and open the HTML report.
- `npm run test:report` — open the last generated HTML report.

## Key compliance controls
1. Environment qualification
   - Use `npm ci` to install dependencies from `package-lock.json`.
   - Document the OS, Node.js, browser versions, and Playwright version.

2. Traceability
   - Map each test file and case back to a requirement or controlled specification.
   - Store mapping documentation in source control.

3. Change control
   - Use version control to record script and configuration changes.
   - Require review for updates to tests, reporters, or the `package.json` scripts.

4. Record retention
   - Archive `playwright-report/` and `test-results/playwright-report.json` for each run.
   - Treat these artifacts as the execution record for the release.

5. Review and approval
   - Maintain evidence of test execution, review, and sign-off outside the repo if required.

## Next steps
- Add a traceability matrix for requirements versus test cases.
- Add SOPs for executing `npm run test:gxp` in the controlled environment.
- Add a compliance checklist for installation qualification and operational qualification.
