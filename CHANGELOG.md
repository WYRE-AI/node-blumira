## [1.0.1](https://github.com/wyre-technology/node-blumira/compare/v1.0.0...v1.0.1) (2026-05-18)


### Bug Fixes

* include compiled dist/ in published package ([#2](https://github.com/wyre-technology/node-blumira/issues/2)) ([8344613](https://github.com/wyre-technology/node-blumira/commit/834461325d199862a9c752d15091c2fde1613925))

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

* initial Blumira SIEM client library ([336e96d](https://github.com/wyre-technology/node-blumira/commit/336e96dbf49e1275eef4056570587c78f77e0316))
