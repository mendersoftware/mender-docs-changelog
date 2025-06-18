---
title: Hosted Mender
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## v4.1.0-saas.9 - 2025-06-18


### Bug Fixes


- *(gui)* Fixed another situation that could cause the organization token to overflow
 ([555cb1e](https://github.com///commit/555cb1e7ec1571bd5ed02104c1185138b6e25d4a)) 







## v4.1.0-saas.8 - 2025-06-18


### Bug Fixes


- *(gui)* Fixed a problem that could apply RBAC restrictions on non-RBAC plans
([MEN-8498](https://northerntech.atlassian.net/browse/MEN-8498)) ([c870092](https://github.com///commit/c87009221163505732cb677e44a9c159233c3d68)) 

- *(gui)* Fixed an issue that could cause the organization token to overflow for older tenants
 ([e04f0e9](https://github.com///commit/e04f0e99df3c4edcd932034bc3d0aad31bd8467f)) 







## v4.1.0-saas.7 - 2025-06-18


### Bug Fixes


- *(generate-delta-worker)* Stuck when generating to local path
([MEN-8484](https://northerntech.atlassian.net/browse/MEN-8484)) ([a7e27ca](https://github.com///commit/a7e27cad64ebb403766ca8bdfa05389c17affd87)) 


  Only used in tests. The generate-delta command fails when the output is
  a local path.

- *(gui)* Restored error handling on user edits
([ME-522](https://northerntech.atlassian.net/browse/ME-522)) ([882a5c7](https://github.com///commit/882a5c7f6bc03325a4fd5875d2b92d22fe6d7e29)) 


  - regression from 5888d3e3ee47b764b256e89da9419f903936e4f3 in the prior repo

- *(gui)* Fixed an issue that would prevent showing all webhook activity
 ([70d9eda](https://github.com///commit/70d9eda75dd1cf955daa892bcc86a9760743be5f)) 

- *(gui)* Fixed wording and position of onboarding tooltip
([MEN-8407](https://northerntech.atlassian.net/browse/MEN-8407)) ([69c1a6d](https://github.com///commit/69c1a6ddd185ed1277fdbb66b194d6f09c4b06a0)) 

- *(gui)* Aligned supported OS versions in download section with tool support
([ME-499](https://northerntech.atlassian.net/browse/ME-499)) ([c256688](https://github.com///commit/c256688950a0f81fdb63326f6fb524e035969ab3)) 

- *(gui)* Fixed billing profile not being fetched
 ([9042c6b](https://github.com///commit/9042c6be7ccc445a5affca63b65559bb562e6597)) 

- Ensure email is always encoded in lowercase when stored
([MEN-8328](https://northerntech.atlassian.net/browse/MEN-8328)) ([d80c818](https://github.com///commit/d80c818eed43765387cfe81445e187f9c1833156)) 


  Added a bson codec for model.Email that will ensure that emails are
  always encoded in lowercase in the database to ensure case insensitive
  queries.




### Documentation


- *(auditlogs)* Replace swagger 2.0 specs with Openapi 3.0.1
 ([d624916](https://github.com///commit/d6249166af2c6b2aa6dcaf29780bc6a47519ba8d)) 

- *(auditlogs)* Consolidate API specifications into a single OAS file
 ([e47649f](https://github.com///commit/e47649f1d9309dd1fbca5bce72b5757548e8b103)) 

- *(auditlogs)* Move OAS to new location and provide symlink
 ([7e55fc3](https://github.com///commit/7e55fc3b196fb340080cacc202f1a730aa560632)) 

- *(auditlogs)* Add content type to export endpoint
 ([3f681c7](https://github.com///commit/3f681c73959cfce5f8aed81adc10d419ac1eabab)) 

- *(deviceauth)* Rename operation id for removing device authentication
 ([3f99b91](https://github.com///commit/3f99b91c57c52214e01a70caa78ed47912956c9f)) 


  "Reject" is in the UI associated with updating the authentication status
  where as "dismiss" is used for removing authentication.

- *(tenantadm)* Consolidate OAS into a single definition
 ([bd79510](https://github.com///commit/bd7951099cfbd7f59ae6a6e9d41a74d560a4e910)) 

- *(tenantadm)* Fixup Tenant examples in OAS specs
 ([cf8ac9b](https://github.com///commit/cf8ac9b3f21f94fc77f2a58d0391c0b0094c4829)) 

- *(tenantadm)* Fix incorrect type for integer in OAS
 ([2b4c082](https://github.com///commit/2b4c0820b88f31dae88d54cd4a1254f6e43bba9a)) 

- *(tenantadm)* Update OAS info section
 ([1e60f1e](https://github.com///commit/1e60f1ecef093efb67e9dec1149fa57afda42e96)) 

- *(tenantadm)* Fix invalid objects in `allOf` overrides for Address
 ([eb48e23](https://github.com///commit/eb48e2348e1ab3abb73ca3de285a622a772cba5c)) 

- *(tenantadm)* Fix inconsistent schema definitions
 ([fd48cc5](https://github.com///commit/fd48cc5e89925e26935ec3c6f594e1d80957e5be)) 





### Features


- *(gui)* Made device tags functionality available in all device auth states
([ME-528](https://northerntech.atlassian.net/browse/ME-528)) ([7b1f3c6](https://github.com///commit/7b1f3c61e4b4151cb81a8aab5c4a22c581e01cb3)) 

- *(gui)* Let tenant token not be visible by default
([MEN-8397](https://northerntech.atlassian.net/browse/MEN-8397)) ([b70e0b4](https://github.com///commit/b70e0b44cf627d6b0621da92f0d0a154588aafb1)) 

- *(useradm)* Change user roles handling for plans different than Enterprise
([MEN-8168](https://northerntech.atlassian.net/browse/MEN-8168)) ([1ee0b84](https://github.com///commit/1ee0b84a6be11bf2dd2ce28785b64031f1c2f52d)) 

- Implemented content type checker middleware for gin framework
([MEN-8327](https://northerntech.atlassian.net/browse/MEN-8327)) ([9016554](https://github.com///commit/9016554b702297ad00f1a748d0824fdf19d05678)) 




### Performance


- Put routing path and parameters in separate accesslog fields
 ([51832b6](https://github.com///commit/51832b685d70d6dbe2f8cdf8442b96d6eec843fb)) 


  By separating the two, it is much less complex to index paths in the log
  parser.




### Refactor


- *(deviceauth)* Move api urls and router maker to `routing.go`
([MEN-8235](https://northerntech.atlassian.net/browse/MEN-8235)) ([7ecd14e](https://github.com///commit/7ecd14e37aca2d0a8c61b6382e5593a9038b8921)) 

- *(deviceauth)* Migrate enterprise deviceauth service to gin
([MEN-8235](https://northerntech.atlassian.net/browse/MEN-8235)) ([f0b43c4](https://github.com///commit/f0b43c47b1c6cab50ff7bfea401f50bc16719d94)) 

- *(gui)* Isolated organization information in settings to align with design
([MEN-8411](https://northerntech.atlassian.net/browse/MEN-8411)) ([2d0eb79](https://github.com///commit/2d0eb79e1c51eb31c7a9c1df83754f0aee663a70)) 


  + made settings items customizable from outside

- *(gui)* Moved billing data to separate settings section & aligned with design
([MEN-8411](https://northerntech.atlassian.net/browse/MEN-8411)) ([bf7578b](https://github.com///commit/bf7578b3966c82d293127d4d9a0cf6d98d90008e)) 

- *(gui)* Centralized support contact component
 ([0dd79cb](https://github.com///commit/0dd79cb8d2cdd8bc96d4f5c47ef0f7d3f58175a4)) 

- *(inventory)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([f6899d4](https://github.com///commit/f6899d44129b892708bbe0bfcc485fbf8f705166)) 

- *(tenantadm)* Move `middleware.go` to the http package
 ([3f5f338](https://github.com///commit/3f5f338d1415a4f11c346d6c157753545c3fbf74)) 

- *(tenantadm)* Move api handler and router to their corresponding file
 ([24e22ae](https://github.com///commit/24e22ae3d0129a6b423e9940bd8bc441dd6e1be4)) 

- *(tenantadm)* Expect status 404 instead of 405 when sign-up is disabled
 ([0a48ab1](https://github.com///commit/0a48ab1729d20fd1876fa44920c98749e6923f3a)) 


  Update the docs and the acceptence tests to expect 404 instead of 405

- Put MakeTestRequest in dedicated testing package
 ([7597129](https://github.com///commit/7597129bd6336a8542ec9357dbf4d105de371269)) 


  Utilities for testing should be separate from application code.
- Remove ant0ine/go-json-rest dependency from `requestid.GetReqId()`
 ([863e415](https://github.com///commit/863e41536cd65293b79f65dd127a7100c9d0f569)) 
- Migrate enterprise inventory service to gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([77b1268](https://github.com///commit/77b126808baeeea03fc67f77a9b6c99131fce943)) 


  Migrate the enterprise-only components from ant0nie/go-json-rest to gin-gonic/gin




### Security


- Bump vite from 6.2.6 to 6.3.4 in /frontend
 ([03506da](https://github.com///commit/03506da1dfa189da0a062f03c178e0d67fc69d0d)) 


  Bumps [vite](https://github.com/vitejs/vite/tree/HEAD/packages/vite) from 6.2.6 to 6.3.4.
  - [Release notes](https://github.com/vitejs/vite/releases)
  - [Changelog](https://github.com/vitejs/vite/blob/main/packages/vite/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite/commits/v6.3.4/packages/vite)
  
  ---
  updated-dependencies:
  - dependency-name: vite
    dependency-version: 6.3.4
    dependency-type: indirect
  ...
- Bump the development-dependencies group across 1 directory with 12 updates
 ([30cc04b](https://github.com///commit/30cc04b5c9794066440094afdec1ef2a47edf461)) 


  Bumps the development-dependencies group with 10 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.4.0` | `0.5.0` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.3.8` | `1.3.13` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.3.8` | `1.3.13` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `3.3.1` | `3.5.0` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `22.15.3` | `22.15.29` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `4.4.1` | `4.5.0` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `3.1.2` | `3.1.4` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `15.5.1` | `16.1.0` |
  | [msw](https://github.com/mswjs/msw) | `2.7.5` | `2.8.7` |
  | [undici](https://github.com/nodejs/undici) | `7.8.0` | `7.10.0` |
  
  
  
  Updates `@northern.tech/eslint-config` from 0.4.0 to 0.5.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.4.0...@northern.tech/eslint-config-0.5.0)
  
  Updates `@rspack/cli` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack)
  
  Updates `@sentry/webpack-plugin` from 3.3.1 to 3.5.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/3.3.1...3.5.0)
  
  Updates `@types/node` from 22.15.3 to 22.15.29
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.32.1 to 8.33.0
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.33.0/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 4.4.1 to 4.5.0
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@4.5.0/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/coverage-v8)
  
  Updates `lint-staged` from 15.5.1 to 16.1.0
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v15.5.1...v16.1.0)
  
  Updates `msw` from 2.7.5 to 2.8.7
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.7.5...v2.8.7)
  
  Updates `undici` from 7.8.0 to 7.10.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.8.0...v7.10.0)
  
  Updates `vitest` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 3.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 22.15.29
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.33.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.8.7
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the mui group across 1 directory with 3 updates
 ([96d55d3](https://github.com///commit/96d55d3f34b37fa17ef593d310c1e6e9a0a80a2d)) 


  Bumps the mui group with 3 updates in the /frontend directory: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.2.0 to 8.5.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.5.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the backend-golang-dependencies group
 ([a834409](https://github.com///commit/a834409d316b166dba470fdd36cf8ce13f28d59a)) 


  Bumps the backend-golang-dependencies group in /backend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.79.3` | `1.80.0` |
  | [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) | `1.10.0` | `1.10.1` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.3` | `2.11.4` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.41.2` | `1.42.0` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.8.0` | `9.9.0` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.37.0` | `0.38.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.39.0` | `0.40.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.32.0` | `0.33.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.31.0` | `0.32.0` |
  
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.79.3 to 1.80.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.79.3...service/s3/v1.80.0)
  
  Updates `github.com/gin-gonic/gin` from 1.10.0 to 1.10.1
  - [Release notes](https://github.com/gin-gonic/gin/releases)
  - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/gin-gonic/gin/compare/v1.10.0...v1.10.1)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.3 to 2.11.4
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.3...v2.11.4)
  
  Updates `github.com/nats-io/nats.go` from 1.41.2 to 1.42.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.41.2...v1.42.0)
  
  Updates `github.com/redis/go-redis/v9` from 9.8.0 to 9.9.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.8.0...v9.9.0)
  
  Updates `golang.org/x/crypto` from 0.37.0 to 0.38.0
  - [Commits](https://github.com/golang/crypto/compare/v0.37.0...v0.38.0)
  
  Updates `golang.org/x/net` from 0.39.0 to 0.40.0
  - [Commits](https://github.com/golang/net/compare/v0.39.0...v0.40.0)
  
  Updates `golang.org/x/sys` from 0.32.0 to 0.33.0
  - [Commits](https://github.com/golang/sys/compare/v0.32.0...v0.33.0)
  
  Updates `golang.org/x/term` from 0.31.0 to 0.32.0
  - [Commits](https://github.com/golang/term/compare/v0.31.0...v0.32.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.80.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/gin-gonic/gin
    dependency-version: 1.10.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.9.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.38.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.33.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.32.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 5 updates
 ([bfc4838](https://github.com///commit/bfc4838fefe59382cb747f5745f8b59f23bc4a71)) 


  Bumps the backend-tests-python-dependencies group with 5 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [boto3](https://github.com/boto/boto3) | `1.38.6` | `1.38.27` |
  | [cryptography](https://github.com/pyca/cryptography) | `44.0.2` | `45.0.3` |
  | [pluggy](https://github.com/pytest-dev/pluggy) | `1.5.0` | `1.6.0` |
  | [redis](https://github.com/redis/redis-py) | `5.2.1` | `6.2.0` |
  | [pytest-xdist](https://github.com/pytest-dev/pytest-xdist) | `3.6.1` | `3.7.0` |
  
  
  
  Updates `boto3` from 1.38.6 to 1.38.27
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.38.6...1.38.27)
  
  Updates `cryptography` from 44.0.2 to 45.0.3
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/44.0.2...45.0.3)
  
  Updates `pluggy` from 1.5.0 to 1.6.0
  - [Changelog](https://github.com/pytest-dev/pluggy/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pluggy/compare/1.5.0...1.6.0)
  
  Updates `redis` from 5.2.1 to 6.2.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v5.2.1...v6.2.0)
  
  Updates `pytest-xdist` from 3.6.1 to 3.7.0
  - [Release notes](https://github.com/pytest-dev/pytest-xdist/releases)
  - [Changelog](https://github.com/pytest-dev/pytest-xdist/blob/master/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pytest-xdist/compare/v3.6.1...v3.7.0)
  
  ---
  updated-dependencies:
  - dependency-name: boto3
    dependency-version: 1.38.27
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 45.0.3
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pluggy
    dependency-version: 1.6.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 6.2.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pytest-xdist
    dependency-version: 3.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...
- Bump webpack-dev-server and @rspack/cli in /frontend
 ([ff4bc85](https://github.com///commit/ff4bc85de991a11e258ba0a1e4a6e1fbd81592f5)) 


  Bumps [webpack-dev-server](https://github.com/webpack/webpack-dev-server) to 5.2.2 and updates ancestor dependency [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli). These dependencies need to be updated together.
  
  
  Updates `webpack-dev-server` from 5.2.0 to 5.2.2
  - [Release notes](https://github.com/webpack/webpack-dev-server/releases)
  - [Changelog](https://github.com/webpack/webpack-dev-server/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/webpack/webpack-dev-server/compare/v5.2.0...v5.2.2)
  
  Updates `@rspack/cli` from 1.3.13 to 1.3.15
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.15/packages/rspack-cli)
  
  ---
  updated-dependencies:
  - dependency-name: webpack-dev-server
    dependency-version: 5.2.2
    dependency-type: indirect
  - dependency-name: "@rspack/cli"
    dependency-version: 1.3.15
    dependency-type: direct:development
  ...
- Bump requests in /backend/services/iot-manager/tests
 ([695983a](https://github.com///commit/695983abeeaf65400923ec435f2738d7475d7cf5)) 


  Bumps [requests](https://github.com/psf/requests) from 2.32.3 to 2.32.4.
  - [Release notes](https://github.com/psf/requests/releases)
  - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
  - [Commits](https://github.com/psf/requests/compare/v2.32.3...v2.32.4)
  
  ---
  updated-dependencies:
  - dependency-name: requests
    dependency-version: 2.32.4
    dependency-type: direct:production
  ...
- Bump the backend-docker-dependencies group across 10 directories with 1 update
 ([f39b7fb](https://github.com///commit/f39b7fb012b5b92cd74e8042f4fedd12e95ed394)) 


  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/create-artifact-worker directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deployments directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceauth directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconfig directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconnect directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/inventory directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/iot-manager directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/reporting directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/useradm directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/workflows directory: golang.
  
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  Updates `golang` from 1.24.3 to 1.24.4
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump @mui/x-date-pickers in /frontend in the mui group
 ([0b07854](https://github.com///commit/0b07854d18232ca6bc0f31235ee04db9055c7081)) 


  Bumps the mui group in /frontend with 1 update: [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/x-date-pickers` from 8.5.0 to 8.5.1
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.5.1/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.5.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  ...
- Bump the production-dependencies group
 ([ef7e609](https://github.com///commit/ef7e609525b582ae01d05d33d36f7aa456e09c09)) 


  Bumps the production-dependencies group in /frontend with 3 updates: [@sentry/react](https://github.com/getsentry/sentry-javascript), [react-hook-form](https://github.com/react-hook-form/react-hook-form) and [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom).
  
  
  Updates `@sentry/react` from 9.24.0 to 9.28.1
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/9.24.0...9.28.1)
  
  Updates `react-hook-form` from 7.56.4 to 7.57.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.56.4...v7.57.0)
  
  Updates `react-router-dom` from 7.6.1 to 7.6.2
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/7.6.2/packages/react-router-dom)
  
  ---
  updated-dependencies:
  - dependency-name: "@sentry/react"
    dependency-version: 9.28.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.57.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.6.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump @playwright/test
 ([be22a5f](https://github.com///commit/be22a5fd353920f7c195bc1866e7dba38564f116)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.52.0 to 1.53.0
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.52.0...v1.53.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.53.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...




### Build


- Change default make target to test for backend/pkg
 ([5ba3fd7](https://github.com///commit/5ba3fd7deda6421612029b31317cc61c2b1ef373)) 
- Add make target for pkg unit tests to test-unit root target
 ([5c2e23a](https://github.com///commit/5c2e23a6ff9b073b38cad1ef56e8845264369817)) 




### Revert


- *(tenantadm)* Restore swagger specifications for generating types
 ([c06ad4e](https://github.com///commit/c06ad4e61f39c5c982596db72036cd3e1b7e1d0c)) 


  ... and remove symlink to new specifications.

- Gin utility for applying middleware to routes
 ([9f5c79c](https://github.com///commit/9f5c79cc30a4ee2576ef39f650b3a161c5996548)) 


  The func does not implement what it is intended to do and instead
  applies the middleware to all routes in the group.
- "ci: Debug mongodb in backend unit tests"
 ([441c1ea](https://github.com///commit/441c1eaa43cc79737468aef3068784f0bfadef28)) 


  Enabling logging just overflows the log buffer.
  
  This reverts commit 6d164c4c70d1fff7d28e88a50390f8afb676c814.






## v4.1.0-saas.6 - 2025-06-05


### Bug Fixes


- *(gui)* Changed cancel button in device configuration edit to close the form
([MEN-8344](https://northerntech.atlassian.net/browse/MEN-8344)) ([f1f542a](https://github.com///commit/f1f542a4322de05692da5a94d85a61d1c840488e)) 

- *(gui)* Made RBAC roles visible again for non-enterprise users
 ([43f829b](https://github.com///commit/43f829b6ec0e44bef0ed1de1a1b83e4e56077afd)) 

- *(gui)* Restored role removal prevention for built-in roles
 ([89a1c43](https://github.com///commit/89a1c431af488c7c07577ff5ea4f06b96ef2362d)) 

- *(gui)* Aligned Roles & Users drawer closing behaviour
([MEN-8063](https://northerntech.atlassian.net/browse/MEN-8063)) ([346fd97](https://github.com///commit/346fd976cfd026e4b8c85cdf7765f4593a94598b)) 

- *(gui)* Fixed closing animation for deployment drawer
([MEN-8063](https://northerntech.atlassian.net/browse/MEN-8063)) ([a9bca65](https://github.com///commit/a9bca657c31002b053297d0c371a191f1369f4e3)) 

- *(gui)* Restored error handling on user edits
([ME-522](https://northerntech.atlassian.net/browse/ME-522)) ([882a5c7](https://github.com///commit/882a5c7f6bc03325a4fd5875d2b92d22fe6d7e29)) 


  - regression from 5888d3e3ee47b764b256e89da9419f903936e4f3 in the prior repo

- *(gui)* Fixed an issue that would prevent showing all webhook activity
 ([70d9eda](https://github.com///commit/70d9eda75dd1cf955daa892bcc86a9760743be5f)) 

- *(gui)* Fixed reset button location in device tags & similar editors
 ([00335b2](https://github.com///commit/00335b22dff4b324269ceeeac2e664caa061c960)) 

- *(gui)* Allowed clearing device tags & device configuration entirely
([ME-529](https://northerntech.atlassian.net/browse/ME-529)) ([896f2a9](https://github.com///commit/896f2a967220ecc514b99e8873841ed31f2d2dde)) 

- *(gui)* Fixed location of device name tag help to not disturb tag editor
 ([e27417c](https://github.com///commit/e27417cbb4298f235bf31044b5934501affcc9af)) 


  - this takes the kv related styles from less into the component making theming a bit more consistent and encapsulating the component further

- *(gui)* Prevented device tag editor to be shown when no tags exist
([ME-528](https://northerntech.atlassian.net/browse/ME-528)) ([3b6b0db](https://github.com///commit/3b6b0dbbe39c278bd10d2385c82fd34042d1dbac)) 


  - this is to reduce confusion about tags defined async to the current session not being visible

- *(useradm)* RBAC - fix permissions related to inventory filters
([ME-513](https://northerntech.atlassian.net/browse/ME-513)) ([fdb7cd4](https://github.com///commit/fdb7cd4de58f7b03860ee6c20f6deae8fc2417ee)) 


  Users without access to all devices should not be able to get
  inventory filers by Id.





### Documentation


- Fixed parameter in reset password and verify email endpoints
([MEN-8267](https://northerntech.atlassian.net/browse/MEN-8267)) ([649fde5](https://github.com///commit/649fde578ac5c6650855db2dd28d6723b297c29b)) 
- Add API specification for changing subscription
([MEN-8145](https://northerntech.atlassian.net/browse/MEN-8145)) ([ab82128](https://github.com///commit/ab821285d360a29fa3b39486662aaebd0eed69b1)) 




### Features


- *(gui)* Made device tags functionality available in all device auth states
([ME-528](https://northerntech.atlassian.net/browse/ME-528)) ([7b1f3c6](https://github.com///commit/7b1f3c61e4b4151cb81a8aab5c4a22c581e01cb3)) 

- *(gui)* Let tenant token not be visible by default
([MEN-8397](https://northerntech.atlassian.net/browse/MEN-8397)) ([b70e0b4](https://github.com///commit/b70e0b44cf627d6b0621da92f0d0a154588aafb1)) 

- *(gui)* Made device tag setting requirement for fully defined keys & values more visible
 ([a3ec69f](https://github.com///commit/a3ec69ff8e3fd2940ead0e355a9dc2ac84b9b302)) 

- New billing API for managing subscription
([MEN-8145](https://northerntech.atlassian.net/browse/MEN-8145)) ([e9e489d](https://github.com///commit/e9e489d21711ed098e279698c6cbe46c690460f4)) 


  The new endpoint
  `POST /api/management/v2/tenantadm/billing/subscription`
  allows the customer to upgrade plan, enable add-ons and change the
  device limit.




### Performance


- Put routing path and parameters in separate accesslog fields
 ([51832b6](https://github.com///commit/51832b685d70d6dbe2f8cdf8442b96d6eec843fb)) 


  By separating the two, it is much less complex to index paths in the log
  parser.




### Refactor


- *(inventory)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([f6899d4](https://github.com///commit/f6899d44129b892708bbe0bfcc485fbf8f705166)) 

- Put MakeTestRequest in dedicated testing package
 ([7597129](https://github.com///commit/7597129bd6336a8542ec9357dbf4d105de371269)) 


  Utilities for testing should be separate from application code.
- Migrate enterprise inventory service to gin
([MEN-8236](https://northerntech.atlassian.net/browse/MEN-8236)) ([77b1268](https://github.com///commit/77b126808baeeea03fc67f77a9b6c99131fce943)) 


  Migrate the enterprise-only components from ant0nie/go-json-rest to gin-gonic/gin




### Security


- Bump the backend-docker-dependencies group across 10 directories with 2 updates
 ([7daaeda](https://github.com///commit/7daaeda97fdf10652498ed2c3db82d0030486de4)) 


  Bumps the backend-docker-dependencies group with 2 updates in the /backend/services/create-artifact-worker directory: golang and alpine.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deployments directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceauth directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconfig directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/deviceconnect directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/inventory directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/iot-manager directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/reporting directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/useradm directory: golang.
  Bumps the backend-docker-dependencies group with 1 update in the /backend/services/workflows directory: golang.
  
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `alpine` from 3.21.3 to 3.22.0
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  Updates `golang` from 1.24.2 to 1.24.3
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: alpine
    dependency-version: 3.22.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump node in /frontend
 ([906c5f3](https://github.com///commit/906c5f3632d55ba59898b4146919ad465c9acc9f)) 


  Bumps node from 23.11.0-alpine3.20 to 24.1.0-alpine3.20.
  
  ---
  updated-dependencies:
  - dependency-name: node
    dependency-version: 24.1.0-alpine3.20
    dependency-type: direct:production
    update-type: version-update:semver-major
  ...
- Bump yaml
 ([64b5ae9](https://github.com///commit/64b5ae9b391ec548b940cfe5302bbdf7125b7671)) 


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 1 update: [yaml](https://github.com/eemeli/yaml).
  
  
  Updates `yaml` from 2.7.1 to 2.8.0
  - [Release notes](https://github.com/eemeli/yaml/releases)
  - [Commits](https://github.com/eemeli/yaml/compare/v2.7.1...v2.8.0)
  
  ---
  updated-dependencies:
  - dependency-name: yaml
    dependency-version: 2.8.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump the production-dependencies group
 ([b273830](https://github.com///commit/b273830a45f46e45f7b5d4244856ef8f3ee95ef6)) 


  Bumps the production-dependencies group in /frontend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.7.0` | `2.8.2` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `9.15.0` | `9.24.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `3.6.0` | `3.7.0` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `7.2.0` | `7.3.1` |
  | [react-big-calendar](https://github.com/jquense/react-big-calendar) | `1.18.0` | `1.19.2` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.56.1` | `7.56.4` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.5.3` | `7.6.1` |
  | [tss-react](https://github.com/garronej/tss-react) | `4.9.16` | `4.9.18` |
  | [validator](https://github.com/validatorjs/validator.js) | `13.15.0` | `13.15.15` |
  
  
  Updates `@reduxjs/toolkit` from 2.7.0 to 2.8.2
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.7.0...v2.8.2)
  
  Updates `@sentry/react` from 9.15.0 to 9.24.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/9.15.0...9.24.0)
  
  Updates `@stripe/react-stripe-js` from 3.6.0 to 3.7.0
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v3.6.0...v3.7.0)
  
  Updates `@stripe/stripe-js` from 7.2.0 to 7.3.1
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v7.2.0...v7.3.1)
  
  Updates `react-big-calendar` from 1.18.0 to 1.19.2
  - [Release notes](https://github.com/jquense/react-big-calendar/releases)
  - [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/jquense/react-big-calendar/compare/v1.18.0...v1.19.2)
  
  Updates `react-hook-form` from 7.56.1 to 7.56.4
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.56.1...v7.56.4)
  
  Updates `react-router-dom` from 7.5.3 to 7.6.1
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.6.1/packages/react-router-dom)
  
  Updates `tss-react` from 4.9.16 to 4.9.18
  - [Release notes](https://github.com/garronej/tss-react/releases)
  - [Commits](https://github.com/garronej/tss-react/compare/v4.9.16...v4.9.18)
  
  Updates `validator` from 13.15.0 to 13.15.15
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.0...13.15.15)
  
  ---
  updated-dependencies:
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.8.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 9.24.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 3.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 7.3.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-big-calendar
    dependency-version: 1.19.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.56.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.6.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: tss-react
    dependency-version: 4.9.18
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: validator
    dependency-version: 13.15.15
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump the development-dependencies group across 1 directory with 12 updates
 ([30cc04b](https://github.com///commit/30cc04b5c9794066440094afdec1ef2a47edf461)) 


  Bumps the development-dependencies group with 10 updates in the /frontend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.4.0` | `0.5.0` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.3.8` | `1.3.13` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.3.8` | `1.3.13` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `3.3.1` | `3.5.0` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `22.15.3` | `22.15.29` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `4.4.1` | `4.5.0` |
  | [@vitest/coverage-v8](https://github.com/vitest-dev/vitest/tree/HEAD/packages/coverage-v8) | `3.1.2` | `3.1.4` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `15.5.1` | `16.1.0` |
  | [msw](https://github.com/mswjs/msw) | `2.7.5` | `2.8.7` |
  | [undici](https://github.com/nodejs/undici) | `7.8.0` | `7.10.0` |
  
  
  
  Updates `@northern.tech/eslint-config` from 0.4.0 to 0.5.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.4.0...@northern.tech/eslint-config-0.5.0)
  
  Updates `@rspack/cli` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.3.8 to 1.3.13
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.3.13/packages/rspack)
  
  Updates `@sentry/webpack-plugin` from 3.3.1 to 3.5.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/3.3.1...3.5.0)
  
  Updates `@types/node` from 22.15.3 to 22.15.29
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.32.1 to 8.33.0
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.33.0/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 4.4.1 to 4.5.0
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@4.5.0/packages/plugin-react)
  
  Updates `@vitest/coverage-v8` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/coverage-v8)
  
  Updates `lint-staged` from 15.5.1 to 16.1.0
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v15.5.1...v16.1.0)
  
  Updates `msw` from 2.7.5 to 2.8.7
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.7.5...v2.8.7)
  
  Updates `undici` from 7.8.0 to 7.10.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.8.0...v7.10.0)
  
  Updates `vitest` from 3.1.2 to 3.1.4
  - [Release notes](https://github.com/vitest-dev/vitest/releases)
  - [Commits](https://github.com/vitest-dev/vitest/commits/v3.1.4/packages/vitest)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.3.13
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 3.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 22.15.29
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.33.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.8.7
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.1.4
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the mui group across 1 directory with 3 updates
 ([96d55d3](https://github.com///commit/96d55d3f34b37fa17ef593d310c1e6e9a0a80a2d)) 


  Bumps the mui group with 3 updates in the /frontend directory: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.1.0 to 7.1.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.1.1/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.2.0 to 8.5.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.5.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.1.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...




### Build


- Change default make target to test for backend/pkg
 ([5ba3fd7](https://github.com///commit/5ba3fd7deda6421612029b31317cc61c2b1ef373)) 
- Add make target for pkg unit tests to test-unit root target
 ([5c2e23a](https://github.com///commit/5c2e23a6ff9b073b38cad1ef56e8845264369817)) 




### Revert


- "ci: Debug mongodb in backend unit tests"
 ([441c1ea](https://github.com///commit/441c1eaa43cc79737468aef3068784f0bfadef28)) 


  Enabling logging just overflows the log buffer.
  
  This reverts commit 6d164c4c70d1fff7d28e88a50390f8afb676c814.





## 4.1.0-saas.5 - 2025-05-09


### Bug Fixes


- *(deployments)* Invalid Location header when returning 201 Created
 ([cfccf2a](https://github.com/mendersoftware/mender-server-enterprise/commit/cfccf2a8e71814d8fca40e9135aa6afe06f15344))  by @alfrunes


  The location strips the `/api` path prefix and returns the remaining
  absolute path as relative. Instead, always return the absolute path.

- *(deployments)* Validate configuration on updates
([MEN-8287](https://northerntech.atlassian.net/browse/MEN-8287)) ([ccad883](https://github.com/mendersoftware/mender-server-enterprise/commit/ccad883d7336da2e6181c995f4f09348220f4778))  by @kjaskiewiczz


  With this commit, when doing configuration update using internal
  endpoint, we validate the configuration.

- *(gui)* Fixed an issue that would prevent showing unassigned static group devices
([ME-519](https://northerntech.atlassian.net/browse/ME-519)) ([cf7f15d](https://github.com/mendersoftware/mender-server-enterprise/commit/cf7f15d7cc1b2761ec1ad2804387cb62e155504a))  by @mineralsfree

- *(gui)* Fixed an issue that would add device filter automatically
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([8d0233c](https://github.com/mendersoftware/mender-server-enterprise/commit/8d0233cadf69f6930888c7820579f02611841a02))  by @mineralsfree

- *(gui)* Fixed an issue with a filter input not reset after save
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([ed6b9f9](https://github.com/mendersoftware/mender-server-enterprise/commit/ed6b9f97d1d55bef11b50b880b9fd14a488d9d94))  by @mineralsfree

- *(gui)* Fixed an issue with 'true' value being set after selecting 'exists' operator
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([b8c8d8a](https://github.com/mendersoftware/mender-server-enterprise/commit/b8c8d8a9fea896dccc1add172816ebbb5b85ebfd))  by @mineralsfree

- *(gui)* Ensured selection filter is reset when attribute or value input are emptied
([MEN-8309](https://northerntech.atlassian.net/browse/MEN-8309)) ([9cb2ff3](https://github.com/mendersoftware/mender-server-enterprise/commit/9cb2ff3e002d045a225c4a3de30be0cd51e6fc0e))  by @mineralsfree

- *(gui)* Restored global settings layout after general input layout adjustments
 ([f83c94e](https://github.com/mendersoftware/mender-server-enterprise/commit/f83c94eb38a1a425e8031d0693262120bb48db6b))  by @mzedel

- *(gui)* Fixed an issue that prevented showing deployment calendar entries
 ([a7d386f](https://github.com/mendersoftware/mender-server-enterprise/commit/a7d386fdcaa19f81db059d709e52d998c0e99ea8))  by @mzedel

- *(useradm)* RBAC - fix permissions related to inventory filters
([ME-510](https://northerntech.atlassian.net/browse/ME-510)) ([c38ab7f](https://github.com/mendersoftware/mender-server-enterprise/commit/c38ab7f5a024d2bdeffaff1d0a3ca06f0083d11a))  by @kjaskiewiczz


  Users without access to all devices should not be able to delete
  inventory filers.

- *(useradm)* Fix permissions for assigning users to tenants
([ME-507](https://northerntech.atlassian.net/browse/ME-507)) ([0efc65e](https://github.com/mendersoftware/mender-server-enterprise/commit/0efc65e970f2cb75fda55be534c13580d99dd239))  by @kjaskiewiczz


  User with multiple roles, where one of the roles is Admin role, should
  be able to assign users to tenants.

- Check if deployment was found when updating device deployment status
([MEN-7749](https://northerntech.atlassian.net/browse/MEN-7749)) ([6b15227](https://github.com/mendersoftware/mender-server-enterprise/commit/6b15227135cc38dd96813c204c3a12d494f0313f))  by @bahaa-ghazal
- Ensure email is always encoded in lowercase when stored
([MEN-8328](https://northerntech.atlassian.net/browse/MEN-8328)) ([d80c818](https://github.com/mendersoftware/mender-server-enterprise/commit/d80c818eed43765387cfe81445e187f9c1833156))  by @alfrunes


  Added a bson codec for model.Email that will ensure that emails are
  always encoded in lowercase in the database to ensure case insensitive
  queries.




### Documentation


- *(deployments)* Fix API specification
([QA-990](https://northerntech.atlassian.net/browse/QA-990)) ([4f8d069](https://github.com/mendersoftware/mender-server-enterprise/commit/4f8d069d054761479abad32b2c1630581be3a422))  by @kjaskiewiczz


  Remove type properties from fields where value is not strictly defined.

- *(inventory)* Migrate API specs to OpenAPI v3.0.1
([QA-886](https://northerntech.atlassian.net/browse/QA-886)) ([e7ce7e5](https://github.com/mendersoftware/mender-server-enterprise/commit/e7ce7e5762405732e9cb02ee32447dc1073ee369))  by @kjaskiewiczz

- Fix API specifications to be compliant with OpenAPI 3 format
([QA-990](https://northerntech.atlassian.net/browse/QA-990)) ([26e9fd2](https://github.com/mendersoftware/mender-server-enterprise/commit/26e9fd22c9e3a7c34b4564703842f8b7d7282948))  by @kjaskiewiczz
- Covert enterprise API docs to OpenAPI v3
([QA-886](https://northerntech.atlassian.net/browse/QA-886)) ([f44166c](https://github.com/mendersoftware/mender-server-enterprise/commit/f44166c8edf5a9c54e28631075511bbea0651721))  by @alfrunes




### Features


- *(deviceauth)* Rate limit authenticated devices API
([MEN-7744](https://northerntech.atlassian.net/browse/MEN-7744)) ([8c80280](https://github.com/mendersoftware/mender-server-enterprise/commit/8c8028081a54a62ba8673071350414b096aa87b0))  by @alfrunes


  Added adaptive ratelimiting for devices APIs based on the `max_devices`
  limit. Two new configuration options are exposed:
   * `ratelimits.interval` - duration until the quota resets
   * `ratelimits.quotas` - mapping plan names to quota weights. The final
     burst limit is computed as `ratelimits.quotas[plan] * max_devices`
  
  The rate limiting counter is independent for each API path (independent
  of method and version).

- *(deviceauth)* Rate limit device requests
([MEN-7744](https://northerntech.atlassian.net/browse/MEN-7744)) ([9c3041f](https://github.com/mendersoftware/mender-server-enterprise/commit/9c3041f5d54ea06c920ae0cc977c8af594133fb2))  by @alfrunes


  Added adaptive ratelimiting for devices APIs based on the `max_devices`
  limit. Two new configuration options are exposed:
   * `ratelimits.devices.enable` - enable device level rate limit
   * `ratelimits.devices.interval` - duration until the quota resets
   * `ratelimits.devices.quota_plan` - mapping plan names to quota
      weights. The final burst limit is computed as
      `ratelimits.quotas[plan] * max_devices`
   * `ratelimits.devices.quota_default` - rate limit fallback for plans
     with undefined limits.
  
  The rate limiting counter is independent for each API path (independent
  of method and version).

- *(generate-delta-worker)* Update `mender-artifact` to latest v4.1.0
([MEN-8337](https://northerntech.atlassian.net/browse/MEN-8337)) ([294c6dd](https://github.com/mendersoftware/mender-server-enterprise/commit/294c6dd8c2e9bef4c1907559f0f7fe8fd0583125))  by @lluiscampos


  Modifying also the integration to build the tool from source instead or
  repurposing the upstream Debian package. This has the main advantage
  that we can compile it statically (by disabling a feature that we don't
  use) and that we have control of the compatibility aspects of the
  binary.

- Add caching for device limits
([MEN-7760](https://northerntech.atlassian.net/browse/MEN-7760)) ([5466c62](https://github.com/mendersoftware/mender-server-enterprise/commit/5466c626ca1437ed366151263c3bc03686c58853))  by @alfrunes
- Delta generation job details view API support
([MEN-8289](https://northerntech.atlassian.net/browse/MEN-8289)) ([00fb186](https://github.com/mendersoftware/mender-server-enterprise/commit/00fb1864b6edf4db1f0037a34beb446d72503114))  by @merlin-northern
- Implemented content type checker middleware for gin framework
([MEN-8327](https://northerntech.atlassian.net/browse/MEN-8327)) ([9016554](https://github.com/mendersoftware/mender-server-enterprise/commit/9016554b702297ad00f1a748d0824fdf19d05678))  by @bahaa-ghazal




### Revert


- Gin utility for applying middleware to routes
 ([9f5c79c](https://github.com/mendersoftware/mender-server-enterprise/commit/9f5c79cc30a4ee2576ef39f650b3a161c5996548))  by @alfrunes


  The func does not implement what it is intended to do and instead
  applies the middleware to all routes in the group.






## 4.1.0-saas.4 - 2025-04-10


### Bug Fixes


- *(gui)* Fixed an issue where admin existence sometimes wasn't taken into account on tenant creation
 ([330ac67](https://github.com/mendersoftware/mender-server-enterprise/commit/330ac67ee20b0ffeaf9a20b9f48db5b48a2bd169))  by @mzedel

- *(gui)* Fixed an issue that prevented properly paginating deployments
([MEN-8212](https://northerntech.atlassian.net/browse/MEN-8212)) ([a20db14](https://github.com/mendersoftware/mender-server-enterprise/commit/a20db1477aab026d60297e789cbbd85e242b8d7c))  by @mzedel

- *(gui)* Fixed an issue on tenant creation that prevented some email addresses from becoming tenant admins
([ME-470](https://northerntech.atlassian.net/browse/ME-470)) ([20b32f9](https://github.com/mendersoftware/mender-server-enterprise/commit/20b32f90130521dd54d51ff30202e122b298a093))  by @mzedel

- *(gui)* Fixed an issue that would retain passwords on tenant creation across different admins
 ([a5e2132](https://github.com/mendersoftware/mender-server-enterprise/commit/a5e2132c015bd3a7c296c6848cf136157ffbad1b))  by @mzedel

- *(gui)* Fixed layout issue on tenant list + aligned styling with remainder of codebase
 ([cc41aee](https://github.com/mendersoftware/mender-server-enterprise/commit/cc41aee501ecd4834c73abc051e51df3a90b8868))  by @mzedel

- *(gui)* Fixed an issue propagating password validation errors
 ([d1d8827](https://github.com/mendersoftware/mender-server-enterprise/commit/d1d882768d39b7cca657cd091c5bcedd8e416f57))  by @mzedel

- *(gui)* Ensured errormessages get propagated in forms
 ([b19f8b3](https://github.com/mendersoftware/mender-server-enterprise/commit/b19f8b33727fd0aab573ebf677a93a3a7811ae39))  by @mzedel

- *(gui)* Fixed an issue that could hinder pagination in very frequently created deployments
 ([34ca4ea](https://github.com/mendersoftware/mender-server-enterprise/commit/34ca4eab7332388e3ddd5a830b8458890315ee42))  by @mzedel

- *(useradm)* Added missing permission scope option to allow generating correct types
 ([e956965](https://github.com/mendersoftware/mender-server-enterprise/commit/e9569657d3fd7dbf638879c320d79029e814ed48))  by @mzedel

- *(useradm)* Added missing permission information in API specs
 ([1f534d1](https://github.com/mendersoftware/mender-server-enterprise/commit/1f534d15c382da7fc3e0498bd064f2c9f6291814))  by @mzedel

- *(deployments)* Use the read preference in FindOldestActiveDeviceDeployment
 ([10f8b55](https://github.com/mendersoftware/mender-server-enterprise/commit/10f8b5503fa2901cb1ecdc374117b513ed9b841b))  by @merlin-northern




### Documentation


- *(deployments)* GET delta/jobs endpoint API docs
([MEN-8199](https://northerntech.atlassian.net/browse/MEN-8199)) ([8bec3b5](https://github.com/mendersoftware/mender-server-enterprise/commit/8bec3b59c805b55a52df77765bd794064e52d089))  by @merlin-northern

- *(deviceauth)* Enhance description of the /devices/count endpoint
([MEN-8255](https://northerntech.atlassian.net/browse/MEN-8255)) ([c9e3633](https://github.com/mendersoftware/mender-server-enterprise/commit/c9e3633f10d6439b8e6e19b49607ebb0d2c83c76))  by @kjaskiewiczz





### Features


- *(deployments)* Get the list of delta generation jobs
([MEN-8199](https://northerntech.atlassian.net/browse/MEN-8199)) ([a0ed3b0](https://github.com/mendersoftware/mender-server-enterprise/commit/a0ed3b08a5b91cadc6e334789aa205b57eab7694))  by @merlin-northern

- *(gui)* Made subtenant creation a bit more comfortable in case of errors
([ME-469](https://northerntech.atlassian.net/browse/ME-469)) ([e01171f](https://github.com/mendersoftware/mender-server-enterprise/commit/e01171fe5aa9434cad9eefb16f52a6c785657bbe))  by @mzedel

- *(gui)* Added more user visible context on tenant creation failures
 ([c027064](https://github.com/mendersoftware/mender-server-enterprise/commit/c02706471c536f15e844fd5806deb999dbdbb5d2))  by @mzedel


  - also centralized mui alert styling to account for increased usage

- *(gui)* Made login form less reactive when entering login info
([MEN-8221](https://northerntech.atlassian.net/browse/MEN-8221)) ([00b4d7b](https://github.com/mendersoftware/mender-server-enterprise/commit/00b4d7be55cfaebdbcd787e308a720d01a40362d))  by @mzedel

- *(gui)* Added sentry integration
 ([0fe2ad0](https://github.com/mendersoftware/mender-server-enterprise/commit/0fe2ad0682fc250f75947f8eda690663a3ad2b7d))  by @mzedel

- *(gui)* Enhanced debugging info to help track down user issues
 ([c559467](https://github.com/mendersoftware/mender-server-enterprise/commit/c559467c461470e66d7d3a68674511c1215a8cc2))  by @mzedel

- *(gui)* Allowed enabling fine grained state debug information to be sent
 ([298059d](https://github.com/mendersoftware/mender-server-enterprise/commit/298059dff2d29cb8367b50753e0b7421ceb28341))  by @mzedel





### Refac


- *(gui)* Split signup in separate forms to ease handling validation mode differences
 ([620592b](https://github.com/mendersoftware/mender-server-enterprise/commit/620592bea038b835990e7625db7ae7f736f3f6e4))  by @mzedel

- *(gui)* Rely on externally gzipping build files to use sourcemaps in sentry
 ([24bdd2f](https://github.com/mendersoftware/mender-server-enterprise/commit/24bdd2f3f048e8088daf40fffd92afc7eed15dbc))  by @mzedel







## 4.1.0-saas.3 - 2025-03-20


### Bug Fixes


- *(deployment)* Ignore false errors when deleting data that does not exist
([MEN-8213](https://northerntech.atlassian.net/browse/MEN-8213)) ([532d95a](https://github.com/mendersoftware/mender-server-enterprise/commit/532d95ab87f1bea1027d7ff83b3281c7d4740f26))  by @bahaa-ghazal

- *(gui)* Removed border on active tab in left nav bar
([MEN-8113](https://northerntech.atlassian.net/browse/MEN-8113)) ([a5d5df4](https://github.com/mendersoftware/mender-server-enterprise/commit/a5d5df49f70a34427edcde7348858fbb9d18c4b7))  by @mineralsfree

- *(gui)* Fixed time filter in past deployments
([MEN-7989](https://northerntech.atlassian.net/browse/MEN-7989)) ([25cdee0](https://github.com/mendersoftware/mender-server-enterprise/commit/25cdee07a5e6f76942f8b0dcaa67a4f76b1b2ecb))  by @mineralsfree

- *(gui)* Fixed location not being changed on device status filter change
([MEN-8118](https://northerntech.atlassian.net/browse/MEN-8118)) ([36eb469](https://github.com/mendersoftware/mender-server-enterprise/commit/36eb4695544a0fdc2559d4178b9e0cfa5c647691))  by @mineralsfree

- *(gui)* Restored rspack to license generator compatible version
 ([1280dc7](https://github.com/mendersoftware/mender-server-enterprise/commit/1280dc7363135444575611f32f5011935557f01b))  by @mzedel

- *(gui)* Fixed default roles being shown before loading ones from backend
([MEN-8095](https://northerntech.atlassian.net/browse/MEN-8095)) ([d934020](https://github.com/mendersoftware/mender-server-enterprise/commit/d9340200ce40229fab441e2334117906ab18e103))  by @mineralsfree

- *(gui)* Fixed an issue that would prevent new signups from using the onboarding
 ([fbaa329](https://github.com/mendersoftware/mender-server-enterprise/commit/fbaa329fb66bb3dc687db463a7cc507f8643a6b8))  by @mzedel

- *(gui)* Default to eu in eu.hosted domain during signup
([MEN-7925](https://northerntech.atlassian.net/browse/MEN-7925)) ([0512d24](https://github.com/mendersoftware/mender-server-enterprise/commit/0512d24b7b6ddbf8e90677f737da4625d95c5e6f))  by @mineralsfree

- *(gui)* Fixed webhook configuration checks by subscription
 ([6b5989d](https://github.com/mendersoftware/mender-server-enterprise/commit/6b5989d8b61fc05bde9b788b69b60474f99983f2))  by @mzedel

- *(gui)* Ensured form validation is applied during validation phase only
 ([b6b870c](https://github.com/mendersoftware/mender-server-enterprise/commit/b6b870c9c39a3e5a24f42ef9bec02184fc830bb0))  by @mzedel

- *(gui)* Fixed permission extension issue in roles form
([MEN-8108](https://northerntech.atlassian.net/browse/MEN-8108)) ([0a41d0d](https://github.com/mendersoftware/mender-server-enterprise/commit/0a41d0dd4fec2a82ab8e746fa6a8a748843dc1a3))  by @mineralsfree

- *(gui)* Fixed an issue that prevented phased deployments when reusing phase definitions
([MEN-8192](https://northerntech.atlassian.net/browse/MEN-8192)) ([f9b735f](https://github.com/mendersoftware/mender-server-enterprise/commit/f9b735f250a41db9e073546fc69a6a471028a50a))  by @mzedel

- *(gui)* Fixed an issue that could clear search queries
 ([c308b2b](https://github.com/mendersoftware/mender-server-enterprise/commit/c308b2bd72f915c11521af236f9fd4ed6659f4e4))  by @mzedel


  - when search was run multiple times in non-search searchfields

- *(gui)* Provide more context on failed 2fa enabled login
 ([dfcb767](https://github.com/mendersoftware/mender-server-enterprise/commit/dfcb767e33c054bdca64aba209eb8ce05902a89a))  by @mzedel

- *(gui)* Fixed an issue that would prevent some info messages from showing
 ([e1277bd](https://github.com/mendersoftware/mender-server-enterprise/commit/e1277bdf3c289d2c383ce4303da4567606193bf5))  by @mzedel

- *(gui)* Restored group creation notification
 ([3bdb3f3](https://github.com/mendersoftware/mender-server-enterprise/commit/3bdb3f34c8b1e6aa3c2e1cf34a619933684d4f04))  by @mzedel

- *(iot-manager)* Do not store events if there are no integrations
([MEN-7868](https://northerntech.atlassian.net/browse/MEN-7868)) ([0c0ee9d](https://github.com/mendersoftware/mender-server-enterprise/commit/0c0ee9d3e497d04cbf43e4693fbdd17c30f1edb3))  by @merlin-northern

- *(iot-manager)* Creating new integration creates a new ID
([MEN-7801](https://northerntech.atlassian.net/browse/MEN-7801)) ([c52491e](https://github.com/mendersoftware/mender-server-enterprise/commit/c52491eb648fa6ab6550ca39386327b1ae2de4df))  by @merlin-northern

- *(tenantadm)* Emit structured logs on request panic
 ([6c67dc3](https://github.com/mendersoftware/mender-server-enterprise/commit/6c67dc36b07e41cbef1367f241a2637fcf311bab))  by @alfrunes


  The former request middleware handling Go panics would emit the panic
  stack trace in an unstructured format. This commit lets the accesslog
  handle it and emit it in the `trace` log context key.

- *(tenantadm)* Waiting for workflow does not abort immediately when it is not yet scheduled
([MEN-8165](https://northerntech.atlassian.net/browse/MEN-8165)) ([6dc0790](https://github.com/mendersoftware/mender-server-enterprise/commit/6dc0790b8c000eba3203fcc36ff9ccd303102ba0))  by @bahaa-ghazal

- Race when provisioning and connecting a device
([MEN-8164](https://northerntech.atlassian.net/browse/MEN-8164)) ([eae5bf2](https://github.com/mendersoftware/mender-server-enterprise/commit/eae5bf230060838f6b93d656ba19d68c609bb425))  by @alfrunes


  If a device gets provisioned and submits a connection request while the
  device is getting provisioned, the device might end up in an
  inconsistent state where the connection status gets overwritten to
  "unknown".
  The issue was discovered in a test where the system was under load
  and the device was running on the same network (artificially low RTT).
- Prevent demoting a service provider with children
([MEN-7841](https://northerntech.atlassian.net/browse/MEN-7841)) ([b342ada](https://github.com/mendersoftware/mender-server-enterprise/commit/b342adae3f343fcc4c82381732fbe33d91d318eb))  by @bahaa-ghazal
- Clear `auditlogs` when promoting a tenant to SP
([MEN-7787](https://northerntech.atlassian.net/browse/MEN-7787)) ([5ab72dc](https://github.com/mendersoftware/mender-server-enterprise/commit/5ab72dc60b6d3a0247c8774e13ff0a54dd8ea474))  by @bahaa-ghazal
- Stop deviceconnect's `/connect` endpoints from sending ping
([MEN-8061](https://northerntech.atlassian.net/browse/MEN-8061)) ([79a32a6](https://github.com/mendersoftware/mender-server-enterprise/commit/79a32a6f12fd1b90be3560a896e50d8d63516210))  by @bahaa-ghazal
- Generate delta worker aborting before artifact upload completes
([MEN-8177](https://northerntech.atlassian.net/browse/MEN-8177)) ([4901878](https://github.com/mendersoftware/mender-server-enterprise/commit/4901878b6eb41dd208ead2f55027b633749b2732))  by @alfrunes


  The artifact generator aborts uploading an artifact prematurely once
  either of the input files are processed and returns exit code 0. This
  results in a very confusing error where the API reports a successfully
  generated artifact, but the artifact is never fully uploaded and
  available through the APIs.
- Generate delta worker for custom S3 bucket
([MEN-8202](https://northerntech.atlassian.net/browse/MEN-8202)) ([0ac2923](https://github.com/mendersoftware/mender-server-enterprise/commit/0ac2923e0261a53a69f298b543e460143558c3e6))  by @alfrunes
- Skip IoT Core/IoT Hub integration if device is not yet provisioned
([MEN-8230](https://northerntech.atlassian.net/browse/MEN-8230)) ([eeffe42](https://github.com/mendersoftware/mender-server-enterprise/commit/eeffe42fd158956bb531c916639b84c93d6d4e63))  by @alfrunes


  If a device has not previously been provisioned, it is not part of the
  integration and should be excluded from the sync.




### Documentation


- Migrate deployments specs to OpenAPI 3.0
 ([4631b2f](https://github.com/mendersoftware/mender-server-enterprise/commit/4631b2fc3f16a53490089b273c708a0ffee3b345))  by @alfrunes
- Correct spelling errors and incorrect descriptions
 ([001407c](https://github.com/mendersoftware/mender-server-enterprise/commit/001407c4538f1cc7147c950ef73f27892c732476))  by @alfrunes
- Migrate deployments specs to OpenAPI 3 and align with open-source
 ([297b808](https://github.com/mendersoftware/mender-server-enterprise/commit/297b808bf43bfb04d6f17e7d5ec3405a5360aff8))  by @alfrunes




### Features


- *(gui)* Added year to timeframe picker
([MEN-8136](https://northerntech.atlassian.net/browse/MEN-8136)) ([48a5e98](https://github.com/mendersoftware/mender-server-enterprise/commit/48a5e98cdfc7793fac653f80d1dbe7ae6172956c))  by @mineralsfree

- *(gui)* Changed login form to a more stepwise approach in order to reduce confusion
([MEN-7761](https://northerntech.atlassian.net/browse/MEN-7761)) ([543bf7a](https://github.com/mendersoftware/mender-server-enterprise/commit/543bf7a7d0e6b2cd0badf20be9a9ecdb0ce2bc6c))  by @mzedel


  - this relies on an as of yet unreleased bugfix release of RHF
  Ticket: MEN-7761

- *(gui)* Made password forgotten flow more informative to reduce confusion
([MEN-7761](https://northerntech.atlassian.net/browse/MEN-7761)) ([ed81bc6](https://github.com/mendersoftware/mender-server-enterprise/commit/ed81bc69f2d809be0f95f060042c7762bd3855c6))  by @mzedel

- *(iot-manager)* Allowed disabling address verification during webhook configuration
 ([e05997c](https://github.com/mendersoftware/mender-server-enterprise/commit/e05997c7c7846c5fec9049a1b937461431687b3a))  by @mzedel

- *(iot-manager)* Added integration_id query parameter to API for getting events
([MEN-7801](https://northerntech.atlassian.net/browse/MEN-7801)) ([bc0dae3](https://github.com/mendersoftware/mender-server-enterprise/commit/bc0dae393ecf61edba3c71555248c2fef25cd2ac))  by @merlin-northern


  Allows to:
  * get device events from iot-manager by integration ID
  * maintains backward compatibility for GET /event
  * with UI calling the new endpoint this fixes the showing
    of events from old webhooks in the integraiton details

- Accept `null` to unset suspend and trial expiration date
([MEN-7727](https://northerntech.atlassian.net/browse/MEN-7727)) ([13046eb](https://github.com/mendersoftware/mender-server-enterprise/commit/13046ebdcb11607186f2a5e88b051e405ace9dc2))  by @bahaa-ghazal




### Refac


- *(gui)* Extraced login related form elements to isolate form handling
 ([0088e78](https://github.com/mendersoftware/mender-server-enterprise/commit/0088e78dac5aa9d8512809fb8a197428201e8a38))  by @mzedel







## 4.1.0-saas.2 - 2025-02-25


### Bug Fixes


- *(gui)* Let read-only user no longer think they could act on selected releases
([MEN-8110](https://northerntech.atlassian.net/browse/MEN-8110)) ([dd710a7](https://github.com/mendersoftware/mender-server-enterprise/commit/dd710a723b68c15f6d92b22e3ea81356e5e638c7))  by @mzedel

  also aligned component label + usage with reality

- *(gui)* Fixed pagination for pending deployments
([MEN-8140](https://northerntech.atlassian.net/browse/MEN-8140)) ([c3f406b](https://github.com/mendersoftware/mender-server-enterprise/commit/c3f406b1585756cc9d57638a549edb7e4b81093e))  by @mzedel

- *(gui)* Prevented a situation where one release upload could prevent another
([MEN-8125](https://northerntech.atlassian.net/browse/MEN-8125)) ([84b24ec](https://github.com/mendersoftware/mender-server-enterprise/commit/84b24ec1ae572731c44cdb5ab937de13c9cc0bcb))  by @mzedel

- *(gui)* Made rbac limitations visible in release tagging too
 ([c706020](https://github.com/mendersoftware/mender-server-enterprise/commit/c7060207dfe15eae736bcfd5b9d84f51b8f083a7))  by @mzedel

- *(gui)* Ensured release tag creation is waited for before changing UI
([MEN-8078](https://northerntech.atlassian.net/browse/MEN-8078)) ([9b0c722](https://github.com/mendersoftware/mender-server-enterprise/commit/9b0c7226f187a77a4831460dd48ea8bc2cba9ef2))  by @mzedel

- *(gui)* Fixed an issue with editing credit card when no billing address was provided
([MEN-8154](https://northerntech.atlassian.net/browse/MEN-8154)) ([0fd9658](https://github.com/mendersoftware/mender-server-enterprise/commit/0fd9658edee50b7db614eb45a83931db43518380))  by @mineralsfree





### Documentation


- *(deployments)* Fix spelling
 ([f2a8379](https://github.com/mendersoftware/mender-server-enterprise/commit/f2a8379bd770e465573123d3f892642dfcdbeb72))  by @vbpieter

- Add missing breaking changes to enterprise changelog
 ([794bd4d](https://github.com/mendersoftware/mender-server-enterprise/commit/794bd4dc7f970ec9b026b3fdcf78d75dc226b39b))  by @alfrunes
- Add missing breaking changes to changelog
 ([799f42d](https://github.com/mendersoftware/mender-server-enterprise/commit/799f42dad02145fedf80d1d6e29bb5239536f7de))  by @alfrunes




### Features


- *(gui)* Split release deployment onboarding step in 2 steps
([MEN-7882](https://northerntech.atlassian.net/browse/MEN-7882)) ([3fc2e9a](https://github.com/mendersoftware/mender-server-enterprise/commit/3fc2e9a61fe128b52b73ad24de356cfb59a658bd))  by @mineralsfree

- *(gui)* Made ui improvements to the deployment onboarding flow
([MEN-7882](https://northerntech.atlassian.net/browse/MEN-7882)) ([35d0f11](https://github.com/mendersoftware/mender-server-enterprise/commit/35d0f116319efa79d24edc64957d3f0f6552e16c))  by @mineralsfree

- *(gui)* Made onboard action tooltip rely on position of action item
([MEN-7882](https://northerntech.atlassian.net/browse/MEN-7882)) ([dfeb0d6](https://github.com/mendersoftware/mender-server-enterprise/commit/dfeb0d6e574d2192b59bfe4918645d1d07d61960))  by @mineralsfree

- *(gui)* Made device issue selection on devices page available for more plans
([MEN-8076](https://northerntech.atlassian.net/browse/MEN-8076)) ([d7d2f97](https://github.com/mendersoftware/mender-server-enterprise/commit/d7d2f976518ef822d103834e0eb1816f0fcdb01b))  by @mzedel

- *(gui)* Made device tag confirmation message align with change
 ([3374b93](https://github.com/mendersoftware/mender-server-enterprise/commit/3374b93c9d899d68a7563171ec1645c2987b7b92))  by @mzedel

- *(gui)* Unified dialog backdrop and esc closing behaviour
([MEN-7998](https://northerntech.atlassian.net/browse/MEN-7998)) ([8b78680](https://github.com/mendersoftware/mender-server-enterprise/commit/8b786806a390feda0281de233acf6639bc61a8a1))  by @mineralsfree

- Implementing internal `Tenantadm` api to remove parent reference from tenant
([MEN-8097](https://northerntech.atlassian.net/browse/MEN-8097)) ([63ac8bd](https://github.com/mendersoftware/mender-server-enterprise/commit/63ac8bd40d79a32c97e6b89436a39f74963d36a1))  by @bahaa-ghazal






## 4.1.0-saas.1 - 2025-02-20


### Bug Fixes


- *(gui)* Fixed date parsing & formatting issues after dayjs migation
([95dd540](https://github.com/mendersoftware/mender-server-enterprise/commit/95dd5400cc14888ae965feeba48c21bef7e4b901))  by @mzedel

- *(gui)* Fixed an issue that would prevent showing phased deployments
([1e73ba7](https://github.com/mendersoftware/mender-server-enterprise/commit/1e73ba734acbb33f2432d0b209a4baafd669651d))  by @mzedel

- Fix(gui): ensured deployment phase information stays inside its boundaries
([MEN-7995](https://northerntech.atlassian.net/browse/MEN-7995)) ([87fe82d](https://github.com/mendersoftware/mender-server-enterprise/commit/87fe82d7467cdcaf95397f0e37889167456f105b))  by @mzedel

- Fix(gui): fixed an issue that prevented upload progress from being shown
  aligning upload progress tracking with updated payload structure after rtk migration
([MEN-8074](https://northerntech.atlassian.net/browse/MEN-8074)) ([1b715c8](https://github.com/mendersoftware/mender-server-enterprise/commit/1b715c82aa75e016a681038459bfadb6f3ae89cd))  by @mzedel




### Features


- Count devices deviceauth command line and workflow
([MEN-8058](https://northerntech.atlassian.net/browse/MEN-8058)) ([7128716](https://github.com/mendersoftware/mender-server-enterprise/commit/7128716912a562e28e52f1638ee6224273bb0dc5))  by @merlin-northern






## 4.1.0-saas - 2025-02-13


### Bug Fixes


- *(gui)* Made user list tracking rely only on backend data instead of local store to prevent duplicate users listed
([MEN-8049](https://northerntech.atlassian.net/browse/MEN-8049)) ([7d1b060](https://github.com/mendersoftware/mender-server-enterprise/commit/7d1b060d096ff2549305cc0f453d8a35b21257b0))  by @mzedel

- *(gui)* Fixed an issue that would cause the ui to crash when creating phased deployments
 ([9827ba9](https://github.com/mendersoftware/mender-server-enterprise/commit/9827ba928889f52e7eb4216b68707386c082dc74))  by @mzedel

- *(gui)* Fixed remaining device percentage not being displayed correctly on phased deployment creation
 ([5600913](https://github.com/mendersoftware/mender-server-enterprise/commit/560091349c778c288ad1bdc5a8bcd9b54c39f399))  by @mzedel

- Update outdated api endpoints in the `inventory` service
([MEN-7017](https://northerntech.atlassian.net/browse/MEN-7017)) ([73c7149](https://github.com/mendersoftware/mender-server-enterprise/commit/73c714951a61642b2fc100214c61e5f66c27ee0c))  by @bahaa-ghazal
- Limiting the size of metadata when uploading and generating artifacts
([MEN-7166](https://northerntech.atlassian.net/browse/MEN-7166)) ([9e80728](https://github.com/mendersoftware/mender-server-enterprise/commit/9e8072874c94da9e7a3659207e08c6a05fc48cc4))  by @bahaa-ghazal




### Documentation


- *(deployments)* Clarifications for the GET /deployments version 2 endpoint.
([MEN-8053](https://northerntech.atlassian.net/browse/MEN-8053)) ([0231b1b](https://github.com/mendersoftware/mender-server-enterprise/commit/0231b1b1786a7c341d0b56544e17e952c4bd5059))  by @merlin-northern

- *(inventory)* Describe inventory webhook events.
([MEN-8041](https://northerntech.atlassian.net/browse/MEN-8041)) ([66df3f5](https://github.com/mendersoftware/mender-server-enterprise/commit/66df3f5532e8743176365c992f74afa2781bbf15))  by @merlin-northern





### Features


- *(gui)* Clarified user creation capabilities for non-enterprise users
([MEN-7883](https://northerntech.atlassian.net/browse/MEN-7883)) ([d2fd192](https://github.com/mendersoftware/mender-server-enterprise/commit/d2fd192e8c09443dabb694288d73636853b02d86))  by @mzedel

- *(gui)* Added automatic refresh to get webhook events
([MEN-8045](https://northerntech.atlassian.net/browse/MEN-8045)) ([502e06a](https://github.com/mendersoftware/mender-server-enterprise/commit/502e06aab96f3ce980cd6fe197a2fd6d7e99233a))  by @mzedel







## 4.0.0-rc.9 - 2025-01-30


### Bug Fixes


- *(gui)* Ensured target directory is nonempty on artifact generation
([MEN-8010](https://northerntech.atlassian.net/browse/MEN-8010)) ([5616722](https://github.com/mendersoftware/mender-server-enterprise/commit/561672221f31d0be257c4e1da98c63eda40f792d))  by @mzedel

- *(gui)* Fixed an issue that could prevent listing devices with their custom identity in a deployment report
 ([f1fcf26](https://github.com/mendersoftware/mender-server-enterprise/commit/f1fcf26f33a3ae458e60f994fed60231d75abd5c))  by @mzedel

- *(gui)* Fixed an issue that would prevent navigating to devices from a software distribution chart
([MEN-8038](https://northerntech.atlassian.net/browse/MEN-8038)) ([6516986](https://github.com/mendersoftware/mender-server-enterprise/commit/6516986b82ce08ecdfd9ed3c790590796c60da2d))  by @mzedel

- *(useradm)* Resolve user ID to email on AssignUserToTenants.
([MEN-8004](https://northerntech.atlassian.net/browse/MEN-8004)) ([b7229df](https://github.com/mendersoftware/mender-server-enterprise/commit/b7229df43e563cd6fed0ddaab074fb4cae1cb4fd))  by @merlin-northern

- Grant `Read` role premission to download audit log
([MEN-7869](https://northerntech.atlassian.net/browse/MEN-7869)) ([0aee905](https://github.com/mendersoftware/mender-server-enterprise/commit/0aee905cd5bf48b5951ad8143852d648705d8b80))  by @bahaa-ghazal




### Features


- *(gui)* Added explanation about integration number limitation
([MEN-7899](https://northerntech.atlassian.net/browse/MEN-7899)) ([dbdfa67](https://github.com/mendersoftware/mender-server-enterprise/commit/dbdfa672a62eb30745fb4b0e73bea7d345644932))  by @mzedel





### Build


- *(make)* Add enterprise version build id
 ([d115b84](https://github.com/mendersoftware/mender-server-enterprise/commit/d115b848f436aa119f29ad79b8cd7e86b90c8666))  by @alfrunes


  Updates the linked version symbol to contain a suffix `+enterprise`.







## 4.0.0-rc.8 - 2025-01-27


### Bug Fixes


- *(gui)* Aligned webhook details behaviour w/ rest of UI
([MEN-7955](https://northerntech.atlassian.net/browse/MEN-7955)) ([7860b5b](https://github.com/mendersoftware/mender-server-enterprise/commit/7860b5b40c698b580f5a299ee8c9206490ea5710))  by @mzedel

- *(gui)* Prevented sso config retrieval on plans that don't support this
 ([fe6da5d](https://github.com/mendersoftware/mender-server-enterprise/commit/fe6da5dbea68222226ab01f52df7e5975fedc09d))  by @mzedel

- *(gui)* Fixed an issue that would prevent deleting & tagging releases in the release overview
([MEN-7960](https://northerntech.atlassian.net/browse/MEN-7960)) ([16b2628](https://github.com/mendersoftware/mender-server-enterprise/commit/16b2628feaf39eba631b5ab013bf3eeecfa95217))  by @mzedel

- *(gui)* Let on-prem installations refer to the docs to prevent server-url misconfiguration following monorepo transition
([MEN-7948](https://northerntech.atlassian.net/browse/MEN-7948)) ([e0dae51](https://github.com/mendersoftware/mender-server-enterprise/commit/e0dae512f67f08f312a61bd3be8192b7bbb7d6db))  by @mzedel

- *(gui)* Fixed end date filters out today's entries in the Audit log, Deployments and Devices
 ([3ee84f2](https://github.com/mendersoftware/mender-server-enterprise/commit/3ee84f2d743b51462f72e68efeae870a51c4d12c))  by @aleksandrychev

- *(iot-manager)* Filter integrations by event scope
([MEN-7956](https://northerntech.atlassian.net/browse/MEN-7956)) ([08f062d](https://github.com/mendersoftware/mender-server-enterprise/commit/08f062db0f1b033bd4cae2052e7b7335e8d56df3))  by @kjaskiewiczz


  Decommission and provision device events and device status change
  event should be sent to integrations containing deviceauth scope.

- *(tenantadm)* It should not be possible to make tenant without device limit a Service Provider tenant
([MEN-7954](https://northerntech.atlassian.net/browse/MEN-7954)) ([f144db6](https://github.com/mendersoftware/mender-server-enterprise/commit/f144db677152250baa47ebede394fe8f85ee7d52))  by @kjaskiewiczz

- Deviceauth healthcheck panics malformed inventory address
 ([70d493a](https://github.com/mendersoftware/mender-server-enterprise/commit/70d493a6913827d893758cd481a535de67fbeff9))  by @alfrunes
- Use internal URLs for storage backend when generating artifacts
([MEN-7939](https://northerntech.atlassian.net/browse/MEN-7939)) ([3d72d5e](https://github.com/mendersoftware/mender-server-enterprise/commit/3d72d5e5b0294a3dcf3faa4413104ef27f95ba19))  by @alfrunes
  - **BREAKING**: Generate artifacts API ignores `storage.proxy_uri` and
`aws.external_url` configuration values and instead access the API using
the same URL as deployments service.


  When generating artifacts, the backend will use the direct access URL
  instead of rewriting the URL using the configured `storage.proxy_uri` or
  `aws.external_url`.
- Use internal URLs for storage backend when generating delta artifacts
([MEN-7939](https://northerntech.atlassian.net/browse/MEN-7939)) ([29eed8a](https://github.com/mendersoftware/mender-server-enterprise/commit/29eed8a37aba778309aca862135f13069abc1151))  by @alfrunes
  - **BREAKING**: Generating delta artifacts ignores `storage.proxy_uri`
and `aws.external_url` configuration values and instead access the API
using the same URL as deployments service.


  When generating delta artifacts, the backend will use the direct access
  URLs instead of rewriting the URL using the configured
  `storage.proxy_uri` or `aws.external_url`.
- Deployment device count should not exceed max devices
([MEN-7847](https://northerntech.atlassian.net/browse/MEN-7847)) ([15e5fee](https://github.com/mendersoftware/mender-server-enterprise/commit/15e5feec727e4257a1ee4345265146a194edb4ab))  by @alfrunes


  Added a condition to skip deployments when the device count reaches max
  devices.
- Segmentation fault for `create-org` CLI timeouts
 ([6054f85](https://github.com/mendersoftware/mender-server-enterprise/commit/6054f855a32e45b3d08f6f06fb15965e1a772b03))  by @alfrunes


  If the service times out waiting for a workflows to complete, the app
  can incorrectly return no error and a nil tenant object.
  This commit simplifies the polling loop and ensures that en error is
  always returned after timeouts.
- Align the tenantadm API with the documentation
([MEN-7986](https://northerntech.atlassian.net/browse/MEN-7986)) ([57a538c](https://github.com/mendersoftware/mender-server-enterprise/commit/57a538cda76a43b93d5a4a5bb191e63a42f40972))  by @alfrunes


  The v1 APIs are retrieving undocumented attributes from other backend
  services (deployments and deviceauth). As a side effect, the internal
  user authentication middleware is fetching this data on every request
  to the management APIs only to discard the information.




### Documentation


- Fix typo in snippet for creating tenant
 ([a346d33](https://github.com/mendersoftware/mender-server-enterprise/commit/a346d33781086d157d831478cfb64bebeef6c3bd))  by @alfrunes
- Docmentation on backend integration tests running separately
([QA-683](https://northerntech.atlassian.net/browse/QA-683)) ([a8f8d54](https://github.com/mendersoftware/mender-server-enterprise/commit/a8f8d545573100186fba953c7179592a23196b23))  by @merlin-northern
- Add missing API parameters to the documentation
 ([7f68520](https://github.com/mendersoftware/mender-server-enterprise/commit/7f68520e8dd4c102b78735b68c0bdbfb986685c7))  by @alfrunes




### Features


- *(gui)* Added feedback on file size limits to artifact upload dialog
([MEN-7858](https://northerntech.atlassian.net/browse/MEN-7858)) ([d612334](https://github.com/mendersoftware/mender-server-enterprise/commit/d612334ebfae6b1a3d416016ee500b89daa70804))  by @mzedel

- *(gui)* Aligned text input appearance with MUI updated guidelines
([MEN-7838](https://northerntech.atlassian.net/browse/MEN-7838)) ([e5d5672](https://github.com/mendersoftware/mender-server-enterprise/commit/e5d56720b901a451fa47a514424f710763b50291))  by @mzedel





### Performance


- Only count tenants when required
 ([55e953b](https://github.com/mendersoftware/mender-server-enterprise/commit/55e953b3b9112fadd04abe3bfe350afd27b23042))  by @alfrunes


  In most instances the tenant count is discarded.




### Refac


- Move compat tests to dedicated test suite
 ([059f437](https://github.com/mendersoftware/mender-server-enterprise/commit/059f4375d3b33073e711fdbf81212a2cd5dacfbb))  by @alfrunes
- Share path for upserting next deployment for a device
 ([5b863c9](https://github.com/mendersoftware/mender-server-enterprise/commit/5b863c951945528f090b55694d1d18c707940bfa))  by @alfrunes


  Makes conflict resolution with open source easier to manage.





