# Node.js development runtime

Use Node.js **22.23.4** (`nvm use`). It includes the October 2026 security fixes, including CVE-2026-111497.

Reference: https://nodejs.org/en/blog/vulnerability/october-2026-security-releases

The npm development-engine configuration uses the current `runtime` and `packageManager` schema. The headless test task uses Chrome Headless instead of the unsupported PhantomJS binary. Install Google Chrome locally, or set `CHROME_BIN` to a Chrome/Chromium executable.

Validated under Node 22.23.4: normal `npm ci` (including the Bower prepare hook), `npm run compile`, `npm test` (497 unit tests and 2 midway tests), and `npm run test-headless` (the same 499 tests). These tests cover the default AngularJS scope; the historical alternate AngularJS test scopes and release/upload operations were not executed.

The Travis job retains its existing Firefox setup; local/headless runs use Chrome. Publication and release scripts are unchanged.
