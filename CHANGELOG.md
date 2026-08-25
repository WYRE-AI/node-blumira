## [1.0.3](https://github.com/WYRE-AI/node-blumira/compare/v1.0.2...v1.0.3) (2026-08-25)


### Bug Fixes

* migrate to WYRE-AI org (npm scope, ghcr namespace, registry) ([#37](https://github.com/WYRE-AI/node-blumira/issues/37)) ([498157f](https://github.com/WYRE-AI/node-blumira/commit/498157f924f87c25ec56d19ff969e78965cff4d8))

## [1.0.2](https://github.com/WYRE-AI/node-blumira/compare/v1.0.1...v1.0.2) (2026-07-23)


### Bug Fixes

* **ci:** drop Node 18.x from the test matrix (EOL, vitest 4 requires 20.12+) ([#26](https://github.com/WYRE-AI/node-blumira/issues/26)) ([cded5b1](https://github.com/WYRE-AI/node-blumira/commit/cded5b1b1b574492aef65f84abb4e3eb1f0a6bcb))
* **deps:** re-pin typescript to ^6.0.3 + ignoreDeprecations for TS7 DTS build breakage ([#25](https://github.com/WYRE-AI/node-blumira/issues/25)) ([332d808](https://github.com/WYRE-AI/node-blumira/commit/332d808768bcc2caa476a95345cceb098fde6bd4))

## [1.0.1](https://github.com/WYRE-AI/node-blumira/compare/v1.0.0...v1.0.1) (2026-05-18)


### Bug Fixes

* include compiled dist/ in published package ([#2](https://github.com/WYRE-AI/node-blumira/issues/2)) ([8344613](https://github.com/WYRE-AI/node-blumira/commit/834461325d199862a9c752d15091c2fde1613925))

## [Unreleased]

### Fixed

- Published package now includes the compiled `dist/` output. `package.json`
  had no `files` field, so npm honored `.gitignore` (which ignores `dist/`)
  and published only `src/`. Consumers running `npm ci --ignore-scripts`
  (e.g. Docker builds) never ran the `prepare` build step, so the package's
  `main`/`exports` pointed at a non-existent `dist/index.js`, causing
  `ERR_MODULE_NOT_FOUND` at runtime. Added `"files": ["dist"]`.

# 1.0.0 (2026-02-26)


### Features

* initial Blumira SIEM client library ([336e96d](https://github.com/WYRE-AI/node-blumira/commit/336e96dbf49e1275eef4056570587c78f77e0316))
