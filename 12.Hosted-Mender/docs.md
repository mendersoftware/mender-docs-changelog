---
title: Hosted Mender
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## v4.1.0-saas.21 - 2025-11-27


### Bug fixes


- *(tenantadm)* Fix default device limits for enterprise plan
([MEN-9049](https://northerntech.atlassian.net/browse/MEN-9049)) ([e83f368](https://github.com///commit/e83f368fd657e2b9a87b472c68978544130385ec)) 


  There is no support for `-1` as device limit in the UI yet, so we should
  use 0 (which means no limit, same as -1) as a default limit for standard
  devices.
 
- *(deployments)* Replace counters with queues to solve consistency errors
([MEN-7704](https://northerntech.atlassian.net/browse/MEN-7704)) ([3d65fa2](https://github.com///commit/3d65fa2985b3c66f4b178ce9106d9e27856487a6)) 


  There are a number of race conditions and errors that could lead to
  permanent errors in the counters. By replacing the counters with queues,
  we should be able to resolve inconsistencies by handling stale jobs
  reliably.

- *(deployments)* Add staleness check to delta jobs for checkUpdate
 ([7fdb493](https://github.com///commit/7fdb493cfdb7105a178c0b21e9aa2bd6ac6de421)) 

- *(deployments)* Try to schedule stale jobs when jobs finish
 ([9bf0ce2](https://github.com///commit/9bf0ce2bc41f5aa9938e5b69f1a8fc33579786cb)) 

- *(deployments)* Remove delta job TTL to prevent disappearing status
([MEN-8981](https://northerntech.atlassian.net/browse/MEN-8981)) ([bc4c823](https://github.com///commit/bc4c8231eb926e73540096669606e7fd7256348a)) 

- *(gui)* Fixed pagination in device search results
([MEN-8196](https://northerntech.atlassian.net/browse/MEN-8196)) ([62c4de2](https://github.com///commit/62c4de2b2a73c22bac716a368e6b70701fa5b652)) 

- *(useradm)* Handle tenant not found in login endpoints
 ([cc35fac](https://github.com///commit/cc35fac4a77bd74bff1e84667c11b5d6ec9c1156)) 

- *(useradm)* Migration ensuring unique read-only SSO configuration
([MEN-8938](https://northerntech.atlassian.net/browse/MEN-8938)) ([1f59cd3](https://github.com///commit/1f59cd32ff17699016cee00056fa87c84d5a6e6c)) 


  The migration builds on top of 2416a39b6610183c712a11b9b5918e0d0069ac22
  ensuring that tenants that inherit SSO configuration cannot create a new
  SSO configuration.

- Introduce docker-compose healthcheck for mongo, nats and traefik
 ([e3aea0b](https://github.com///commit/e3aea0bd890ac71c18ba08be9e80dd59b4ad3da5)) 


  Introducing healthcheck allow to monitor services.
  This permits a better dependency when mender services are starting,
  waiting for mongo, nats, traefik to be heatlhy before starting.
- Increase docker-compose restart
 ([d687f66](https://github.com///commit/d687f664183da924d5be642c6ced14ebe0e5dfd5)) 


  Some services still fails after the introduction of the healthcheck on
  slow machines. Increase the number restarts allowed to solve it, no
  better mechanisms found.
- Service provider children properly inherits sso configuration
 ([1f1d731](https://github.com///commit/1f1d731efff47e958455ecbeac6c5b422b4574e2)) 


  By setting the `source_tenant_id` parameter when creating a new tenant
  from a service provider, makes the created tenant properly inherit the
  SSO configuration from the parent. The SSO configuration can only be
  modified by the service provider, rendering the
  `restrict_to_parent_tenant` parameter practically always `true`.




### Documentation


- *(deployments)* Add artifact_too_big device deployment status
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([da06093](https://github.com///commit/da0609333b510e508047e330207e9b9c4c552c13)) 

- *(useradm)* Update documentation for creating tenant
([MEN-8938](https://northerntech.atlassian.net/browse/MEN-8938)) ([cb94161](https://github.com///commit/cb941619696a6fdd1de32145fb425a57035d1aca)) 


  Removed ineffective `restrict_to_parent_sso` parameter and updated the
  description for `sso`.

- Add documentation that `retries` is restricted to professional and enterprise plans
 ([02e404a](https://github.com///commit/02e404a7e1754c02450bf762ef268d69b9ca52a2)) 




### Features


- *(deployments)* Limit max deployment artifact size for micro devices
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([54a4f0d](https://github.com///commit/54a4f0da572e0499a8f62cdc693e7877b1afa471)) 

- *(deployments)* Rate limit new device deployments globally
([MEN-8943](https://northerntech.atlassian.net/browse/MEN-8943)) ([4a5f1f2](https://github.com///commit/4a5f1f27a4d318099cf74f69342783d6852de5fd)) 

- *(deviceauth)* Internal endpoints for device limits
([MEN-8904](https://northerntech.atlassian.net/browse/MEN-8904)) ([66f2a77](https://github.com///commit/66f2a778b8793bd9eb3855b14902fee76a099756)) 


  Support for all device tiers for set, get, delete operations.

- *(deviceauth)* Adjusted rate limits to account for device tier
 ([6e6c73f](https://github.com///commit/6e6c73f18ee750444864f20167030868abb7b847)) 


  The new device tier for standard devices are:
   - 15 requests/minute for checkUpdate
   - 15 requests/minute for submitInventory
   - 30 requests/minute for all other operations
  
   For micro device tier the ratelimits are:
   - 1 request/day for checkUpdate
   - 1 requests/14days for submitInventory
   - 30 requests/day for all other operations

- *(pkg)* Added request content length to access logs
([MEN-8935](https://northerntech.atlassian.net/browse/MEN-8935)) ([137da33](https://github.com///commit/137da33ab3056aa80eca0dc4226dddd24b84e7bc)) 

- *(tenantadm)* Device tier limits support for create_organization workflow
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([00996c8](https://github.com///commit/00996c8a8e385fd9bca7763aa82e88cccc994c7c)) 

- *(useradm)* Send audit email to all admin on SSO configuration change
([MEN-8971](https://northerntech.atlassian.net/browse/MEN-8971)) ([fc6be43](https://github.com///commit/fc6be43363ca8300fd541a50c2bd6ef694871fee)) 


  When a user updates the single sign-on configuration for their account,
  a security notification is sent to all admin user emails.

- *(workflows)* Add device tier limits to create_organization workflows
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([fd4d469](https://github.com///commit/fd4d469e9f896e6f90a95da47862000b6dbabb29)) 

- New flag `--tenant-token` for `create-org` CLI command
([MEN-7901](https://northerntech.atlassian.net/browse/MEN-7901)) ([5df75ff](https://github.com///commit/5df75ff970d27326d7507402e233af61262463d4)) 


  The new flag sets the tenant-token to a given string.
  Primarily useful in tests.
- Update traefik version
 ([106f570](https://github.com///commit/106f570bc67613071f276bb69dad42ba47d83d07)) 


  Update of traefik version to support Docker 29.x with API >= 1.44.




### Refactor


- *(tenantadm)* Make trial filter parameter explicitly bool
 ([6ddb347](https://github.com///commit/6ddb34756faab816c286b5354c1807adfb7d821d)) 

- *(tenantadm)* Add Stripe status filter to list subscriptions
 ([e835f1c](https://github.com///commit/e835f1c33ba87eb1b32bae3a25ea3ab9ba9d61ed)) 

- *(useradm)* Consolidate SSO metadata API handlers
 ([2bf2446](https://github.com///commit/2bf2446972716708c45410cfa42f5f5279718677)) 





### Security


- Bump the backend-docker-dependencies group across 10 directories with 2 updates
 ([26854ec](https://github.com///commit/26854ec71cfb181948696f1bbb0d5505114306c9)) 


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
  
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `alpine` from 3.22.1 to 3.22.2
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  Updates `golang` from 1.25.0 to 1.25.3
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: alpine
    dependency-version: 3.22.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.25.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 17 updates
 ([2cae646](https://github.com///commit/2cae6466e34d2928760bcb6a55df3f351b63d33b)) 


  Bumps the backend-tests-python-dependencies group with 17 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [attrs](https://github.com/sponsors/hynek) | `25.3.0` | `25.4.0` |
  | [boto3](https://github.com/boto/boto3) | `1.40.24` | `1.40.58` |
  | [certifi](https://github.com/certifi/python-certifi) | `2025.8.3` | `2025.10.5` |
  | [cffi](https://github.com/python-cffi/cffi) | `1.17.1` | `2.0.0` |
  | [cryptography](https://github.com/pyca/cryptography) | `45.0.7` | `46.0.3` |
  | [filelock](https://github.com/tox-dev/py-filelock) | `3.19.1` | `3.20.0` |
  | [idna](https://github.com/kjd/idna) | `3.10` | `3.11` |
  | [iniconfig](https://github.com/pytest-dev/iniconfig) | `2.1.0` | `2.3.0` |
  | [kubernetes](https://github.com/kubernetes-client/python) | `33.1.0` | `34.1.0` |
  | [pillow](https://github.com/python-pillow/Pillow) | `11.3.0` | `12.0.0` |
  | [pycparser](https://github.com/eliben/pycparser) | `2.22` | `2.23` |
  | [pymongo](https://github.com/mongodb/mongo-python-driver) | `4.14.1` | `4.15.3` |
  | [pyparsing](https://github.com/pyparsing/pyparsing) | `3.2.3` | `3.2.5` |
  | [pyyaml](https://github.com/yaml/pyyaml) | `6.0.2` | `6.0.3` |
  | [stripe](https://github.com/stripe/stripe-python) | `12.5.0` | `13.0.1` |
  | [redis](https://github.com/redis/redis-py) | `6.4.0` | `7.0.0` |
  | [pydantic](https://github.com/pydantic/pydantic) | `2.11.7` | `2.12.3` |
  
  
  
  Updates `attrs` from 25.3.0 to 25.4.0
  - [Commits](https://github.com/sponsors/hynek/commits)
  
  Updates `boto3` from 1.40.24 to 1.40.58
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.24...1.40.58)
  
  Updates `certifi` from 2025.8.3 to 2025.10.5
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.08.03...2025.10.05)
  
  Updates `cffi` from 1.17.1 to 2.0.0
  - [Release notes](https://github.com/python-cffi/cffi/releases)
  - [Commits](https://github.com/python-cffi/cffi/compare/v1.17.1...v2.0.0)
  
  Updates `cryptography` from 45.0.7 to 46.0.3
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/45.0.7...46.0.3)
  
  Updates `filelock` from 3.19.1 to 3.20.0
  - [Release notes](https://github.com/tox-dev/py-filelock/releases)
  - [Changelog](https://github.com/tox-dev/filelock/blob/main/docs/changelog.rst)
  - [Commits](https://github.com/tox-dev/py-filelock/compare/3.19.1...3.20.0)
  
  Updates `idna` from 3.10 to 3.11
  - [Release notes](https://github.com/kjd/idna/releases)
  - [Changelog](https://github.com/kjd/idna/blob/master/HISTORY.rst)
  - [Commits](https://github.com/kjd/idna/compare/v3.10...v3.11)
  
  Updates `iniconfig` from 2.1.0 to 2.3.0
  - [Release notes](https://github.com/pytest-dev/iniconfig/releases)
  - [Changelog](https://github.com/pytest-dev/iniconfig/blob/main/CHANGELOG)
  - [Commits](https://github.com/pytest-dev/iniconfig/compare/v2.1.0...v2.3.0)
  
  Updates `kubernetes` from 33.1.0 to 34.1.0
  - [Release notes](https://github.com/kubernetes-client/python/releases)
  - [Changelog](https://github.com/kubernetes-client/python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/kubernetes-client/python/compare/v33.1.0...v34.1.0)
  
  Updates `pillow` from 11.3.0 to 12.0.0
  - [Release notes](https://github.com/python-pillow/Pillow/releases)
  - [Changelog](https://github.com/python-pillow/Pillow/blob/main/CHANGES.rst)
  - [Commits](https://github.com/python-pillow/Pillow/compare/11.3.0...12.0.0)
  
  Updates `pycparser` from 2.22 to 2.23
  - [Release notes](https://github.com/eliben/pycparser/releases)
  - [Changelog](https://github.com/eliben/pycparser/blob/main/CHANGES)
  - [Commits](https://github.com/eliben/pycparser/compare/release_v2.22...release_v2.23)
  
  Updates `pymongo` from 4.14.1 to 4.15.3
  - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
  - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
  - [Commits](https://github.com/mongodb/mongo-python-driver/compare/4.14.1...4.15.3)
  
  Updates `pyparsing` from 3.2.3 to 3.2.5
  - [Release notes](https://github.com/pyparsing/pyparsing/releases)
  - [Changelog](https://github.com/pyparsing/pyparsing/blob/master/CHANGES)
  - [Commits](https://github.com/pyparsing/pyparsing/compare/3.2.3...3.2.5)
  
  Updates `pyyaml` from 6.0.2 to 6.0.3
  - [Release notes](https://github.com/yaml/pyyaml/releases)
  - [Changelog](https://github.com/yaml/pyyaml/blob/6.0.3/CHANGES)
  - [Commits](https://github.com/yaml/pyyaml/compare/6.0.2...6.0.3)
  
  Updates `stripe` from 12.5.0 to 13.0.1
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v12.5.0...v13.0.1)
  
  Updates `redis` from 6.4.0 to 7.0.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v6.4.0...v7.0.0)
  
  Updates `pydantic` from 2.11.7 to 2.12.3
  - [Release notes](https://github.com/pydantic/pydantic/releases)
  - [Changelog](https://github.com/pydantic/pydantic/blob/main/HISTORY.md)
  - [Commits](https://github.com/pydantic/pydantic/compare/v2.11.7...v2.12.3)
  
  ---
  updated-dependencies:
  - dependency-name: attrs
    dependency-version: 25.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.58
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.10.5
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cffi
    dependency-version: 2.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 46.0.3
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: filelock
    dependency-version: 3.20.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: idna
    dependency-version: '3.11'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: iniconfig
    dependency-version: 2.3.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: kubernetes
    dependency-version: 34.1.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pillow
    dependency-version: 12.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pycparser
    dependency-version: '2.23'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.15.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pyparsing
    dependency-version: 3.2.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pyyaml
    dependency-version: 6.0.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 13.0.1
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 7.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pydantic
    dependency-version: 2.12.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...
- Bump js-yaml from 4.1.0 to 4.1.1 in /frontend
 ([b0b6165](https://github.com///commit/b0b6165551dce4310f78b63d6081ca0ae35f8d5f)) 


  Bumps [js-yaml](https://github.com/nodeca/js-yaml) from 4.1.0 to 4.1.1.
  - [Changelog](https://github.com/nodeca/js-yaml/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/nodeca/js-yaml/compare/4.1.0...4.1.1)
  
  ---
  updated-dependencies:
  - dependency-name: js-yaml
    dependency-version: 4.1.1
    dependency-type: indirect
  ...
- Bump golang.org/x/crypto from 0.43.0 to 0.45.0 in /backend
 ([8981e10](https://github.com///commit/8981e10742a4e097df46534fe5c314bc11ea2de7)) 


  Bumps [golang.org/x/crypto](https://github.com/golang/crypto) from 0.43.0 to 0.45.0.
  - [Commits](https://github.com/golang/crypto/compare/v0.43.0...v0.45.0)
  
  ---
  updated-dependencies:
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.45.0
    dependency-type: direct:production
  ...





## v4.1.0-saas.17 - 2025-11-03


### Bug fixes


- *(deployments)* Backwards compatible artifact metadata
 ([8110c52](https://github.com///commit/8110c5251b1025bc00a9b7c56e42500715c477d0)) 

- *(deployments)* Panic on database errors on DELETE /artifacts
 ([f3c9bda](https://github.com///commit/f3c9bda8eb050ceb744f0ce7f45c58c44934c861)) 

- *(deviceconnect)* SetReadDeadline when setting up ping handler
([MEN-8843](https://northerntech.atlassian.net/browse/MEN-8843)) ([b10a3a8](https://github.com///commit/b10a3a8dd0b1b4c85c6b33184b9f9ed6b5fa8b86)) 

- *(gui)* Fixed an issue that left notch in outlined w/o a background
 ([1673cff](https://github.com///commit/1673cff934be78a379d9123f93317336ee83bfe0)) 

- *(gui)* Removed error messages shown when subscribing or showing billing info as trial user
 ([231d4e3](https://github.com///commit/231d4e34a0d376a2b963e4e01a4a393a975f2668)) 


  - NB: this lets the frontend rely on trial signups to always provide a new billing profile when signing up

- *(gui)* Fixed an issue that prevented updating existing sso configs
 ([d022d1a](https://github.com///commit/d022d1a78ba2f2b60cc1670b0015451c01c5734e)) 

- *(gui)* Limited chances a set deployment device limit gets changed unintended
 ([1f12d38](https://github.com///commit/1f12d38249ac4bba72bbbc7ebb92ffdcf4fe9b09)) 

- *(gui)* Fixed an issue that could prevent the billing overview from working
 ([4d1f0f3](https://github.com///commit/4d1f0f3f41ece22b75310d76f2015ff7576f4a8c)) 

- *(gui)* Increased reliance on theme defined button colors to align more w/ updated theme
 ([28cd0fd](https://github.com///commit/28cd0fd1a2e5c976d16769a25daff75125748035)) 





### Documentation


- *(deployments)* Mark release meta_data as deprecated
 ([33563c6](https://github.com///commit/33563c6ac639c4fdba1471eb0c1e65e66e2e4f80)) 

- *(deployments)* Use array type for deprecated meta_data attribute
 ([0135305](https://github.com///commit/0135305d78d95038ff7c3bfadcdd8d34d7a8a8df)) 

- *(deployments)* Document 'sort' option in the internal endpoint for getting deployments
([MEN-8914](https://northerntech.atlassian.net/browse/MEN-8914)) ([7165f58](https://github.com///commit/7165f58eec679b36e0a83f5a4d4b71595c62aa30)) 

- *(deployments)* Aligned update meta_data example with schema definition
 ([bf16c73](https://github.com///commit/bf16c73192800aae538348d752f824b3771e7db1)) 

- *(deployments)* Aligned artifact_too_big schema w/ rest of docs
 ([db35fca](https://github.com///commit/db35fca1333e3f4e8305dc9d554c5339333ed2e3)) 

- *(useradm)* Fixed an issue that prevented generating a user information response example
 ([79650ca](https://github.com///commit/79650ca4a1f4aac8ea6a1b7a39776c1a61cc3756)) 


  - the schema types in the allOf need to be the same for this to apply

- Aligned more error responses w/ existing shared response definitions
 ([d5596d5](https://github.com///commit/d5596d572c1a0621e87b973549fc86d4542d5b69)) 
- Aligned unauthorized errors definitions w/ shared definition
 ([9d26fd7](https://github.com///commit/9d26fd700a572600bba631291102eb1dc34baba3)) 




### Features


- *(gui)* Ensured progress gets updated when monitoring a delta generation job
 ([7487d8f](https://github.com///commit/7487d8f0dc6b921ede11ddac6ab3bae392a1ffff)) 

- *(tenantadm)* Configure default device limits for tiers in plans
([MEN-8905](https://northerntech.atlassian.net/browse/MEN-8905)) ([2af153d](https://github.com///commit/2af153dc98b44d72fc2b578084ca6fdfa811400b)) 

- *(tenantadm)* Set limits for all tiers when creating organization
([MEN-8905](https://northerntech.atlassian.net/browse/MEN-8905)) ([7d4d760](https://github.com///commit/7d4d760a37c584b64716d04a79a3cf43873d78cc)) 

- *(tenantadm)* Override device tier limits in create organization cli
([MEN-8905](https://northerntech.atlassian.net/browse/MEN-8905)) ([fe60c4b](https://github.com///commit/fe60c4b5f952024f6d8dc430de572f947c6d4a44)) 

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([64ca71f](https://github.com///commit/64ca71f162901bb4dce096f14da416a23495dfbc)) 


  Added the following configuration parameters:
  ```yaml
  rate_limits:
    # auth configures rate limits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # reject_unmatched rejects requests that does not resolve to a
      # rate limit group. That is, if either there's no api_pattern matching
      # the request or if the group_expression does not match a group.
      # Defaults to false - disable rate limiting for unmatched requests.
      reject_unmatched: false
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups:
          # name defines the name of the group. The name is used in
          # match.group_expression to match an api_pattern with a group.
        - name: default
          # interval is the time interval when the rate limiter resets.
          interval: 1m
          # quota is the number of requests allowed in an interval.
          quota: 300
          # event_expression is a go template for grouping requests.
          # The following attributes are available in the context:
          # Identity - contains a subset of the JWT claims:
          # .Subject  (jwt:"sub")          string
          # .Tenant   (jwt:"mender.tenant") string
          # .Plan     (jwt:"mender.plan")   string
          # .Addons   (jwt:"mender.addons") []struct{Enabled bool; Name string}
          # .IsUser   (jwt:"mender.user")   bool
          # .IsDevice (jwt:"mender.device") bool
          # .Trial    (jwt:"mender.trial")  bool
          event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
      match:
          # api_pattern specifies an API path pattern as defined by http.ServeMux
          # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
        - api_pattern: /
          # group_expression defines  the group for this matching expression.
          # A group can be selected dynamically using Go templates or statically
          # with a literal string.
          # See group.event_expression for template context attributes.
          group_expression: "default"
          # More example match rules:
  ```





### Refactor


- *(gui)* Refactored subscription form to be a RHF form & reduce faulty billing calls
 ([5938972](https://github.com///commit/59389724fd85802e50dc6ce951814a5d8d4beeb0)) 

- *(gui)* Let email check be done in thunk to align msw handler location
 ([eaae614](https://github.com///commit/eaae614b8ae7b9b4ed46a9f5fd630ff54e8c746e)) 





### Security


- Bump @playwright/test
 ([28a4805](https://github.com///commit/28a48056a49a56847807b947dec81661d1f29dee)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.55.1 to 1.56.1
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.55.1...v1.56.1)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.56.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump validator from 13.15.15 to 13.15.20 in /frontend
 ([94a0d8a](https://github.com///commit/94a0d8ad6f672f011e922ce1813632887499a301)) 


  Bumps [validator](https://github.com/validatorjs/validator.js) from 13.15.15 to 13.15.20.
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.15...13.15.20)
  
  ---
  updated-dependencies:
  - dependency-name: validator
    dependency-version: 13.15.20
    dependency-type: direct:production
  ...
- Bump the e2e-test-dependencies group
 ([d8d93f9](https://github.com///commit/d8d93f9b8edf2193fd78fa5541712bf613a9c28a)) 


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 3 updates: [commander](https://github.com/tj/commander.js), [dayjs](https://github.com/iamkun/dayjs) and [inquirer](https://github.com/SBoudrias/Inquirer.js).
  
  
  Updates `commander` from 14.0.1 to 14.0.2
  - [Release notes](https://github.com/tj/commander.js/releases)
  - [Changelog](https://github.com/tj/commander.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/tj/commander.js/compare/v14.0.1...v14.0.2)
  
  Updates `dayjs` from 1.11.18 to 1.11.19
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.18...v1.11.19)
  
  Updates `inquirer` from 12.9.6 to 12.10.0
  - [Release notes](https://github.com/SBoudrias/Inquirer.js/releases)
  - [Commits](https://github.com/SBoudrias/Inquirer.js/compare/inquirer@12.9.6...inquirer@12.10.0)
  
  ---
  updated-dependencies:
  - dependency-name: commander
    dependency-version: 14.0.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: dayjs
    dependency-version: 1.11.19
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: inquirer
    dependency-version: 12.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump the mui group in /frontend with 3 updates
 ([13fccec](https://github.com///commit/13fccec266e96898aaed7723cec06278ffceaa9d)) 


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.3 to 7.3.4
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.4/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.3 to 7.3.4
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.4/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.12.0 to 8.16.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.16.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.16.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the production-dependencies group
 ([49e08c8](https://github.com///commit/49e08c8f076748a6cc90eee4f0e2f004ed6663ab)) 


  Bumps the production-dependencies group in /frontend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/store](https://github.com/NorthernTechHQ/nt-gui) | `0.7.0` | `0.8.0` |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.8.2` | `2.9.2` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `10.17.0` | `10.22.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `3.9.0` | `5.3.0` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `7.8.0` | `8.2.0` |
  | [axios](https://github.com/axios/axios) | `1.12.0` | `1.13.1` |
  | [dayjs](https://github.com/iamkun/dayjs) | `1.11.13` | `1.11.19` |
  | [react](https://github.com/facebook/react/tree/HEAD/packages/react) | `19.1.1` | `19.2.0` |
  | [react-dom](https://github.com/facebook/react/tree/HEAD/packages/react-dom) | `19.1.1` | `19.2.0` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.62.0` | `7.66.0` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.8.1` | `7.9.5` |
  | [uuid](https://github.com/uuidjs/uuid) | `11.1.0` | `13.0.0` |
  
  
  Updates `@northern.tech/store` from 0.7.0 to 0.8.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/store-0.7.0...@northern.tech/store-0.8.0)
  
  Updates `@reduxjs/toolkit` from 2.8.2 to 2.9.2
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.8.2...v2.9.2)
  
  Updates `@sentry/react` from 10.17.0 to 10.22.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/10.17.0...10.22.0)
  
  Updates `@stripe/react-stripe-js` from 3.9.0 to 5.3.0
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v3.9.0...v5.3.0)
  
  Updates `@stripe/stripe-js` from 7.8.0 to 8.2.0
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v7.8.0...v8.2.0)
  
  Updates `axios` from 1.12.0 to 1.13.1
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.12.0...v1.13.1)
  
  Updates `dayjs` from 1.11.13 to 1.11.19
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.13...v1.11.19)
  
  Updates `react` from 19.1.1 to 19.2.0
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.0/packages/react)
  
  Updates `react-dom` from 19.1.1 to 19.2.0
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.0/packages/react-dom)
  
  Updates `react-hook-form` from 7.62.0 to 7.66.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.62.0...v7.66.0)
  
  Updates `react-router-dom` from 7.8.1 to 7.9.5
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.9.5/packages/react-router-dom)
  
  Updates `uuid` from 11.1.0 to 13.0.0
  - [Release notes](https://github.com/uuidjs/uuid/releases)
  - [Changelog](https://github.com/uuidjs/uuid/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/uuidjs/uuid/compare/v11.1.0...v13.0.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/store"
    dependency-version: 0.8.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.9.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 10.22.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 5.3.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 8.2.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: axios
    dependency-version: 1.13.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: dayjs
    dependency-version: 1.11.19
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react
    dependency-version: 19.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-dom
    dependency-version: 19.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.66.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.9.5
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: uuid
    dependency-version: 13.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  ...
- Bump nats
 ([6ef8f84](https://github.com///commit/6ef8f840f0b80bddfcaf20b5a3a13bf112873d68)) 


  Bumps the backend-docker-compose-dependencies group with 1 update in the / directory: nats.
  
  
  Updates `nats` from 2.11 to 2.12
  
  ---
  updated-dependencies:
  - dependency-name: nats
    dependency-version: '2.12'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the backend-golang-dependencies group across 1 directory with 17 updates
 ([9e22c80](https://github.com///commit/9e22c80c9521fb3d9e782f7922e97610f6e361f5)) 


  Bumps the backend-golang-dependencies group with 12 updates in the /backend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.19.0` | `1.19.1` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.38.3` | `1.39.2` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.31.6` | `1.31.12` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.1` | `1.69.5` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.2` | `1.32.6` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.87.3` | `1.88.3` |
  | [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) | `1.10.1` | `1.11.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.8` | `2.12.0` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.45.0` | `1.46.1` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.13.0` | `9.14.0` |
  | [github.com/spf13/viper](https://github.com/spf13/viper) | `1.20.1` | `1.21.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.43.0` | `0.44.0` |
  
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.19.0 to 1.19.1
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/sdk-breaking-changes-guide-migration.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.19.0...sdk/azcore/v1.19.1)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.38.3 to 1.39.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.38.3...v1.39.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.31.6 to 1.31.12
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.31.6...config/v1.31.12)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.10 to 1.18.16
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.10...config/v1.18.16)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.1 to 1.69.5
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.1...service/iot/v1.69.5)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.2 to 1.32.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.32.2...v1.32.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.87.3 to 1.88.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.87.3...service/s3/v1.88.3)
  
  Updates `github.com/gin-gonic/gin` from 1.10.1 to 1.11.0
  - [Release notes](https://github.com/gin-gonic/gin/releases)
  - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/gin-gonic/gin/compare/v1.10.1...v1.11.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.8 to 2.12.0
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.8...v2.12.0)
  
  Updates `github.com/nats-io/nats.go` from 1.45.0 to 1.46.1
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.45.0...v1.46.1)
  
  Updates `github.com/redis/go-redis/v9` from 9.13.0 to 9.14.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.13.0...v9.14.0)
  
  Updates `github.com/spf13/viper` from 1.20.1 to 1.21.0
  - [Release notes](https://github.com/spf13/viper/releases)
  - [Commits](https://github.com/spf13/viper/compare/v1.20.1...v1.21.0)
  
  Updates `golang.org/x/crypto` from 0.41.0 to 0.42.0
  - [Commits](https://github.com/golang/crypto/compare/v0.41.0...v0.42.0)
  
  Updates `golang.org/x/net` from 0.43.0 to 0.44.0
  - [Commits](https://github.com/golang/net/compare/v0.43.0...v0.44.0)
  
  Updates `golang.org/x/sys` from 0.35.0 to 0.36.0
  - [Commits](https://github.com/golang/sys/compare/v0.35.0...v0.36.0)
  
  Updates `golang.org/x/term` from 0.34.0 to 0.35.0
  - [Commits](https://github.com/golang/term/compare/v0.34.0...v0.35.0)
  
  Updates `golang.org/x/time` from 0.12.0 to 0.13.0
  - [Commits](https://github.com/golang/time/compare/v0.12.0...v0.13.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.19.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.39.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.12
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.16
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.88.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/gin-gonic/gin
    dependency-version: 1.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.46.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.14.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/spf13/viper
    dependency-version: 1.21.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.44.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.36.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.35.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/time
    dependency-version: 0.13.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...




### Revert


- "chore(iot-manager): replace deprecated cipher NewCFBDecrypter and NewCFBEncrypter (...)"
 ([b9f3810](https://github.com///commit/b9f38101319e9e118d724c0d1d18a6c4db7a5111)) 


  This reverts commit 8baa94e909df4b39f55e8ac31653d5b490cf918c.






## v4.1.0-saas.19 - 2025-11-12


### Bug fixes


- *(gui)* Increased reliance on theme defined button colors to align more w/ updated theme
 ([28cd0fd](https://github.com///commit/28cd0fd1a2e5c976d16769a25daff75125748035)) 

- *(useradm)* Handle tenant not found in login endpoints
 ([cc35fac](https://github.com///commit/cc35fac4a77bd74bff1e84667c11b5d6ec9c1156)) 

- Validate rate limit config when setting up redis
([MEN-8864](https://northerntech.atlassian.net/browse/MEN-8864)) ([39b60a7](https://github.com///commit/39b60a7a28133ed621c8f72a0e0e9fa15e9252e4)) 




### Documentation


- *(deployments)* Add artifact_too_big device deployment status
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([da06093](https://github.com///commit/da0609333b510e508047e330207e9b9c4c552c13)) 

- *(deployments)* Document 'sort' option in the internal endpoint for getting deployments
([MEN-8914](https://northerntech.atlassian.net/browse/MEN-8914)) ([7165f58](https://github.com///commit/7165f58eec679b36e0a83f5a4d4b71595c62aa30)) 





### Features


- *(deployments)* Add 'artifact too big' device deployment status
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([d4a2115](https://github.com///commit/d4a21156026382d54d4d8cf6d9d0bb22e3551d7a)) 

- *(deployments)* Add max artifact size limit for micro devices
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([91a6788](https://github.com///commit/91a678800810bea55596e0b547e3fbfe7b0ab33d)) 

- *(deployments)* Limit max deployment artifact size for micro devices
([MEN-8573](https://northerntech.atlassian.net/browse/MEN-8573)) ([54a4f0d](https://github.com///commit/54a4f0da572e0499a8f62cdc693e7877b1afa471)) 

- *(deviceauth)* Internal endpoints for device limits
([MEN-8904](https://northerntech.atlassian.net/browse/MEN-8904)) ([66f2a77](https://github.com///commit/66f2a778b8793bd9eb3855b14902fee76a099756)) 


  Support for all device tiers for set, get, delete operations.

- *(deviceauth)* Rate limit deployments/next for micro tier devices
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([346acec](https://github.com///commit/346acec4857be4ee659f8add445655e91b0d9b9f)) 

- *(deviceauth)* Adjusted rate limits to account for device tier
 ([6e6c73f](https://github.com///commit/6e6c73f18ee750444864f20167030868abb7b847)) 


  The new device tier for standard devices are:
   - 15 requests/minute for checkUpdate
   - 15 requests/minute for submitInventory
   - 30 requests/minute for all other operations
  
   For micro device tier the ratelimits are:
   - 1 request/day for checkUpdate
   - 1 requests/14days for submitInventory
   - 30 requests/day for all other operations

- *(pkg)* Add device tier to identity
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([de321eb](https://github.com///commit/de321ebdb4235bd1bed6d749fe5e774781137dbd)) 

- *(tenantadm)* Device tier limits support for create_organization workflow
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([00996c8](https://github.com///commit/00996c8a8e385fd9bca7763aa82e88cccc994c7c)) 

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([64ca71f](https://github.com///commit/64ca71f162901bb4dce096f14da416a23495dfbc)) 


  Added the following configuration parameters:
  ```yaml
  rate_limits:
    # auth configures rate limits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # reject_unmatched rejects requests that does not resolve to a
      # rate limit group. That is, if either there's no api_pattern matching
      # the request or if the group_expression does not match a group.
      # Defaults to false - disable rate limiting for unmatched requests.
      reject_unmatched: false
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups:
          # name defines the name of the group. The name is used in
          # match.group_expression to match an api_pattern with a group.
        - name: default
          # interval is the time interval when the rate limiter resets.
          interval: 1m
          # quota is the number of requests allowed in an interval.
          quota: 300
          # event_expression is a go template for grouping requests.
          # The following attributes are available in the context:
          # Identity - contains a subset of the JWT claims:
          # .Subject  (jwt:"sub")          string
          # .Tenant   (jwt:"mender.tenant") string
          # .Plan     (jwt:"mender.plan")   string
          # .Addons   (jwt:"mender.addons") []struct{Enabled bool; Name string}
          # .IsUser   (jwt:"mender.user")   bool
          # .IsDevice (jwt:"mender.device") bool
          # .Trial    (jwt:"mender.trial")  bool
          event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
      match:
          # api_pattern specifies an API path pattern as defined by http.ServeMux
          # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
        - api_pattern: /
          # group_expression defines  the group for this matching expression.
          # A group can be selected dynamically using Go templates or statically
          # with a literal string.
          # See group.event_expression for template context attributes.
          group_expression: "default"
          # More example match rules:
  ```

- *(workflows)* Add device tier limits to create_organization workflows
([MEN-8906](https://northerntech.atlassian.net/browse/MEN-8906)) ([fd4d469](https://github.com///commit/fd4d469e9f896e6f90a95da47862000b6dbabb29)) 





### Refactor


- *(ratelimits)* Move ratelimits default configs to service config
 ([f5af7f3](https://github.com///commit/f5af7f30fdd67235a0532c0989617db9505bdc61)) 


  The defaults will differ so we need to decentralize them.







## v4.1.0-saas.18 - 2025-11-04


### Bug fixes


- *(gui)* Fixed an issue that prevented updating existing sso configs
 ([d022d1a](https://github.com///commit/d022d1a78ba2f2b60cc1670b0015451c01c5734e)) 







## v4.1.0-saas.17 - 2025-11-03


### Bug fixes


- *(deployments)* Fixed faulty delta artifact generation specs that lead to faulty client generation
 ([8aa15fd](https://github.com///commit/8aa15fd7166403eb640d231d373832ef5def029f)) 

- *(deployments)* Backwards compatible artifact metadata
 ([MEN-8941](https://northerntech.atlassian.net/browse/MEN-8941)) ([8110c52](https://github.com///commit/8110c5251b1025bc00a9b7c56e42500715c477d0))

- *(deployments)* Panic on database errors on DELETE /artifacts
 ([f3c9bda](https://github.com///commit/f3c9bda8eb050ceb744f0ce7f45c58c44934c861)) 

- *(generate-delta-worker)* Do not expose signed url in description
 ([6538a53](https://github.com///commit/6538a5351acf73575b2ac1c19659f1af9e70feb6)) 


  Extracts the artifact ID in the URL to avoid printing the signed URL to
  the source artifact.

- *(gui)* Fixed an issue that left notch in outlined w/o a background
 ([1673cff](https://github.com///commit/1673cff934be78a379d9123f93317336ee83bfe0)) 

- *(gui)* Fixed an issue that prevented closing details view of an ongoing delta generation
 ([0770333](https://github.com///commit/07703338737f7b400198b6b58da55895d9dc2a06)) 

- *(gui)* Removed error messages shown when subscribing or showing billing info as trial user
 ([231d4e3](https://github.com///commit/231d4e34a0d376a2b963e4e01a4a393a975f2668)) 


  - NB: this lets the frontend rely on trial signups to always provide a new billing profile when signing up

- *(tenantadm)* Ignore Stripe subscriptions not managed by this service
([MEN-8708](https://northerntech.atlassian.net/browse/MEN-8708)) ([4e8c712](https://github.com///commit/4e8c71200c16210da4349667c6b6003d6ca69f05)) 


  Instead of correlating events with customer ID, we correlate with
  subscription IDs. This is mostly to address a transient issue in the
  transition phase where a multi-subscription customer will have the
  subscriptions consolidated, but it also eliminates the need for
  additional database indexing to cover fast customer lookups.

- *(useradm)* Add orchestrator client to command for getting user stats
 ([19bfb5b](https://github.com///commit/19bfb5b4e3e4dd10aac27d961fb82d6f0e9b7578)) 


  Without the orchestrator client, stats will not be exported to google
  spreadsheet.

- *(useradm)* Invalidate cache when deleting PAT token
([MEN-7285](https://northerntech.atlassian.net/browse/MEN-7285)) ([e05e898](https://github.com///commit/e05e898b7056c79aefad095b9e22f359dcfd1174)) 

- *(useradm)* Prevent race condition recaching revoked PAT token
 ([1564ec6](https://github.com///commit/1564ec6a452c366af2ea4069340e9173669aa4db)) 





### Documentation


- *(deployments)* Mark release meta_data as deprecated
 ([33563c6](https://github.com///commit/33563c6ac639c4fdba1471eb0c1e65e66e2e4f80)) 

- *(deployments)* Use array type for deprecated meta_data attribute
 ([0135305](https://github.com///commit/0135305d78d95038ff7c3bfadcdd8d34d7a8a8df)) 

- *(devicemonitor)* Added internal delete device endpoint to api docs
 ([85e5570](https://github.com///commit/85e557004ec26e1ad32e3e1b296d2391ba5c9a51)) 

- *(tenantad)* Document new "updated_at" field of tenant object
([MEN-8859](https://northerntech.atlassian.net/browse/MEN-8859)) ([5266b1d](https://github.com///commit/5266b1da670276875a44429c66647b04191fc5eb)) 

- *(useradm)* API documentation for user feedback endpoint
 ([6bc4c29](https://github.com///commit/6bc4c298931e0b746ace659b6b3d375fb59c085c)) 





### Features


- *(deployments)* Added support for anthropic analysis backend
 ([0e71550](https://github.com///commit/0e715506bb4b23b5115a56ef7d5ad5d75a057847)) 

- *(deviceauth)* Rate limit deployments/next for micro tier devices
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([346acec](https://github.com///commit/346acec4857be4ee659f8add445655e91b0d9b9f)) 

- *(devicemonitor)* Added internal delete device endpoint
 ([2cc83f6](https://github.com///commit/2cc83f6883c22b092139513105c08a91e66c4484)) 

- *(gui)* Let ai request cool down time reflect reality when rate limited
 ([92e8864](https://github.com///commit/92e8864a8c9d95991d17ad562877bc6e114ec727)) 

- *(gui)* Added execution feedback to troubleshooting device interactions
([MEN-8632](https://northerntech.atlassian.net/browse/MEN-8632)) ([e1e4074](https://github.com///commit/e1e4074581b787e9a7bf43943aba68cf9a4a4407)) 

- *(gui)* Let tenant sso setting inheritance conditions be more explicit
([MEN-8672](https://northerntech.atlassian.net/browse/MEN-8672)) ([76d4db9](https://github.com///commit/76d4db9a219758e21d357f487435cf106bbc62c6)) 

- *(gui)* Made it possible for tenants to allow improving ai functionality in the future
([MEN-8719](https://northerntech.atlassian.net/browse/MEN-8719)) ([c2dd114](https://github.com///commit/c2dd114e1ec2d2eeb8b33dc300d04de04d3861cd)) 

- *(gui)* Ensured progress gets updated when monitoring a delta generation job
 ([7487d8f](https://github.com///commit/7487d8f0dc6b921ede11ddac6ab3bae392a1ffff)) 

- *(pkg)* Add device tier to identity
([MEN-8580](https://northerntech.atlassian.net/browse/MEN-8580)) ([de321eb](https://github.com///commit/de321ebdb4235bd1bed6d749fe5e774781137dbd)) 

- *(tenantadm)* Register timestamp of last modification with tenant object
([MEN-8859](https://northerntech.atlassian.net/browse/MEN-8859)) ([52c3884](https://github.com///commit/52c38840850fbf0785ac3f89d4ff6d5c0da0b579)) 

- *(useradm)* Email notifications on two-factor authentication changes
([MEN-8903](https://northerntech.atlassian.net/browse/MEN-8903)) ([f41f382](https://github.com///commit/f41f3822f6cc0cf91c753c9d1d6c1f0a44f36a7a)) 


  An email notification is sent to the user email when the user enables or
  disables two-factor authentication.

- *(useradm)* Require consent to enable AI features
([MEN-8677](https://northerntech.atlassian.net/browse/MEN-8677)) ([909a9bd](https://github.com///commit/909a9bd0b1c47b692014353599021d201e29a561)) 


  There is an explicit option for enabling AI features in the global
  settings (`aiFeatures.enabled`), requiring admin access to allow
  using the feature.

- *(useradm)* New endpoint for submitting user feedback
([MEN-7603](https://northerntech.atlassian.net/browse/MEN-7603)) ([2f73a24](https://github.com///commit/2f73a24cb9217d8cea65561bb4f3bdeff786f80b)) 


  POST /api/management/v2/useradm/support/feedback/:form_id
  
  The new endpoint accepts a form response with user feedback. There are
  currently two `form_id` defined: "product" and "feat.ai" for general
  product feedback and feedback specific to the experimental AI feature.

- *(workflows)* Delete devicemonitor device when decommissioning devices
 ([6a25915](https://github.com///commit/6a25915ecac07346111c9f30af0d4cd12e5d03a9)) 

- New flag `--tenant-token` for `create-org` CLI command
([MEN-7901](https://northerntech.atlassian.net/browse/MEN-7901)) ([5df75ff](https://github.com///commit/5df75ff970d27326d7507402e233af61262463d4)) 


  The new flag sets the tenant-token to a given string.
  Primarily useful in tests.




### Refactor


- *(gui)* Refactored subscription form to be a RHF form & reduce faulty billing calls
 ([5938972](https://github.com///commit/59389724fd85802e50dc6ce951814a5d8d4beeb0)) 

- *(useradm)* Share workflows client code for starting workflow
 ([2d6eae6](https://github.com///commit/2d6eae6d9dc7f0e9023c89f14c509be2b814c3fa)) 





### Security


- Bump validator in /frontend/tests/e2e_tests
 ([f9d5dd6](https://github.com///commit/f9d5dd641b6fbb7ebf24049de8cd20d541b3bc84)) 


  Bumps [validator](https://github.com/validatorjs/validator.js) from 13.15.15 to 13.15.20.
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.15...13.15.20)
  
  ---
  updated-dependencies:
  - dependency-name: validator
    dependency-version: 13.15.20
    dependency-type: direct:development
  ...
- Bump validator from 13.15.15 to 13.15.20 in /frontend
 ([94a0d8a](https://github.com///commit/94a0d8ad6f672f011e922ce1813632887499a301)) 


  Bumps [validator](https://github.com/validatorjs/validator.js) from 13.15.15 to 13.15.20.
  - [Release notes](https://github.com/validatorjs/validator.js/releases)
  - [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/validatorjs/validator.js/compare/13.15.15...13.15.20)
  
  ---
  updated-dependencies:
  - dependency-name: validator
    dependency-version: 13.15.20
    dependency-type: direct:production
  ...
- Bump chrislusf/seaweedfs
 ([7bcb49b](https://github.com///commit/7bcb49b2bef8b6dd098d32040d8ca4ecf4f308e0)) 


  Bumps the backend-docker-compose-dependencies group with 1 update in the /compose directory: chrislusf/seaweedfs.
  
  
  Updates `chrislusf/seaweedfs` from 3.97 to 3.99
  
  ---
  updated-dependencies:
  - dependency-name: chrislusf/seaweedfs
    dependency-version: '3.99'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([fcfe670](https://github.com///commit/fcfe67062b3287b2dfec568940babd9c7e555ef2)) 


  Bumps the backend-golang-dependencies group in /backend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/storage/azblob](https://github.com/Azure/azure-sdk-for-go) | `1.6.2` | `1.6.3` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.39.2` | `1.39.5` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.31.12` | `1.31.16` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.18.16` | `1.18.20` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.5` | `1.69.8` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.6` | `1.32.9` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.88.4` | `1.89.1` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.12.0` | `2.12.1` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.46.1` | `1.47.0` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.14.0` | `9.16.0` |
  | [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) | `1.17.4` | `1.17.6` |
  | [golang.org/x/time](https://github.com/golang/time) | `0.13.0` | `0.14.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/storage/azblob` from 1.6.2 to 1.6.3
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/storage/azblob/v1.6.2...sdk/storage/azblob/v1.6.3)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.39.2 to 1.39.5
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.39.2...v1.39.5)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.31.12 to 1.31.16
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.31.12...config/v1.31.16)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.16 to 1.18.20
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/config/v1.18.20/CHANGELOG.md)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.16...config/v1.18.20)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.5 to 1.69.8
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.5...service/iot/v1.69.8)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.6 to 1.32.9
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.32.6...service/mgn/v1.32.9)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.88.4 to 1.89.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.88.4...service/s3/v1.89.1)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.12.0 to 2.12.1
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.12.0...v2.12.1)
  
  Updates `github.com/nats-io/nats.go` from 1.46.1 to 1.47.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.46.1...v1.47.0)
  
  Updates `github.com/redis/go-redis/v9` from 9.14.0 to 9.16.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.14.0...v9.16.0)
  
  Updates `go.mongodb.org/mongo-driver` from 1.17.4 to 1.17.6
  - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
  - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.17.4...v1.17.6)
  
  Updates `golang.org/x/time` from 0.13.0 to 0.14.0
  - [Commits](https://github.com/golang/time/compare/v0.13.0...v0.14.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/storage/azblob
    dependency-version: 1.6.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.39.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.16
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.20
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.8
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.9
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.89.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.47.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.16.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: go.mongodb.org/mongo-driver
    dependency-version: 1.17.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/time
    dependency-version: 0.14.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump @playwright/test
 ([28a4805](https://github.com///commit/28a48056a49a56847807b947dec81661d1f29dee)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.55.1 to 1.56.1
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.55.1...v1.56.1)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.56.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump the e2e-test-dependencies group
 ([d8d93f9](https://github.com///commit/d8d93f9b8edf2193fd78fa5541712bf613a9c28a)) 


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 3 updates: [commander](https://github.com/tj/commander.js), [dayjs](https://github.com/iamkun/dayjs) and [inquirer](https://github.com/SBoudrias/Inquirer.js).
  
  
  Updates `commander` from 14.0.1 to 14.0.2
  - [Release notes](https://github.com/tj/commander.js/releases)
  - [Changelog](https://github.com/tj/commander.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/tj/commander.js/compare/v14.0.1...v14.0.2)
  
  Updates `dayjs` from 1.11.18 to 1.11.19
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.18...v1.11.19)
  
  Updates `inquirer` from 12.9.6 to 12.10.0
  - [Release notes](https://github.com/SBoudrias/Inquirer.js/releases)
  - [Commits](https://github.com/SBoudrias/Inquirer.js/compare/inquirer@12.9.6...inquirer@12.10.0)
  
  ---
  updated-dependencies:
  - dependency-name: commander
    dependency-version: 14.0.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: dayjs
    dependency-version: 1.11.19
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: inquirer
    dependency-version: 12.10.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump the mui group in /frontend with 3 updates
 ([13fccec](https://github.com///commit/13fccec266e96898aaed7723cec06278ffceaa9d)) 


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.3 to 7.3.4
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.4/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.3 to 7.3.4
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.4/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.12.0 to 8.16.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.16.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.16.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the production-dependencies group
 ([49e08c8](https://github.com///commit/49e08c8f076748a6cc90eee4f0e2f004ed6663ab)) 


  Bumps the production-dependencies group in /frontend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/store](https://github.com/NorthernTechHQ/nt-gui) | `0.7.0` | `0.8.0` |
  | [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) | `2.8.2` | `2.9.2` |
  | [@sentry/react](https://github.com/getsentry/sentry-javascript) | `10.17.0` | `10.22.0` |
  | [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) | `3.9.0` | `5.3.0` |
  | [@stripe/stripe-js](https://github.com/stripe/stripe-js) | `7.8.0` | `8.2.0` |
  | [axios](https://github.com/axios/axios) | `1.12.0` | `1.13.1` |
  | [dayjs](https://github.com/iamkun/dayjs) | `1.11.13` | `1.11.19` |
  | [react](https://github.com/facebook/react/tree/HEAD/packages/react) | `19.1.1` | `19.2.0` |
  | [react-dom](https://github.com/facebook/react/tree/HEAD/packages/react-dom) | `19.1.1` | `19.2.0` |
  | [react-hook-form](https://github.com/react-hook-form/react-hook-form) | `7.62.0` | `7.66.0` |
  | [react-router-dom](https://github.com/remix-run/react-router/tree/HEAD/packages/react-router-dom) | `7.8.1` | `7.9.5` |
  | [uuid](https://github.com/uuidjs/uuid) | `11.1.0` | `13.0.0` |
  
  
  Updates `@northern.tech/store` from 0.7.0 to 0.8.0
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/store-0.7.0...@northern.tech/store-0.8.0)
  
  Updates `@reduxjs/toolkit` from 2.8.2 to 2.9.2
  - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
  - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v2.8.2...v2.9.2)
  
  Updates `@sentry/react` from 10.17.0 to 10.22.0
  - [Release notes](https://github.com/getsentry/sentry-javascript/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript/blob/develop/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript/compare/10.17.0...10.22.0)
  
  Updates `@stripe/react-stripe-js` from 3.9.0 to 5.3.0
  - [Release notes](https://github.com/stripe/react-stripe-js/releases)
  - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/react-stripe-js/compare/v3.9.0...v5.3.0)
  
  Updates `@stripe/stripe-js` from 7.8.0 to 8.2.0
  - [Release notes](https://github.com/stripe/stripe-js/releases)
  - [Commits](https://github.com/stripe/stripe-js/compare/v7.8.0...v8.2.0)
  
  Updates `axios` from 1.12.0 to 1.13.1
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.12.0...v1.13.1)
  
  Updates `dayjs` from 1.11.13 to 1.11.19
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.13...v1.11.19)
  
  Updates `react` from 19.1.1 to 19.2.0
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.0/packages/react)
  
  Updates `react-dom` from 19.1.1 to 19.2.0
  - [Release notes](https://github.com/facebook/react/releases)
  - [Changelog](https://github.com/facebook/react/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/facebook/react/commits/v19.2.0/packages/react-dom)
  
  Updates `react-hook-form` from 7.62.0 to 7.66.0
  - [Release notes](https://github.com/react-hook-form/react-hook-form/releases)
  - [Changelog](https://github.com/react-hook-form/react-hook-form/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/react-hook-form/react-hook-form/compare/v7.62.0...v7.66.0)
  
  Updates `react-router-dom` from 7.8.1 to 7.9.5
  - [Release notes](https://github.com/remix-run/react-router/releases)
  - [Changelog](https://github.com/remix-run/react-router/blob/main/packages/react-router-dom/CHANGELOG.md)
  - [Commits](https://github.com/remix-run/react-router/commits/react-router-dom@7.9.5/packages/react-router-dom)
  
  Updates `uuid` from 11.1.0 to 13.0.0
  - [Release notes](https://github.com/uuidjs/uuid/releases)
  - [Changelog](https://github.com/uuidjs/uuid/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/uuidjs/uuid/compare/v11.1.0...v13.0.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/store"
    dependency-version: 0.8.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@reduxjs/toolkit"
    dependency-version: 2.9.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@sentry/react"
    dependency-version: 10.22.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/react-stripe-js"
    dependency-version: 5.3.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 8.2.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  - dependency-name: axios
    dependency-version: 1.13.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: dayjs
    dependency-version: 1.11.19
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react
    dependency-version: 19.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-dom
    dependency-version: 19.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.66.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.9.5
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: uuid
    dependency-version: 13.0.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: production-dependencies
  ...




### Revert


- "chore(iot-manager): replace deprecated cipher NewCFBDecrypter and NewCFBEncrypter (...)"
 ([b9f3810](https://github.com///commit/b9f38101319e9e118d724c0d1d18a6c4db7a5111)) 


  This reverts commit 8baa94e909df4b39f55e8ac31653d5b490cf918c.






## v4.1.0-saas.16 - 2025-10-23


### Bug fixes


- *(tenantadm)* Make subscription parameters required for preview recurring invoice
([MEN-8835](https://northerntech.atlassian.net/browse/MEN-8835)) ([3bfa95c](https://github.com///commit/3bfa95c74ef3e515487913ea1bebe59eb50d2b98)) 


  The recurring preview mode does not work in some edge cases. Since the
  request is always sent from the UI with a subscription request we'll
  enforce this requirement and remove the dependency on the subscription
  when doing the upstream request.

- *(deployments)* Throw error when `per_page` exceeds maximum allowed value
([MEN-8841](https://northerntech.atlassian.net/browse/MEN-8841)) ([e7c966c](https://github.com///commit/e7c966cb9311b2866b13570a97efa3e54c06ad9c)) 

- *(deployments)* Aligned update metadata understanding w/ mender-artifact
 ([33fae57](https://github.com///commit/33fae571932e14ca5b16afd26bc8e410b5c2a92b)) 


  - api responses represented the content as a list, whereas the proper representation is the object

- *(deviceauth)* Count current devices for max_devices limit
([MEN-8767](https://northerntech.atlassian.net/browse/MEN-8767)) ([3041965](https://github.com///commit/3041965d6788744c8484f35498c9c0854ad9d6bd)) 

- *(deviceauth)* `request_size_limit` configuration not applied
([MEN-8788](https://northerntech.atlassian.net/browse/MEN-8788)) ([93d82a5](https://github.com///commit/93d82a59001e23650efb8d5d2518b4b0b9534206)) 

- *(deviceauth)* Always exit with non-zero exit code on error
 ([c486a45](https://github.com///commit/c486a4520bdfdd4402134a2cdfe4ac6a4a206d7a)) 

- *(deviceauth)* Tier in authreq for devices with external id
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([2de6766](https://github.com///commit/2de67665323269be3d5afc3632b8d3aafc45b169)) 

- *(deviceconnect)* SetReadDeadline when setting up ping handler
([MEN-8843](https://northerntech.atlassian.net/browse/MEN-8843)) ([b10a3a8](https://github.com///commit/b10a3a8dd0b1b4c85c6b33184b9f9ed6b5fa8b86)) 

- *(gui)* Fixed an issue that prevented showing billing errors
 ([06f0cec](https://github.com///commit/06f0cecd067917479b8249b362d5edfa317b89e4)) 

- *(gui)* Let theme switch also be reflected via external style definitions
 ([2485bf1](https://github.com///commit/2485bf1a8c00b2060797b0977284980fd420fd63)) 

- *(gui)* Fixed contact descriptions
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([a013a00](https://github.com///commit/a013a0074da904d19d1ca01c9ad8dfef0382d083)) 

- *(gui)* Fall back to delta job count while pagination total isn't available
 ([79360cc](https://github.com///commit/79360cc0e91249c86e867eb766b9216dcd3f2fa9)) 

- *(gui)* Fixed an issue that could cause the deployment device limit to be ignored
([ME-568](https://northerntech.atlassian.net/browse/ME-568)) ([64974ec](https://github.com///commit/64974ec50a534fc690c9ce0ea91c80dbb3407607)) 

- *(gui)* Reduce situations deployments to specific devices won't find releases
 ([bd4e361](https://github.com///commit/bd4e361f8e0fa34f7d479237f3b17a1d24de6675)) 

- *(gui)* Limited chances a set deployment device limit gets changed unintended
 ([1f12d38](https://github.com///commit/1f12d38249ac4bba72bbbc7ebb92ffdcf4fe9b09)) 

- *(gui)* Fixed an issue that could prevent the billing overview from working
 ([4d1f0f3](https://github.com///commit/4d1f0f3f41ece22b75310d76f2015ff7576f4a8c)) 

- *(gui)* Fixed an issue that prevented editing SSO configurations
 ([3005bea](https://github.com///commit/3005beaad9511b5c4768eff7438fc009fd8b567f)) 

- *(gui)* Fixed faulty check to see if user settings info can be relied on
 ([9251747](https://github.com///commit/92517472e60c29c5025ea4b948525aeb45d04599)) 

- *(tenantadm)* Proxy invalid user error from useradm
([MEN-8857](https://northerntech.atlassian.net/browse/MEN-8857)) ([050bd72](https://github.com///commit/050bd72961194684fe2e924636cba63b9427520a)) 

- *(tenantadm)* Properly handle duplicate Stripe webhook events
 ([90e88c7](https://github.com///commit/90e88c7e7dd093ac629454089b640f8ff9403ac4)) 

- *(useradm)* Fix command for collecting user stats
([MEN-8862](https://northerntech.atlassian.net/browse/MEN-8862)) ([e1c70d4](https://github.com///commit/e1c70d45d45e5fbe7de7874e96c28cc790500493)) 

- *(workflows)* Remove Retries
 ([3e5b281](https://github.com///commit/3e5b281e26b98c7d5cf9cf7c05bf1d56abe515be)) 


  This retry mechanism has no automatic Delay, so the retries are made in
  sequence, and this is useless and detrimental to the load.
  
  Removing the retries, while waiting for a more robust approach, like
  retries with delays and workflows autoscaling.

- *(workflows)* Expose Jetstream `replicas` parameter
([MEN-7164](https://northerntech.atlassian.net/browse/MEN-7164)) ([b87100e](https://github.com///commit/b87100eb5aa12fec6ac83dd59329e1742a6fbfa9)) 

- Adjusted burst limiting to work w/ updated miniredis
 ([8158efa](https://github.com///commit/8158efa8a1a814cc0b31051cd77bdf8bf8960801)) 


  - prior it was "every request extends the window" => now: "first request wins the window"
- Validate rate limit config when setting up redis
([MEN-8864](https://northerntech.atlassian.net/browse/MEN-8864)) ([186f750](https://github.com///commit/186f7505048c8404fdf646b6a669ad02b27b8aea)) 
- Check release tags when fetching a release by name
([MEN-8422](https://northerntech.atlassian.net/browse/MEN-8422)) ([cf4a45b](https://github.com///commit/cf4a45b4affc4d583fb6d2bf13c9607000661a02)) 




### Documentation


- *(deviceauth)* Update and deprecate /limits/max_devices endpoints
([MEN-8570](https://northerntech.atlassian.net/browse/MEN-8570)) ([a70bcda](https://github.com///commit/a70bcdae3485615d31d7b999c2d9023e73136bd7)) 

- *(deviceauth)* Add missing spec for limits/devices to backend docs
 ([2212874](https://github.com///commit/22128746d51cadd01da6942426c16ba7737d59f1)) 

- *(deviceauth)* Document unlimited limits in API docs
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([fff5975](https://github.com///commit/fff5975d3a1163fa31d97f34412eef8ffa50c40e)) 

- *(api)* Unified path structure + servers across specs
 ([2a73980](https://github.com///commit/2a739800ae8694fa5d210365fceac50413696f44)) 

- *(api)* Deduplicated schema definitions across service specs
 ([a7f31cb](https://github.com///commit/a7f31cbd2e9c48bd28a23bc624297d628fd7b145)) 

- *(deployments)* Aligned docs based specs w/ services based specs
 ([f84f39b](https://github.com///commit/f84f39b702a6ba3301ca475b7c5914ee350d09fa)) 


  - to also publish delta job endpoints

- *(deployments)* Clarify V2 `/artifacts` endpoint usage
([MEN-8842](https://northerntech.atlassian.net/browse/MEN-8842)) ([d5a1a0f](https://github.com///commit/d5a1a0f471fd51fc82d07fcf41082abd74b42b9c)) 

- *(inventory)* Add clarity to list devices api docs
 ([c460380](https://github.com///commit/c46038013ba60510d2a45fcea66917be29642976)) 

- *(useradm)* Make API specs more consistent with enterprise
([MEN-8345](https://northerntech.atlassian.net/browse/MEN-8345)) ([1022949](https://github.com///commit/1022949e7df31ccb90b624d1c6ba411950c98634)) 

- Aligned enterprise only services w/ file naming scheme + structure
 ([b9c4ccd](https://github.com///commit/b9c4ccd07abaf8921332b0e1e16660647c61118c)) 
- Aligned more error responses w/ existing shared response definitions
 ([d5596d5](https://github.com///commit/d5596d572c1a0621e87b973549fc86d4542d5b69)) 
- Aligned unauthorized errors definitions w/ shared definition
 ([9d26fd7](https://github.com///commit/9d26fd700a572600bba631291102eb1dc34baba3)) 
- Aligned update metadata w/ defined type to allow parsing
 ([f306fac](https://github.com///commit/f306fac4caac94f14daed287def36f0b375d1069)) 




### Features


- *(deviceauth)* Support unlimited device tier limits
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([0e17a1f](https://github.com///commit/0e17a1f4f196b905b478624eced1edecb3776f88)) 

- *(deviceauth)* DEVICEAUTH_ENABLE_TIERS to enable device tiers support
 ([b3bffb4](https://github.com///commit/b3bffb4c75da6d57841bbe99b4ec63ab0f0e71c2)) 

- *(deployments)* Rate limit new device deployments per tenant
([MEN-8840](https://northerntech.atlassian.net/browse/MEN-8840)) ([1ab79a5](https://github.com///commit/1ab79a5e810bca03354ae5ceb5085b2e05ad2183)) 


  Introduce a rate limiter that can be configured to only allow a certain
  number of new device deployments to be created within a specific time
  interval.

- *(deployments)* Configure new device deployments rate limiter
([MEN-8840](https://northerntech.atlassian.net/browse/MEN-8840)) ([70211e7](https://github.com///commit/70211e7e2b8c2a4e8cf917c97b0343222d1e6bd2)) 

- *(deviceauth)* Support for device tier parameter in the authset
([MEN-8558](https://northerntech.atlassian.net/browse/MEN-8558)) ([fa03730](https://github.com///commit/fa037303fe5be4a822fd6d5315aa4f4440f61807)) 


  We introduce a new [authset](https://docs.mender.io/overview/device-authentication)
  parameter: device tier: a string of letters describing a device kind.
  Currently supported values: micro, system, standard.

- *(deviceauth)* Check device tier limit when accepting device
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([8bb262f](https://github.com///commit/8bb262f02fb5f3e9e6a2b3546b4eca61de619cd3)) 

- *(deviceauth)* Maintain device tier from auth set
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([6390f63](https://github.com///commit/6390f63ba4e567c3193b02292cb4e44dcdbca86a)) 


  Maintain the tier of a device based on the latest accepted auth

- *(deviceauth)* Count tenant device limits by tier
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([4084a26](https://github.com///commit/4084a26c21caf51e6244bae4bf94b53c6af55d63)) 

- *(deviceauth)* Management api to get device limit per tier
([MEN-8563](https://northerntech.atlassian.net/browse/MEN-8563)) ([5e9c2e2](https://github.com///commit/5e9c2e2786a6c3499d09f02ff2e3f7c578b9abfb)) 

- *(generate-delta-worker)* GENERATE_DELTA_USE_FIFOS env var control the named pipes usage
([MEN-8762](https://northerntech.atlassian.net/browse/MEN-8762)) ([71dbd6e](https://github.com///commit/71dbd6e411b88c0a794d38d38a5a68573704b03c)) 


  A new setting via an environment variable GENERATE_DELTA_USE_FIFOS
  is introduced to control the use of named pipes in the binary delta
  generation on the server side via generate-delta-worker. This setting
  should be set to false for enviornments where the resources permit
  safe usage of regular files for the delta generation. By defaut it is set
  to false.

- *(gui)* Added chinese server to login notifications
([MEN-8770](https://northerntech.atlassian.net/browse/MEN-8770)) ([ac933a0](https://github.com///commit/ac933a083e936486673d0eb8dc8c544350304493)) 

- *(gui)* Added special handling for non-stripe non-enterprise customers
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([3e99e17](https://github.com///commit/3e99e17765e2010f4feb95f30ce9658a398a36d0)) 

- *(gui)* Utilized AddonSelect for enterprise/non-stripe users
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([13b7c79](https://github.com///commit/13b7c798a8d2815b33fb838bd021ca8541ed81f0)) 

- *(gui)* Added improved success payment modal
([MEN-8703](https://northerntech.atlassian.net/browse/MEN-8703)) ([f56e4c6](https://github.com///commit/f56e4c64333876fce83b484baed36b0d7a27069b)) 

- *(gui)* Let confirmation modal to delay the logout after token invalidation
([MEN-8703](https://northerntech.atlassian.net/browse/MEN-8703)) ([2a1a71e](https://github.com///commit/2a1a71e76e4d029d030d01ea09e1c0753d783890)) 

- *(gui)* Added delta artifact generation job retrieval functionality
 ([66e577a](https://github.com///commit/66e577ad3872122a10f81627fa6518a2d985c3f5)) 

- *(gui)* Added a way to see details about delta generation jobs
([MEN-8250](https://northerntech.atlassian.net/browse/MEN-8250)) ([36c6adf](https://github.com///commit/36c6adfdaa51ff5a3ca243d691e290afbbcf9fce)) 

- *(gui)* Added overview of recent delta generation jobs
([MEN-8251](https://northerntech.atlassian.net/browse/MEN-8251)) ([0ca8799](https://github.com///commit/0ca8799dae18dca14f513fcb3ea48ca6335082f9)) 

- *(gui)* Let release upload be focused on releases view to reduce confusion
([MEN-8248](https://northerntech.atlassian.net/browse/MEN-8248)) ([22bc53c](https://github.com///commit/22bc53c41293450cb880c58fa5fda847f861ffa5)) 

- *(gui)* Let device deployments history access our log viewer as well
([MEN-8727](https://northerntech.atlassian.net/browse/MEN-8727)) ([f1753f7](https://github.com///commit/f1753f74d684e448176f062dc1d93b0258b2b68d)) 

- *(gui)* Let timeframe filter elements also show context dependent notifications
 ([59cac13](https://github.com///commit/59cac137acd21daf69ea8f54dddb6f1fde0da7b2)) 

- *(gui)* Added notification about auditlog retention time to explain missing entries
([MEN-8153](https://northerntech.atlassian.net/browse/MEN-8153)) ([51c8fa1](https://github.com///commit/51c8fa1fa4ba9e020a0a385272c4e531216bfd8e)) 




### Refactor


- *(deviceauth)* Remove unused limits function and fix comment
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([347ddc7](https://github.com///commit/347ddc71d5d09ad09238f90167eebd29ce66d62d)) 

- *(deviceauth)* Rename MaxDevicesCount constant
([MEN-8886](https://northerntech.atlassian.net/browse/MEN-8886)) ([05775fd](https://github.com///commit/05775fdca4e8dea754defd8864b9774231f8562d)) 

- *(deviceauth)* Remove tenantadm related code from OS
([MEN-8649](https://northerntech.atlassian.net/browse/MEN-8649)) ([31b9d2b](https://github.com///commit/31b9d2beeb60a4485449f620ca58df580ba1cae9)) 

- *(gui)* Made use of store + testing package in codebase
 ([2d90e96](https://github.com///commit/2d90e9682eeaf53f45612b7c13b70c2abcc580ed)) 

- *(gui)* Made use of testing package & utils in tests
 ([f416d68](https://github.com///commit/f416d68d89986df4b446f6bca9955c392cee8d34)) 

- *(gui)* Aligned thunk spying w/ updated store package format
 ([ab1ee33](https://github.com///commit/ab1ee331199ec1bab9183d9ebb0568a2a2ffa136)) 

- *(gui)* Let email check be done in thunk to align msw handler location
 ([eaae614](https://github.com///commit/eaae614b8ae7b9b4ed46a9f5fd630ff54e8c746e)) 






## v4.1.0-saas.14 - 2025-09-30


### Bug fixes


- *(deployments)* Limit `name`, `type` and `device types compatible` length
 ([6f612d4](https://github.com///commit/6f612d4c2d8ecb9e3d4f1246cd0755d77cdda11f)) 


  Limit the max length of `name` (aka `Release name` in the gui),
  `type` and `device types compatible` fields in `MultipartGenerateImageMsg`
  (used by single file uploads) to 256 characters.
  
  There has been introduced a limit of 256 characters to the corresponding
  fields in mender-artifact:
      https://github.com/mendersoftware/mender-artifact/commit/ddd821f8a5150fb8a3186b337525f17b2757599c
  causing uploads that do not abide by this limit to fail silently in the
  background when being processed by the workflow worker.
  
  With this input validation we provide an explicit error to the user in
  this case.

- *(deployments)* Limit delta artifact by the uncompressed size
([MEN-8734](https://northerntech.atlassian.net/browse/MEN-8734)) ([12e6da8](https://github.com///commit/12e6da8c13e515e1305bf452062ccbf7d4483d65)) 

- *(deployments)* Increase the server side delta generation limit to 5 GiB
([MEN-8734](https://northerntech.atlassian.net/browse/MEN-8734)) ([32a46d5](https://github.com///commit/32a46d5ab4d7505412a64351c633379e91cb79e2)) 

- *(deviceauth)* `request_size_limit` configuration not applied
([MEN-8788](https://northerntech.atlassian.net/browse/MEN-8788)) ([93d82a5](https://github.com///commit/93d82a59001e23650efb8d5d2518b4b0b9534206)) 

- *(deviceconnect)* Make sure goroutines recover when panicing
([MEN-7750](https://northerntech.atlassian.net/browse/MEN-7750)) ([0f5870a](https://github.com///commit/0f5870ad5d8fc073193a243e9b9a4f12f00752c4)) 

- *(generate-delta-worker)* Do not expose signed url in description
 ([6538a53](https://github.com///commit/6538a5351acf73575b2ac1c19659f1af9e70feb6)) 


  Extracts the artifact ID in the URL to avoid printing the signed URL to
  the source artifact.

- *(gui)* Handle error conditions during trial signup gracefully
 ([744dfd1](https://github.com///commit/744dfd1deb37675b32e708266673928dce56f1a7)) 

- *(gui)* Let artifact generation success depend on artifact presence, not time
 ([3679a0f](https://github.com///commit/3679a0f3cea7b782a550d970b6455719b352a2ec)) 

- *(gui)* Let theme switch also be reflected via external style definitions
 ([2485bf1](https://github.com///commit/2485bf1a8c00b2060797b0977284980fd420fd63)) 

- *(gui)* Fetch billing profile on trial
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([0900de9](https://github.com///commit/0900de9307a2f5e36bef3c48758a76eeec11f452)) 

- *(gui)* Fixed contact descriptions
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([a013a00](https://github.com///commit/a013a0074da904d19d1ca01c9ad8dfef0382d083)) 

- *(gui)* Let users know about billing related issues
 ([00ac623](https://github.com///commit/00ac6232535cceaaef31cbbe7c5782024fe2f0dc)) 


  - to e.g. help identify rate limiting failures

- *(gui)* Fixed an issue that prevented showing billing errors
 ([06f0cec](https://github.com///commit/06f0cecd067917479b8249b362d5edfa317b89e4)) 

- *(gui)* Fall back to delta job count while pagination total isn't available
 ([79360cc](https://github.com///commit/79360cc0e91249c86e867eb766b9216dcd3f2fa9)) 

- *(tenantadm)* Ignore Stripe subscriptions not managed by this service
([MEN-8708](https://northerntech.atlassian.net/browse/MEN-8708)) ([4e8c712](https://github.com///commit/4e8c71200c16210da4349667c6b6003d6ca69f05)) 


  Instead of correlating events with customer ID, we correlate with
  subscription IDs. This is mostly to address a transient issue in the
  transition phase where a multi-subscription customer will have the
  subscriptions consolidated, but it also eliminates the need for
  additional database indexing to cover fast customer lookups.

- *(tenantadm)* Remove old "Upgrade from trial" API
([MEN-8763](https://northerntech.atlassian.net/browse/MEN-8763)) ([9a68228](https://github.com///commit/9a68228e6f34a4b6070020c104b1cea4e21b9c0c)) 


  The endpoint is superseded by the new self-service upgrade path.

- *(useradm)* Invalidate cache when deleting PAT token
([MEN-7285](https://northerntech.atlassian.net/browse/MEN-7285)) ([e05e898](https://github.com///commit/e05e898b7056c79aefad095b9e22f359dcfd1174)) 

- *(useradm)* Prevent race condition recaching revoked PAT token
 ([1564ec6](https://github.com///commit/1564ec6a452c366af2ea4069340e9173669aa4db)) 

- *(useradm)* Construct valid OIDC redirect_uri
 ([d67ed99](https://github.com///commit/d67ed9989bd0efbaa6b2319fc7e0569ec75e548e)) 

- *(useradm)* OIDC /login content-type is x-www-form-urlencoded
 ([8abe4a7](https://github.com///commit/8abe4a7f64d1cd6d806b15ebf48ae5368132335a)) 

- *(useradm)* Don't panic if optional OIDC claim `email` is missing
 ([2fea2c5](https://github.com///commit/2fea2c54b4251199cbd17dd78d6f83de81131f45)) 

- *(useradm)* Support GET requests to /oidc/:provider/login
 ([161822b](https://github.com///commit/161822b09fadf477bd9119076b8aa7ea30a6f8e1)) 


  If the OIDC IDP provider doesn't support response_mode=form_post
  (resolved by consulting the /.well-known/openid-configuration of the IDP) we
  default to response_mode=query in the URL generated by
  /oidc/:provider/start.
  
  The "query" response_mode implies that the HTTP
  method of the callback request should be `GET` and we must therefore
  support it.

- Upgrade backend golang version to 1.25.0
 ([d336b7d](https://github.com///commit/d336b7d3d160d8630112820f82b3a71b186de0a6)) 




### Documentation


- *(devicemonitor)* Added internal delete device endpoint to api docs
 ([85e5570](https://github.com///commit/85e557004ec26e1ad32e3e1b296d2391ba5c9a51)) 

- *(inventory)* Add clarity to list devices api docs
 ([c460380](https://github.com///commit/c46038013ba60510d2a45fcea66917be29642976)) 

- *(useradm)* API documentation for user feedback endpoint
 ([6bc4c29](https://github.com///commit/6bc4c298931e0b746ace659b6b3d375fb59c085c)) 

- *(useradm)* Fix swagger spec for feedback API
 ([828ed75](https://github.com///commit/828ed75ed01c2538d90dd30d0c67cf1b83d277f9)) 

- *(useradm)* Make API specs more consistent with enterprise
([MEN-8345](https://northerntech.atlassian.net/browse/MEN-8345)) ([1022949](https://github.com///commit/1022949e7df31ccb90b624d1c6ba411950c98634)) 

- *(useradm)* Make API specs more consistent with open source
([MEN-8345](https://northerntech.atlassian.net/browse/MEN-8345)) ([c900a1d](https://github.com///commit/c900a1d03aa6b941d84d2c380152b3615b5cbbad)) 





### Features


- *(deployments)* Added support for anthropic analysis backend
 ([0e71550](https://github.com///commit/0e715506bb4b23b5115a56ef7d5ad5d75a057847)) 

- *(devicemonitor)* Added internal delete device endpoint
 ([2cc83f6](https://github.com///commit/2cc83f6883c22b092139513105c08a91e66c4484)) 

- *(gui)* Let ai request cool down time reflect reality when rate limited
 ([92e8864](https://github.com///commit/92e8864a8c9d95991d17ad562877bc6e114ec727)) 

- *(gui)* Added execution feedback to troubleshooting device interactions
([MEN-8632](https://northerntech.atlassian.net/browse/MEN-8632)) ([e1e4074](https://github.com///commit/e1e4074581b787e9a7bf43943aba68cf9a4a4407)) 

- *(gui)* Let tenant sso setting inheritance conditions be more explicit
([MEN-8672](https://northerntech.atlassian.net/browse/MEN-8672)) ([76d4db9](https://github.com///commit/76d4db9a219758e21d357f487435cf106bbc62c6)) 

- *(gui)* Made it possible for tenants to allow improving ai functionality in the future
([MEN-8719](https://northerntech.atlassian.net/browse/MEN-8719)) ([c2dd114](https://github.com///commit/c2dd114e1ec2d2eeb8b33dc300d04de04d3861cd)) 

- *(gui)* Cosmetic subscription adjustments & typography usage
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([0d37587](https://github.com///commit/0d375876f258b8d1651e26fd593e054d23bbca10)) 

- *(gui)* Added special handling for non-stripe non-enterprise customers
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([3e99e17](https://github.com///commit/3e99e17765e2010f4feb95f30ce9658a398a36d0)) 

- *(gui)* Utilized AddonSelect for enterprise/non-stripe users
([MEN-8644](https://northerntech.atlassian.net/browse/MEN-8644)) ([13b7c79](https://github.com///commit/13b7c798a8d2815b33fb838bd021ca8541ed81f0)) 

- *(gui)* Switched to a new endpoint for user feedback
([MEN-7739](https://northerntech.atlassian.net/browse/MEN-7739)) ([e8dae0d](https://github.com///commit/e8dae0d247307b49f45f95c4d428c0671300ef7e)) 

- *(gui)* Adjusted ai feedback to use new feedback endpoint
([MEN-7739](https://northerntech.atlassian.net/browse/MEN-7739)) ([ec2a3f2](https://github.com///commit/ec2a3f2c0fd90c3d19a94207e6e05c5a9968b9b4)) 

- *(gui)* Added chinese server to login notifications
([MEN-8770](https://northerntech.atlassian.net/browse/MEN-8770)) ([ac933a0](https://github.com///commit/ac933a083e936486673d0eb8dc8c544350304493)) 

- *(gui)* Added improved success payment modal
([MEN-8703](https://northerntech.atlassian.net/browse/MEN-8703)) ([f56e4c6](https://github.com///commit/f56e4c64333876fce83b484baed36b0d7a27069b)) 

- *(gui)* Let confirmation modal to delay the logout after token invalidation
([MEN-8703](https://northerntech.atlassian.net/browse/MEN-8703)) ([2a1a71e](https://github.com///commit/2a1a71e76e4d029d030d01ea09e1c0753d783890)) 

- *(gui)* Added delta artifact generation job retrieval functionality
 ([66e577a](https://github.com///commit/66e577ad3872122a10f81627fa6518a2d985c3f5)) 

- *(gui)* Added a way to see details about delta generation jobs
([MEN-8250](https://northerntech.atlassian.net/browse/MEN-8250)) ([36c6adf](https://github.com///commit/36c6adfdaa51ff5a3ca243d691e290afbbcf9fce)) 

- *(gui)* Added overview of recent delta generation jobs
([MEN-8251](https://northerntech.atlassian.net/browse/MEN-8251)) ([0ca8799](https://github.com///commit/0ca8799dae18dca14f513fcb3ea48ca6335082f9)) 

- *(gui)* Let release upload be focused on releases view to reduce confusion
([MEN-8248](https://northerntech.atlassian.net/browse/MEN-8248)) ([22bc53c](https://github.com///commit/22bc53c41293450cb880c58fa5fda847f861ffa5)) 

- *(useradm)* Require consent to enable AI features
([MEN-8677](https://northerntech.atlassian.net/browse/MEN-8677)) ([909a9bd](https://github.com///commit/909a9bd0b1c47b692014353599021d201e29a561)) 


  There is an explicit option for enabling AI features in the global
  settings (`aiFeatures.enabled`), requiring admin access to allow
  using the feature.

- *(useradm)* New endpoint for submitting user feedback
([MEN-7603](https://northerntech.atlassian.net/browse/MEN-7603)) ([2f73a24](https://github.com///commit/2f73a24cb9217d8cea65561bb4f3bdeff786f80b)) 


  POST /api/management/v2/useradm/support/feedback/:form_id
  
  The new endpoint accepts a form response with user feedback. There are
  currently two `form_id` defined: "product" and "feat.ai" for general
  product feedback and feedback specific to the experimental AI feature.

- *(useradm)* Send email notifications on password or email change
([MEN-8676](https://northerntech.atlassian.net/browse/MEN-8676)) ([9472690](https://github.com///commit/94726900cb732f6903bc35dec73e01e2943817f7)) 

- *(workflows)* Delete devicemonitor device when decommissioning devices
 ([6a25915](https://github.com///commit/6a25915ecac07346111c9f30af0d4cd12e5d03a9)) 

- *(workflows)* New workflow for sending email when user is changing email
([MEN-8676](https://northerntech.atlassian.net/browse/MEN-8676)) ([48ec7e6](https://github.com///commit/48ec7e674e275ebcbfaa5ea0b62a68fa61866e6a)) 

- *(workflows)* New workflow for sending email when user is changing password
([MEN-8676](https://northerntech.atlassian.net/browse/MEN-8676)) ([f152900](https://github.com///commit/f152900e34f1e03e6128da37265b1ee421b1888c)) 





### Refactor


- *(deviceauth)* Remove tenantadm related code from OS
([MEN-8649](https://northerntech.atlassian.net/browse/MEN-8649)) ([31b9d2b](https://github.com///commit/31b9d2beeb60a4485449f620ca58df580ba1cae9)) 





### Security


- Bump mermaid from 11.9.0 to 11.10.1 in /frontend
 ([f20bb82](https://github.com///commit/f20bb82e79c924b12017a2eabdadd347e85cfae8)) 


  Bumps [mermaid](https://github.com/mermaid-js/mermaid) from 11.9.0 to 11.10.1.
  - [Release notes](https://github.com/mermaid-js/mermaid/releases)
  - [Commits](https://github.com/mermaid-js/mermaid/compare/mermaid@11.9.0...mermaid@11.10.1)
  
  ---
  updated-dependencies:
  - dependency-name: mermaid
    dependency-version: 11.10.1
    dependency-type: indirect
  ...
- Bump the mui group in /frontend with 3 updates
 ([d6671fa](https://github.com///commit/d6671fa9230cee890831fe47877c5a68e9dcb6ed)) 


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.2.0 to 7.3.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.1/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.2.0 to 7.3.1
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.1/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.9.2 to 8.11.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.11.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the development-dependencies group
 ([ee210fa](https://github.com///commit/ee210fae283177c0360da33513d54e11cff1a6b3)) 


  Bumps the development-dependencies group in /frontend with 12 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/eslint-config](https://github.com/NorthernTechHQ/nt-gui) | `0.6.0` | `0.6.1` |
  | [@northern.tech/themes](https://github.com/NorthernTechHQ/nt-gui) | `0.3.0` | `0.3.1` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.4.11` | `1.5.1` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.4.11` | `1.5.1` |
  | [@rspack/plugin-react-refresh](https://github.com/rspack-contrib/rspack-plugin-react-refresh) | `1.4.3` | `1.5.0` |
  | [@sentry/webpack-plugin](https://github.com/getsentry/sentry-javascript-bundler-plugins) | `4.1.1` | `4.2.0` |
  | [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) | `6.7.0` | `6.8.0` |
  | [@typescript-eslint/eslint-plugin](https://github.com/typescript-eslint/typescript-eslint/tree/HEAD/packages/eslint-plugin) | `8.39.1` | `8.41.0` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.0.0` | `5.0.2` |
  | [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) | `3.45.0` | `3.45.1` |
  | [undici](https://github.com/nodejs/undici) | `7.14.0` | `7.15.0` |
  | [vite-plugin-svgr](https://github.com/pd4d10/vite-plugin-svgr) | `4.3.0` | `4.5.0` |
  
  
  Updates `@northern.tech/eslint-config` from 0.6.0 to 0.6.1
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/eslint-config-0.6.0...@northern.tech/eslint-config-0.6.1)
  
  Updates `@northern.tech/themes` from 0.3.0 to 0.3.1
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/themes-0.3.0...@northern.tech/themes-0.3.1)
  
  Updates `@rspack/cli` from 1.4.11 to 1.5.1
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.1/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.4.11 to 1.5.1
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.1/packages/rspack)
  
  Updates `@rspack/plugin-react-refresh` from 1.4.3 to 1.5.0
  - [Release notes](https://github.com/rspack-contrib/rspack-plugin-react-refresh/releases)
  - [Commits](https://github.com/rspack-contrib/rspack-plugin-react-refresh/compare/v1.4.3...v1.5.0)
  
  Updates `@sentry/webpack-plugin` from 4.1.1 to 4.2.0
  - [Release notes](https://github.com/getsentry/sentry-javascript-bundler-plugins/releases)
  - [Changelog](https://github.com/getsentry/sentry-javascript-bundler-plugins/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/getsentry/sentry-javascript-bundler-plugins/compare/4.1.1...4.2.0)
  
  Updates `@testing-library/jest-dom` from 6.7.0 to 6.8.0
  - [Release notes](https://github.com/testing-library/jest-dom/releases)
  - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/testing-library/jest-dom/compare/v6.7.0...v6.8.0)
  
  Updates `@typescript-eslint/eslint-plugin` from 8.39.1 to 8.41.0
  - [Release notes](https://github.com/typescript-eslint/typescript-eslint/releases)
  - [Changelog](https://github.com/typescript-eslint/typescript-eslint/blob/main/packages/eslint-plugin/CHANGELOG.md)
  - [Commits](https://github.com/typescript-eslint/typescript-eslint/commits/v8.41.0/packages/eslint-plugin)
  
  Updates `@vitejs/plugin-react` from 5.0.0 to 5.0.2
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.0.2/packages/plugin-react)
  
  Updates `core-js` from 3.45.0 to 3.45.1
  - [Release notes](https://github.com/zloirock/core-js/releases)
  - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/zloirock/core-js/commits/v3.45.1/packages/core-js)
  
  Updates `undici` from 7.14.0 to 7.15.0
  - [Release notes](https://github.com/nodejs/undici/releases)
  - [Commits](https://github.com/nodejs/undici/compare/v7.14.0...v7.15.0)
  
  Updates `vite-plugin-svgr` from 4.3.0 to 4.5.0
  - [Release notes](https://github.com/pd4d10/vite-plugin-svgr/releases)
  - [Commits](https://github.com/pd4d10/vite-plugin-svgr/compare/v4.3.0...v4.5.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/eslint-config"
    dependency-version: 0.6.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@northern.tech/themes"
    dependency-version: 0.3.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.5.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.5.1
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/plugin-react-refresh"
    dependency-version: 1.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.2.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@testing-library/jest-dom"
    dependency-version: 6.8.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.41.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.0.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.45.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.15.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vite-plugin-svgr
    dependency-version: 4.5.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 2 directories with 9 updates
 ([ea1783d](https://github.com///commit/ea1783dc61fc1c19a522c2118ca182ec5b899c22)) 


  Bumps the backend-tests-python-dependencies group with 1 update in the /backend/services/iot-manager/tests directory: [requests](https://github.com/psf/requests).
  Bumps the backend-tests-python-dependencies group with 9 updates in the /backend/tests directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [pymongo](https://github.com/mongodb/mongo-python-driver) | `4.13.2` | `4.14.1` |
  | [certifi](https://github.com/certifi/python-certifi) | `2025.7.14` | `2025.8.3` |
  | [requests](https://github.com/psf/requests) | `2.32.4` | `2.32.5` |
  | [azure-iot-hub](https://github.com/Azure/azure-iot-hub-python) | `2.6.1` | `2.7.0` |
  | [boto3](https://github.com/boto/boto3) | `1.40.0` | `1.40.21` |
  | [cryptography](https://github.com/pyca/cryptography) | `45.0.5` | `45.0.7` |
  | [filelock](https://github.com/tox-dev/py-filelock) | `3.18.0` | `3.19.1` |
  | [stripe](https://github.com/stripe/stripe-python) | `12.4.0` | `12.5.0` |
  | [redis](https://github.com/redis/redis-py) | `6.2.0` | `6.4.0` |
  
  
  
  Updates `requests` from 2.32.4 to 2.32.5
  - [Release notes](https://github.com/psf/requests/releases)
  - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
  - [Commits](https://github.com/psf/requests/compare/v2.32.4...v2.32.5)
  
  Updates `pymongo` from 4.13.2 to 4.14.1
  - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
  - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
  - [Commits](https://github.com/mongodb/mongo-python-driver/compare/4.13.2...4.14.1)
  
  Updates `certifi` from 2025.7.14 to 2025.8.3
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.07.14...2025.08.03)
  
  Updates `requests` from 2.32.4 to 2.32.5
  - [Release notes](https://github.com/psf/requests/releases)
  - [Changelog](https://github.com/psf/requests/blob/main/HISTORY.md)
  - [Commits](https://github.com/psf/requests/compare/v2.32.4...v2.32.5)
  
  Updates `azure-iot-hub` from 2.6.1 to 2.7.0
  - [Changelog](https://github.com/Azure/azure-iot-hub-python/blob/main/RELEASE%20INSTRUCTIONS.md)
  - [Commits](https://github.com/Azure/azure-iot-hub-python/commits)
  
  Updates `boto3` from 1.40.0 to 1.40.21
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.0...1.40.21)
  
  Updates `cryptography` from 45.0.5 to 45.0.7
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/45.0.5...45.0.7)
  
  Updates `filelock` from 3.18.0 to 3.19.1
  - [Release notes](https://github.com/tox-dev/py-filelock/releases)
  - [Changelog](https://github.com/tox-dev/filelock/blob/main/docs/changelog.rst)
  - [Commits](https://github.com/tox-dev/py-filelock/compare/3.18.0...3.19.1)
  
  Updates `stripe` from 12.4.0 to 12.5.0
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v12.4.0...v12.5.0)
  
  Updates `redis` from 6.2.0 to 6.4.0
  - [Release notes](https://github.com/redis/redis-py/releases)
  - [Changelog](https://github.com/redis/redis-py/blob/master/CHANGES)
  - [Commits](https://github.com/redis/redis-py/compare/v6.2.0...v6.4.0)
  
  ---
  updated-dependencies:
  - dependency-name: requests
    dependency-version: 2.32.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.14.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.8.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: requests
    dependency-version: 2.32.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: azure-iot-hub
    dependency-version: 2.7.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.21
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 45.0.7
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: filelock
    dependency-version: 3.19.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 12.5.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: redis
    dependency-version: 6.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([690e8c8](https://github.com///commit/690e8c8eca26aab215d5c3d401b411d45160935b)) 


  Bumps the backend-golang-dependencies group in /backend with 16 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.18.2` | `1.19.0` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.37.1` | `1.38.3` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.30.2` | `1.31.6` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.18.2` | `1.18.10` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.66.0` | `1.69.1` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.28.1` | `1.32.2` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.85.1` | `1.87.3` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.7` | `2.11.8` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.44.0` | `1.45.0` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.11.0` | `9.12.1` |
  | [github.com/spf13/cobra](https://github.com/spf13/cobra) | `1.9.1` | `1.10.1` |
  | [github.com/stretchr/testify](https://github.com/stretchr/testify) | `1.10.0` | `1.11.1` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.40.0` | `0.41.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.42.0` | `0.43.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.34.0` | `0.35.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.33.0` | `0.34.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.18.2 to 1.19.0
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/sdk-breaking-changes-guide-migration.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.18.2...sdk/azcore/v1.19.0)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.37.1 to 1.38.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.37.1...v1.38.3)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.30.2 to 1.31.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.30.2...config/v1.31.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.2 to 1.18.10
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.2...config/v1.18.10)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.66.0 to 1.69.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.66.0...service/iot/v1.69.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.28.1 to 1.32.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.28.1...v1.32.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.85.1 to 1.87.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.85.1...service/s3/v1.87.3)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.7 to 2.11.8
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.7...v2.11.8)
  
  Updates `github.com/nats-io/nats.go` from 1.44.0 to 1.45.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.44.0...v1.45.0)
  
  Updates `github.com/redis/go-redis/v9` from 9.11.0 to 9.12.1
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.11.0...v9.12.1)
  
  Updates `github.com/spf13/cobra` from 1.9.1 to 1.10.1
  - [Release notes](https://github.com/spf13/cobra/releases)
  - [Commits](https://github.com/spf13/cobra/compare/v1.9.1...v1.10.1)
  
  Updates `github.com/stretchr/testify` from 1.10.0 to 1.11.1
  - [Release notes](https://github.com/stretchr/testify/releases)
  - [Commits](https://github.com/stretchr/testify/compare/v1.10.0...v1.11.1)
  
  Updates `golang.org/x/crypto` from 0.40.0 to 0.41.0
  - [Commits](https://github.com/golang/crypto/compare/v0.40.0...v0.41.0)
  
  Updates `golang.org/x/net` from 0.42.0 to 0.43.0
  - [Commits](https://github.com/golang/net/compare/v0.42.0...v0.43.0)
  
  Updates `golang.org/x/sys` from 0.34.0 to 0.35.0
  - [Commits](https://github.com/golang/sys/compare/v0.34.0...v0.35.0)
  
  Updates `golang.org/x/term` from 0.33.0 to 0.34.0
  - [Commits](https://github.com/golang/term/compare/v0.33.0...v0.34.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.19.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.38.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.6
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.10
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.87.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.8
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.45.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.12.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/spf13/cobra
    dependency-version: 1.10.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/stretchr/testify
    dependency-version: 1.11.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.41.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.43.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.35.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.34.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump the e2e-test-dependencies group
 ([3810c06](https://github.com///commit/3810c06373de41fa923bf9d2ac206bc37fd762e9)) 


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 2 updates: [dayjs](https://github.com/iamkun/dayjs) and [yaml](https://github.com/eemeli/yaml).
  
  
  Updates `dayjs` from 1.11.13 to 1.11.18
  - [Release notes](https://github.com/iamkun/dayjs/releases)
  - [Changelog](https://github.com/iamkun/dayjs/blob/v1.11.18/CHANGELOG.md)
  - [Commits](https://github.com/iamkun/dayjs/compare/v1.11.13...v1.11.18)
  
  Updates `yaml` from 2.8.0 to 2.8.1
  - [Release notes](https://github.com/eemeli/yaml/releases)
  - [Commits](https://github.com/eemeli/yaml/compare/v2.8.0...v2.8.1)
  
  ---
  updated-dependencies:
  - dependency-name: dayjs
    dependency-version: 1.11.18
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: yaml
    dependency-version: 2.8.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  ...
- Bump @playwright/test
 ([57a1922](https://github.com///commit/57a1922e84a64935cdb3305a03a51678a48585af)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.54.2 to 1.55.0
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.54.2...v1.55.0)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.55.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump github.com/redis/go-redis/v9
 ([ee255e2](https://github.com///commit/ee255e2351698964d064b4fa0b7bac2efa3c9d7f)) 


  Bumps the backend-golang-dependencies group in /backend with 1 update: [github.com/redis/go-redis/v9](https://github.com/redis/go-redis).
  
  
  Updates `github.com/redis/go-redis/v9` from 9.12.1 to 9.13.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.12.1...v9.13.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.13.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 2 updates
 ([b1fb007](https://github.com///commit/b1fb0078c69f82c459bcfe5753f84d72355556f2)) 


  Bumps the backend-tests-python-dependencies group with 2 updates in the /backend/tests directory: [pytest](https://github.com/pytest-dev/pytest) and [boto3](https://github.com/boto/boto3).
  
  
  Updates `pytest` from 8.4.1 to 8.4.2
  - [Release notes](https://github.com/pytest-dev/pytest/releases)
  - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pytest/compare/8.4.1...8.4.2)
  
  Updates `boto3` from 1.40.21 to 1.40.24
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.21...1.40.24)
  
  ---
  updated-dependencies:
  - dependency-name: pytest
    dependency-version: 8.4.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.24
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  ...
- Bump vite from 7.0.6 to 7.1.5 in /frontend
 ([fd3c822](https://github.com///commit/fd3c8223d58894792976e2ac08eaf05d5f61d31c)) 


  Bumps [vite](https://github.com/vitejs/vite/tree/HEAD/packages/vite) from 7.0.6 to 7.1.5.
  - [Release notes](https://github.com/vitejs/vite/releases)
  - [Changelog](https://github.com/vitejs/vite/blob/main/packages/vite/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite/commits/v7.1.5/packages/vite)
  
  ---
  updated-dependencies:
  - dependency-name: vite
    dependency-version: 7.1.5
    dependency-type: indirect
  ...
- Bump axios from 1.11.0 to 1.12.0 in /frontend
 ([b460d89](https://github.com///commit/b460d8916f2562686675b8d327a7974901a0ddc4)) 


  Bumps [axios](https://github.com/axios/axios) from 1.11.0 to 1.12.0.
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.11.0...v1.12.0)
  
  ---
  updated-dependencies:
  - dependency-name: axios
    dependency-version: 1.12.0
    dependency-type: direct:production
  ...
- Bump the backend-docker-compose-dependencies group across 2 directories with 4 updates
 ([020619a](https://github.com///commit/020619a35768dd1682f5128a8a98bcaa07e59819)) 


  Bumps the backend-docker-compose-dependencies group with 2 updates in the / directory: traefik and nats.
  Bumps the backend-docker-compose-dependencies group with 2 updates in the /compose directory: redis and chrislusf/seaweedfs.
  
  
  Updates `traefik` from v3.1 to 3.5
  
  Updates `nats` from 2.10 to 2.11
  
  Updates `redis` from 7.2 to 8.2
  
  Updates `chrislusf/seaweedfs` from 3.85 to 3.97
  
  ---
  updated-dependencies:
  - dependency-name: traefik
    dependency-version: '3.5'
    dependency-type: direct:production
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: nats
    dependency-version: '2.11'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: redis
    dependency-version: '8.2'
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: chrislusf/seaweedfs
    dependency-version: '3.97'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...

- Bump axios from 1.11.0 to 1.12.0 in /frontend
 ([b460d89](https://github.com///commit/b460d8916f2562686675b8d327a7974901a0ddc4)) 


  Bumps [axios](https://github.com/axios/axios) from 1.11.0 to 1.12.0.
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.11.0...v1.12.0)
  
  ---
  updated-dependencies:
  - dependency-name: axios
    dependency-version: 1.12.0
    dependency-type: direct:production
  ...
- Bump the e2e-test-dependencies group
 ([116338d](https://github.com///commit/116338df1b4a36e2f9d339bd0e608c5826ddd00f)) 


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 6 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [chalk](https://github.com/chalk/chalk) | `5.5.0` | `5.6.2` |
  | [commander](https://github.com/tj/commander.js) | `14.0.0` | `14.0.1` |
  | [docker-compose](https://github.com/PDMLab/docker-compose) | `1.2.0` | `1.3.0` |
  | [inquirer](https://github.com/SBoudrias/Inquirer.js) | `12.9.1` | `12.9.6` |
  | [ora](https://github.com/sindresorhus/ora) | `8.2.0` | `9.0.0` |
  | [uuid](https://github.com/uuidjs/uuid) | `11.1.0` | `13.0.0` |
  
  
  Updates `chalk` from 5.5.0 to 5.6.2
  - [Release notes](https://github.com/chalk/chalk/releases)
  - [Commits](https://github.com/chalk/chalk/compare/v5.5.0...v5.6.2)
  
  Updates `commander` from 14.0.0 to 14.0.1
  - [Release notes](https://github.com/tj/commander.js/releases)
  - [Changelog](https://github.com/tj/commander.js/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/tj/commander.js/compare/v14.0.0...v14.0.1)
  
  Updates `docker-compose` from 1.2.0 to 1.3.0
  - [Changelog](https://github.com/PDMLab/docker-compose/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/PDMLab/docker-compose/compare/v1.2.0...v1.3.0)
  
  Updates `inquirer` from 12.9.1 to 12.9.6
  - [Release notes](https://github.com/SBoudrias/Inquirer.js/releases)
  - [Commits](https://github.com/SBoudrias/Inquirer.js/compare/inquirer@12.9.1...inquirer@12.9.6)
  
  Updates `ora` from 8.2.0 to 9.0.0
  - [Release notes](https://github.com/sindresorhus/ora/releases)
  - [Commits](https://github.com/sindresorhus/ora/compare/v8.2.0...v9.0.0)
  
  Updates `uuid` from 11.1.0 to 13.0.0
  - [Release notes](https://github.com/uuidjs/uuid/releases)
  - [Changelog](https://github.com/uuidjs/uuid/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/uuidjs/uuid/compare/v11.1.0...v13.0.0)
  
  ---
  updated-dependencies:
  - dependency-name: chalk
    dependency-version: 5.6.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  - dependency-name: commander
    dependency-version: 14.0.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: docker-compose
    dependency-version: 1.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  - dependency-name: inquirer
    dependency-version: 12.9.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: e2e-test-dependencies
  - dependency-name: ora
    dependency-version: 9.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: e2e-test-dependencies
  - dependency-name: uuid
    dependency-version: 13.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: e2e-test-dependencies
  ...
- Bump the backend-docker-compose-dependencies group across 2 directories with 4 updates
 ([020619a](https://github.com///commit/020619a35768dd1682f5128a8a98bcaa07e59819)) 


  Bumps the backend-docker-compose-dependencies group with 2 updates in the / directory: traefik and nats.
  Bumps the backend-docker-compose-dependencies group with 2 updates in the /compose directory: redis and chrislusf/seaweedfs.
  
  
  Updates `traefik` from v3.1 to 3.5
  
  Updates `nats` from 2.10 to 2.11
  
  Updates `redis` from 7.2 to 8.2
  
  Updates `chrislusf/seaweedfs` from 3.85 to 3.97
  
  ---
  updated-dependencies:
  - dependency-name: traefik
    dependency-version: '3.5'
    dependency-type: direct:production
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: nats
    dependency-version: '2.11'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: redis
    dependency-version: '8.2'
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-docker-compose-dependencies
  - dependency-name: chrislusf/seaweedfs
    dependency-version: '3.97'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the development-dependencies group
 ([6787079](https://github.com///commit/6787079c949751de4246b708078cabbd10a6d602)) 


  Bumps the development-dependencies group in /frontend with 9 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [@northern.tech/themes](https://github.com/NorthernTechHQ/nt-gui) | `0.6.1` | `0.6.2` |
  | [@rspack/cli](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack-cli) | `1.5.3` | `1.5.6` |
  | [@rspack/core](https://github.com/web-infra-dev/rspack/tree/HEAD/packages/rspack) | `1.5.3` | `1.5.6` |
  | [@types/node](https://github.com/DefinitelyTyped/DefinitelyTyped/tree/HEAD/types/node) | `24.3.1` | `24.5.2` |
  | [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/tree/HEAD/packages/plugin-react) | `5.0.2` | `5.0.3` |
  | [eslint](https://github.com/eslint/eslint) | `9.35.0` | `9.36.0` |
  | [jsdom](https://github.com/jsdom/jsdom) | `26.1.0` | `27.0.0` |
  | [lint-staged](https://github.com/lint-staged/lint-staged) | `16.1.6` | `16.2.0` |
  | [msw](https://github.com/mswjs/msw) | `2.11.2` | `2.11.3` |
  
  
  Updates `@northern.tech/themes` from 0.6.1 to 0.6.2
  - [Release notes](https://github.com/NorthernTechHQ/nt-gui/releases)
  - [Changelog](https://github.com/NorthernTechHQ/nt-gui/blob/main/release-please-config.json)
  - [Commits](https://github.com/NorthernTechHQ/nt-gui/compare/@northern.tech/themes-0.6.1...@northern.tech/themes-0.6.2)
  
  Updates `@rspack/cli` from 1.5.3 to 1.5.6
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.6/packages/rspack-cli)
  
  Updates `@rspack/core` from 1.5.3 to 1.5.6
  - [Release notes](https://github.com/web-infra-dev/rspack/releases)
  - [Commits](https://github.com/web-infra-dev/rspack/commits/v1.5.6/packages/rspack)
  
  Updates `@types/node` from 24.3.1 to 24.5.2
  - [Release notes](https://github.com/DefinitelyTyped/DefinitelyTyped/releases)
  - [Commits](https://github.com/DefinitelyTyped/DefinitelyTyped/commits/HEAD/types/node)
  
  Updates `@vitejs/plugin-react` from 5.0.2 to 5.0.3
  - [Release notes](https://github.com/vitejs/vite-plugin-react/releases)
  - [Changelog](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite-plugin-react/commits/plugin-react@5.0.3/packages/plugin-react)
  
  Updates `eslint` from 9.35.0 to 9.36.0
  - [Release notes](https://github.com/eslint/eslint/releases)
  - [Changelog](https://github.com/eslint/eslint/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/eslint/eslint/compare/v9.35.0...v9.36.0)
  
  Updates `jsdom` from 26.1.0 to 27.0.0
  - [Release notes](https://github.com/jsdom/jsdom/releases)
  - [Changelog](https://github.com/jsdom/jsdom/blob/main/Changelog.md)
  - [Commits](https://github.com/jsdom/jsdom/compare/26.1.0...27.0.0)
  
  Updates `lint-staged` from 16.1.6 to 16.2.0
  - [Release notes](https://github.com/lint-staged/lint-staged/releases)
  - [Changelog](https://github.com/lint-staged/lint-staged/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/lint-staged/lint-staged/compare/v16.1.6...v16.2.0)
  
  Updates `msw` from 2.11.2 to 2.11.3
  - [Release notes](https://github.com/mswjs/msw/releases)
  - [Changelog](https://github.com/mswjs/msw/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/mswjs/msw/compare/v2.11.2...v2.11.3)
  
  ---
  updated-dependencies:
  - dependency-name: "@northern.tech/themes"
    dependency-version: 0.6.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/cli"
    dependency-version: 1.5.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.5.6
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.5.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 5.0.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: eslint
    dependency-version: 9.36.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: jsdom
    dependency-version: 27.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.2.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.11.3
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  ...
- Bump the mui group in /frontend with 3 updates
 ([544749d](https://github.com///commit/544749d86c093b643f1ebd2e5aa8f4b473a70f69)) 


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.3.1 to 7.3.2
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.2/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.3.1 to 7.3.2
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.3.2/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 8.11.0 to 8.11.3
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.11.3/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.3.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.3.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.11.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  ...
- Bump the backend-tests-python-dependencies group across 1 directory with 2 updates
 ([b1fb007](https://github.com///commit/b1fb0078c69f82c459bcfe5753f84d72355556f2)) 


  Bumps the backend-tests-python-dependencies group with 2 updates in the /backend/tests directory: [pytest](https://github.com/pytest-dev/pytest) and [boto3](https://github.com/boto/boto3).
  
  
  Updates `pytest` from 8.4.1 to 8.4.2
  - [Release notes](https://github.com/pytest-dev/pytest/releases)
  - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pytest-dev/pytest/compare/8.4.1...8.4.2)
  
  Updates `boto3` from 1.40.21 to 1.40.24
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.40.21...1.40.24)
  
  ---
  updated-dependencies:
  - dependency-name: pytest
    dependency-version: 8.4.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.40.24
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  ...
- Bump @playwright/test
 ([7489159](https://github.com///commit/748915946dc8b598ce2918fa65df8fdbc8fc945c)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.55.0 to 1.55.1
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.55.0...v1.55.1)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.55.1
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: playwright
  ...
- Bump nats
 ([6ef8f84](https://github.com///commit/6ef8f840f0b80bddfcaf20b5a3a13bf112873d68)) 


  Bumps the backend-docker-compose-dependencies group with 1 update in the / directory: nats.
  
  
  Updates `nats` from 2.11 to 2.12
  
  ---
  updated-dependencies:
  - dependency-name: nats
    dependency-version: '2.12'
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-docker-compose-dependencies
  ...
- Bump the backend-golang-dependencies group across 1 directory with 17 updates
 ([9e22c80](https://github.com///commit/9e22c80c9521fb3d9e782f7922e97610f6e361f5)) 


  Bumps the backend-golang-dependencies group with 12 updates in the /backend directory:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.19.0` | `1.19.1` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.38.3` | `1.39.2` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.31.6` | `1.31.12` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.69.1` | `1.69.5` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.32.2` | `1.32.6` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.87.3` | `1.88.3` |
  | [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) | `1.10.1` | `1.11.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.8` | `2.12.0` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.45.0` | `1.46.1` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.13.0` | `9.14.0` |
  | [github.com/spf13/viper](https://github.com/spf13/viper) | `1.20.1` | `1.21.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.43.0` | `0.44.0` |
  
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.19.0 to 1.19.1
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/sdk-breaking-changes-guide-migration.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.19.0...sdk/azcore/v1.19.1)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.38.3 to 1.39.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.38.3...v1.39.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.31.6 to 1.31.12
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.31.6...config/v1.31.12)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.18.10 to 1.18.16
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.18.10...config/v1.18.16)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.69.1 to 1.69.5
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.69.1...service/iot/v1.69.5)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.32.2 to 1.32.6
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.32.2...v1.32.6)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.87.3 to 1.88.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.87.3...service/s3/v1.88.3)
  
  Updates `github.com/gin-gonic/gin` from 1.10.1 to 1.11.0
  - [Release notes](https://github.com/gin-gonic/gin/releases)
  - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/gin-gonic/gin/compare/v1.10.1...v1.11.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.8 to 2.12.0
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.8...v2.12.0)
  
  Updates `github.com/nats-io/nats.go` from 1.45.0 to 1.46.1
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.45.0...v1.46.1)
  
  Updates `github.com/redis/go-redis/v9` from 9.13.0 to 9.14.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/RELEASE-NOTES.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.13.0...v9.14.0)
  
  Updates `github.com/spf13/viper` from 1.20.1 to 1.21.0
  - [Release notes](https://github.com/spf13/viper/releases)
  - [Commits](https://github.com/spf13/viper/compare/v1.20.1...v1.21.0)
  
  Updates `golang.org/x/crypto` from 0.41.0 to 0.42.0
  - [Commits](https://github.com/golang/crypto/compare/v0.41.0...v0.42.0)
  
  Updates `golang.org/x/net` from 0.43.0 to 0.44.0
  - [Commits](https://github.com/golang/net/compare/v0.43.0...v0.44.0)
  
  Updates `golang.org/x/sys` from 0.35.0 to 0.36.0
  - [Commits](https://github.com/golang/sys/compare/v0.35.0...v0.36.0)
  
  Updates `golang.org/x/term` from 0.34.0 to 0.35.0
  - [Commits](https://github.com/golang/term/compare/v0.34.0...v0.35.0)
  
  Updates `golang.org/x/time` from 0.12.0 to 0.13.0
  - [Commits](https://github.com/golang/time/compare/v0.12.0...v0.13.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.19.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.39.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.31.12
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.16
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.69.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.32.6
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.88.3
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/gin-gonic/gin
    dependency-version: 1.11.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.12.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.46.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.14.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/spf13/viper
    dependency-version: 1.21.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.44.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.36.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.35.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/time
    dependency-version: 0.13.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
- Bump github.com/quic-go/quic-go from 0.54.0 to 0.54.1 in /backend
 ([27df7d6](https://github.com///commit/27df7d6bee416bec25b8fda09c445ad0740bca6a)) 


  Bumps [github.com/quic-go/quic-go](https://github.com/quic-go/quic-go) from 0.54.0 to 0.54.1.
  - [Release notes](https://github.com/quic-go/quic-go/releases)
  - [Commits](https://github.com/quic-go/quic-go/compare/v0.54.0...v0.54.1)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/quic-go/quic-go
    dependency-version: 0.54.1
    dependency-type: indirect
  ...
- Bump vite from 7.1.5 to 7.1.11 in /frontend
 ([0839758](https://github.com///commit/08397583bcd1c3e9df9efdc054a05137bec9f9bc)) 


  Bumps [vite](https://github.com/vitejs/vite/tree/HEAD/packages/vite) from 7.1.5 to 7.1.11.
  - [Release notes](https://github.com/vitejs/vite/releases)
  - [Changelog](https://github.com/vitejs/vite/blob/main/packages/vite/CHANGELOG.md)
  - [Commits](https://github.com/vitejs/vite/commits/v7.1.11/packages/vite)
  
  ---
  updated-dependencies:
  - dependency-name: vite
    dependency-version: 7.1.11
    dependency-type: indirect
  ...






## v4.1.0-saas.13 - 2025-08-16


### Bug fixes


- *(deployments)* Wrong version on delta/jobs endpoints
 ([5c64290](https://github.com///commit/5c6429007b7331a49c137c95ab3fed5d9deaf09b)) 

- *(workflows)* Move inventory to end of decommission workflow
 ([355fcd9](https://github.com///commit/355fcd91eeb0a0e3cd5d2fb4005d213b00b2a524)) 


  To lower the probability of failed decommission causing the device not
  to show up in the UI. By not removing the device from inventory it is
  possible to initiate the retry from the UI.





### Documentation


- *(useradm)* Move API specification to single file
([QA-1094](https://northerntech.atlassian.net/browse/QA-1094)) ([9bcf6cf](https://github.com///commit/9bcf6cf82123f35dc0a0ff7869d0bcd30869aeff)) 





### Features


- *(workflows)* Support both pull and push mode consumer
([MEN-8326](https://northerntech.atlassian.net/browse/MEN-8326)) ([4a93316](https://github.com///commit/4a9331623ffcd19435620ff845c788d3a0e869e2)) 

- *(workflows)* Add CLI flag to migrate consumers from push to pull mode
 ([8b9a9a2](https://github.com///commit/8b9a9a2aeb9dc9406dab6497594d94d156f510e1)) 





### Security


- Bump the backend-tests-python-dependencies group across 1 directory with 4 updates
 ([43f7d7f](https://github.com///commit/43f7d7f647d31124d0d6497e8d10862202f66536)) 


  Bumps the backend-tests-python-dependencies group with 4 updates in the /backend/tests directory: [boto3](https://github.com/boto/boto3), [certifi](https://github.com/certifi/python-certifi), [cryptography](https://github.com/pyca/cryptography) and [stripe](https://github.com/stripe/stripe-python).
  
  
  Updates `boto3` from 1.39.0 to 1.40.0
  - [Release notes](https://github.com/boto/boto3/releases)
  - [Commits](https://github.com/boto/boto3/compare/1.39.0...1.40.0)
  
  Updates `certifi` from 2025.6.15 to 2025.7.14
  - [Commits](https://github.com/certifi/python-certifi/compare/2025.06.15...2025.07.14)
  
  Updates `cryptography` from 45.0.4 to 45.0.5
  - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
  - [Commits](https://github.com/pyca/cryptography/compare/45.0.4...45.0.5)
  
  Updates `stripe` from 12.2.0 to 12.4.0
  - [Release notes](https://github.com/stripe/stripe-python/releases)
  - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/stripe/stripe-python/compare/v12.2.0...v12.4.0)
  
  ---
  updated-dependencies:
  - dependency-name: boto3
    dependency-version: 1.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.7.14
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: cryptography
    dependency-version: 45.0.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 12.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  ...






## v4.1.0-saas.12 - 2025-08-12


### Bug fixes


- *(gui)* Reject configuration deployment with too long field length
([MEN-8123](https://northerntech.atlassian.net/browse/MEN-8123)) ([c95e30f](https://github.com///commit/c95e30fae4687dbf1b17e742c0ef3c5900384b01)) 

- *(gui)* Prevented a situation that created the appearance we support multiple integrations
 ([1dba715](https://github.com///commit/1dba715184b01835b42dc09001fab29d506b4754)) 

- *(gui)* Let artifact type filtering no longer autoselect an option to reduce user confusion
 ([f77aaee](https://github.com///commit/f77aaeeaf164d7310f2456c629c03cc3ab416192)) 

- *(gui)* Fixed an issue that prevented showing details of a auditlogged portforward session
 ([a807849](https://github.com///commit/a807849137af0a2470e2a0bbb4d53d1f3e7b25a2)) 


  - extracted the shared logic to a reusable hook to improve reusability of the working approach

- *(gui)* Adjusted price parsing for the new stripe configuration
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([951d3af](https://github.com///commit/951d3af8c1509fb7bfebaa913428d9c5466e672a)) 

- *(gui)* Adjusted billing page for older customers to exclude upgrade page
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([2c0de68](https://github.com///commit/2c0de680085518b5cabea33db73543986de61725)) 

- *(gui)* Aligned license report download location w/ backend expectation
([MEN-8447](https://northerntech.atlassian.net/browse/MEN-8447)) ([4a638e2](https://github.com///commit/4a638e2bb9f48b7802fb4d5366a9cbc7bac7716f)) 

- *(gui)* Fixed an issue that would prevent showing updated pagination info in some situations
 ([989d785](https://github.com///commit/989d78577f7e79aa67508ed94f0da3fdb418b750)) 

- *(tenantadm)* `create-org` CLI correctly handles 404 response from workflows
 ([96b2ae2](https://github.com///commit/96b2ae2b58e2536997afb054e437384e4849225b)) 

- *(tenantadm)* Make plan bindings config path optional
 ([becc5f8](https://github.com///commit/becc5f8e170be87376ee4d406877e6876e10e65f)) 


  Hard-coded the defaults instead of always loading the file which may
  cause unnecessary headaches when trying to execute the binary without
  the config file in the right path.

- *(tenantadm)* Prevent creating child tenant without users
([MEN-8261](https://northerntech.atlassian.net/browse/MEN-8261)) ([01c3fee](https://github.com///commit/01c3fee5a5329eac587fa754f229a815d1282e35)) 

- *(useradm)* Validate User `sso` values with configured providers
([MEN-8513](https://northerntech.atlassian.net/browse/MEN-8513)) ([83e5abf](https://github.com///commit/83e5abf49da0b0f296d870cd9f320c693ae0a99f)) 

- *(useradm)* Use configured base URL for OAuth2 redirects
([MEN-8502](https://northerntech.atlassian.net/browse/MEN-8502)) ([aeb7deb](https://github.com///commit/aeb7deba0a88a77a835fa59d32fb0dc1f2d45072)) 


  Removes the use of X-Forwarded-Host when generating the redirect URL for
  OAuth2 login and instead rely on the configured value `base_url` (env:
  USERADM_BASE_URL).

- Allow user to see devices info when having read permission
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([758214b](https://github.com///commit/758214b50388aa996707caf088db2c3023a86196)) 


  If user have a read permission to a device group, allow the user to see
  the devices information in a deployment sent to the device group.
- Ensure the enterprise backend to return JSON on no method or route
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([b5426ae](https://github.com///commit/b5426ae6d89292e3e4fc414c4f30d355db3783e7)) 




### Documentation


- *(deployments)* Deprecate v1 GET `/artifacts/list` management endpoint
([MEN-8183](https://northerntech.atlassian.net/browse/MEN-8183)) ([2b308d5](https://github.com///commit/2b308d55b0f08bde3a6d845fa260587bac328d7f)) 

- *(workflows)* Prepare API specification in OpenAPI format
([QA-893](https://northerntech.atlassian.net/browse/QA-893)) ([0986835](https://github.com///commit/0986835db0a349d6ac776bc1fc95adc913c2e4f5)) 

- Adjusted documentation for release process
 ([3f8464f](https://github.com///commit/3f8464fb1e9fbf852d09446021706d91146ccee2)) 


  Tried to reword some of the sections as it is quite confusing which
  sections to follow and which to ignore for a hosted Mender release.
  I also made the first step optional, requiring only checking for
  critical fixes for the enterprise sync PRs.




### Features


- *(gui)* Added subscription page route
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([b4980a4](https://github.com///commit/b4980a4e8d63a11c9851ded8e1fcf4937db34155)) 

- *(gui)* Changed upgrade links to the new subscription page
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([215ae41](https://github.com///commit/215ae4173bc1cb89ecc1b5f6e551ee354de54cc0)) 

- *(gui)* Navigate user to a proper upgrade component depending on the current pricing
([MEN-8412](https://northerntech.atlassian.net/browse/MEN-8412)) ([a8d66a7](https://github.com///commit/a8d66a7c1ad6ac4aefacb4103c2db5e8093794df)) 

- *(tenantadm)* Extend functionality of internal endpoint for getting tenants
([MEN-8225](https://northerntech.atlassian.net/browse/MEN-8225)) ([56b77a2](https://github.com///commit/56b77a2f2dc395d2c4c80bbe393b5b4508793f3e)) 


  Make it possible to filter tenants by plan and trial fields and to specify which fields
  resulting objects should contain.

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([07d5b18](https://github.com///commit/07d5b18a1e7df6c710fad94d1d53c6173fadf013)) 


  Added the following configuration parameters:
  
  ```yaml
  ratelimits:
    # auth configures ratelimits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # reject_unmatched rejects requests that does not resolve to a
      # ratelimit group. That is, if either there's no api_pattern matching
      # the request or if the group_expression does not match a group.
      # Defaults to false - disable ratelimiting for unmatched requests.
      reject_unmatched: false
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups:
          # name defines the name of the group. The name is used in
          # match.group_expression to match an api_pattern with a group.
        - name: default
          # interval is the time interval when the rate limiter resets.
          interval: 1m
          # quota is the number of requests allowed in an interval.
          quota: 300
          # event_expression is a go template for grouping requests.
          # The following attributes are available in the context:
          # Identity - contains a subset of the JWT claims:
          # .Subject  (jwt:"sub")          string
          # .Tenant   (jwt:"mender.tenant") string
          # .Plan     (jwt:"mender.plan")   string
          # .Addons   (jwt:"mender.addons") []struct{Enabled bool; Name string}
          # .IsUser   (jwt:"mender.user")   bool
          # .IsDevice (jwt:"mender.device") bool
          # .Trial    (jwt:"mender.trial")  bool
          event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
          # More example groups:
      # - name: "example_slow_group_by_tenant"
      #   quota: 1
      #   interval: 30s
      #   event_expression: "{{with .Identity}}{{.Tenant}}{{end}}"
      # match specifies matching expressions for mapping API requests to rate
      # limiting groups.
      match:
          # api_pattern specifies an API path pattern as defined by http.ServeMux
          # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
        - api_pattern: /
          # group_expression defines  the group for this matching expression.
          # A group can be selected dynamically using Go templates or statically
          # with a literal string.
          # See group.event_expression for template context attributes.
          group_expression: "default"
          # More example match rules:
      # - api_pattern: /api/management/v1/useradm/expample/slow/api/
      #   group_expression: "example_slow_group_by_tenant"
      # - api_pattern: /api/management/v1/useradm/expample/slow/api/
      #   group_expression: >
      #     {{-if .Identity.Trial-}}
      #     example_slow_group_by_tenant
      #     {{-else-}}
      #     default
      #     {{-end-}}
  ```

- *(useradm)* CLI command for getting and exporting usage statistics
([MEN-8225](https://northerntech.atlassian.net/browse/MEN-8225)) ([2c81c3b](https://github.com///commit/2c81c3b1b7d5e174c96dc4161cd0b218f3ca94de)) 

- *(workflows)* New workflow for exporting useradm stats into google spreadsheet
([MEN-8225](https://northerntech.atlassian.net/browse/MEN-8225)) ([a29fdd6](https://github.com///commit/a29fdd66a94c7a074193a59b07bd7b8e5510443f)) 

- Restrict the child tenants SSO changes to the parent tenant SSO
([ME-535](https://northerntech.atlassian.net/browse/ME-535)) ([d704951](https://github.com///commit/d704951a865664f066139466a46d35434f5fcce5)) 


  Support locking the SSO configuration for the child tenants
  to the configuration given by the parent.




### Refactor


- *(gui)* Unified session details display for device connect sessions
 ([8d526ae](https://github.com///commit/8d526ae8433393c7f7095fea299e44d17e7ab588)) 

- *(tenantadm)* Do not embed stripe.API inside internal client
 ([341719d](https://github.com///commit/341719d0bd5298e5998c7b5cf6c2b4cea3eebfa6)) 

- *(useradm)* Rename ErrForbidden to ErrFeatureUnavailableForPlan
 ([224639d](https://github.com///commit/224639d2f0cdf70b3d7e531dcf44dfcf4ca58d8f)) 


  It's too easy to use this error variable in places where it shouldn't
  be.

- *(useradm)* Bake some new consts for oauth2 signup cookies
 ([f5e5afd](https://github.com///commit/f5e5afdbc8cd8188834badc3a8c9424434dac248)) 





### Security


- Bump pbkdf2 from 3.1.2 to 3.1.3 in /frontend
 ([00e44b0](https://github.com///commit/00e44b08654f8d2c3dedc22159db53fa98e88444)) 


  Bumps [pbkdf2](https://github.com/crypto-browserify/pbkdf2) from 3.1.2 to 3.1.3.
  - [Changelog](https://github.com/browserify/pbkdf2/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/crypto-browserify/pbkdf2/compare/v3.1.2...v3.1.3)
  
  ---
  updated-dependencies:
  - dependency-name: pbkdf2
    dependency-version: 3.1.3
    dependency-type: indirect
  ...
- Bump mender-artifact to the latest version
 ([5091cc4](https://github.com///commit/5091cc426c67b6140e7864bb9eedc7629cbed715)) 
- Bump the development-dependencies group across 1 directory with 14 updates
 ([f47ef65](https://github.com///commit/f47ef651009e85b7574879e8702bbc704f1b7348)) 


  ---
  updated-dependencies:
  - dependency-name: "@rspack/cli"
    dependency-version: 1.4.8
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.4.8
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.0.15
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.37.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.7.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.2.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.44.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: globals
    dependency-version: 16.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.10.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: prettier
    dependency-version: 3.6.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.12.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.2.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  ...
- Bump the mui group in /frontend with 4 updates
 ([0b504f6](https://github.com///commit/0b504f67457dda2b09426895ff0ed2362f865429)) 


  ---
  updated-dependencies:
  - dependency-name: "@emotion/styled"
    dependency-version: 11.14.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.6.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump @playwright/test
 ([4cfded4](https://github.com///commit/4cfded4336983d99e3a09433e9d48893abee1b4a)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.53.2 to 1.54.2
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.53.2...v1.54.2)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.54.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: playwright
  ...
- Bump typescript
 ([72c1988](https://github.com///commit/72c19882bc010834c45e144d61591bcc2b6338ee)) 


  Bumps the e2e-test-dependencies group in /frontend/tests/e2e_tests with 1 update: [typescript](https://github.com/microsoft/TypeScript).
  
  
  Updates `typescript` from 5.8.3 to 5.9.2
  - [Release notes](https://github.com/microsoft/TypeScript/releases)
  - [Changelog](https://github.com/microsoft/TypeScript/blob/main/azure-pipelines.release-publish.yml)
  - [Commits](https://github.com/microsoft/TypeScript/compare/v5.8.3...v5.9.2)
  
  ---
  updated-dependencies:
  - dependency-name: typescript
    dependency-version: 5.9.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: e2e-test-dependencies
  ...
- Bump @mui/x-date-pickers in /frontend in the mui group
 ([89980f5](https://github.com///commit/89980f56cdf3d84e4e28a034f49caea1a56464fa)) 


  Bumps the mui group in /frontend with 1 update: [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/x-date-pickers` from 8.6.0 to 8.9.2
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.9.2/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.9.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...
- Bump the backend-docker-dependencies group across 10 directories with 2 updates
 ([0ce201b](https://github.com///commit/0ce201b6acee13f14559f49f3bc1cf73bc584917)) 


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
  
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `alpine` from 3.22.0 to 3.22.1
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  Updates `golang` from 1.24.4 to 1.24.5
  
  ---
  updated-dependencies:
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: alpine
    dependency-version: 3.22.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  - dependency-name: golang
    dependency-version: 1.24.5
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-docker-dependencies
  ...
- Bump the backend-golang-dependencies group
 ([ea75028](https://github.com///commit/ea750287738af93cf168f3e6229684c3d00e796e)) 


  Bumps the backend-golang-dependencies group in /backend with 15 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.18.0` | `1.18.2` |
  | [github.com/Azure/azure-sdk-for-go/sdk/storage/azblob](https://github.com/Azure/azure-sdk-for-go) | `1.6.1` | `1.6.2` |
  | [github.com/aws/aws-sdk-go-v2](https://github.com/aws/aws-sdk-go-v2) | `1.36.5` | `1.37.1` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.29.17` | `1.30.2` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.17.70` | `1.18.2` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.64.4` | `1.66.0` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.27.4` | `1.28.1` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.82.0` | `1.85.1` |
  | [github.com/go-viper/mapstructure/v2](https://github.com/go-viper/mapstructure) | `2.3.0` | `2.4.0` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.6` | `2.11.7` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.43.0` | `1.44.0` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.39.0` | `0.40.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.41.0` | `0.42.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.33.0` | `0.34.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.32.0` | `0.33.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.18.0 to 1.18.2
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/go-mgmt-sdk-release-guideline.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.18.0...sdk/azcore/v1.18.2)
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/storage/azblob` from 1.6.1 to 1.6.2
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/go-mgmt-sdk-release-guideline.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.6.1...sdk/storage/azblob/v1.6.2)
  
  Updates `github.com/aws/aws-sdk-go-v2` from 1.36.5 to 1.37.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.36.5...v1.37.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.29.17 to 1.30.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.29.17...v1.30.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.17.70 to 1.18.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/config/v1.18.2/CHANGELOG.md)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/credentials/v1.17.70...config/v1.18.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.64.4 to 1.66.0
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/iot/v1.64.4...service/s3/v1.66.0)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.27.4 to 1.28.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.27.4...config/v1.28.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.82.0 to 1.85.1
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.82.0...service/s3/v1.85.1)
  
  Updates `github.com/go-viper/mapstructure/v2` from 2.3.0 to 2.4.0
  - [Release notes](https://github.com/go-viper/mapstructure/releases)
  - [Changelog](https://github.com/go-viper/mapstructure/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/go-viper/mapstructure/compare/v2.3.0...v2.4.0)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.6 to 2.11.7
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.6...v2.11.7)
  
  Updates `github.com/nats-io/nats.go` from 1.43.0 to 1.44.0
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.43.0...v1.44.0)
  
  Updates `golang.org/x/crypto` from 0.39.0 to 0.40.0
  - [Commits](https://github.com/golang/crypto/compare/v0.39.0...v0.40.0)
  
  Updates `golang.org/x/net` from 0.41.0 to 0.42.0
  - [Commits](https://github.com/golang/net/compare/v0.41.0...v0.42.0)
  
  Updates `golang.org/x/sys` from 0.33.0 to 0.34.0
  - [Commits](https://github.com/golang/sys/compare/v0.33.0...v0.34.0)
  
  Updates `golang.org/x/term` from 0.32.0 to 0.33.0
  - [Commits](https://github.com/golang/term/compare/v0.32.0...v0.33.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.18.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/storage/azblob
    dependency-version: 1.6.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2
    dependency-version: 1.37.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.30.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.18.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.66.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.28.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.85.1
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/go-viper/mapstructure/v2
    dependency-version: 2.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.7
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.44.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.40.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.42.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.34.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.33.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...




### Build


- *(gui)* Added HMR enabled dev option
 ([4eb4d22](https://github.com///commit/4eb4d22f357acf104e083d9c2477a1b5aac79f18)) 







## v4.1.0-saas.11 - 2025-07-28


### Bug fixes


- *(deviceauth)* Fix the pagination logic in devices search endpoint
([MEN-8521](https://northerntech.atlassian.net/browse/MEN-8521)) ([5431bc1](https://github.com///commit/5431bc1f6b91379021c633cc2c7d3e29ad31c1d9)) 

- *(deviceconnect)* Increase the file upload size limit
 ([6ff38c3](https://github.com///commit/6ff38c39c3a04a37e52098a7d21225bb310c6e1f)) 

- *(gui)* Fixed billing profile not being fetched
 ([9042c6b](https://github.com///commit/9042c6be7ccc445a5affca63b65559bb562e6597)) 

- *(gui)* Fixed a problem that could apply RBAC restrictions on non-RBAC plans
([MEN-8498](https://northerntech.atlassian.net/browse/MEN-8498)) ([c870092](https://github.com///commit/c87009221163505732cb677e44a9c159233c3d68)) 

- *(gui)* Fixed an issue that could cause the organization token to overflow for older tenants
 ([e04f0e9](https://github.com///commit/e04f0e99df3c4edcd932034bc3d0aad31bd8467f)) 

- *(gui)* Fixed another situation that could cause the organization token to overflow
 ([555cb1e](https://github.com///commit/555cb1e7ec1571bd5ed02104c1185138b6e25d4a)) 

- *(gui)* Restricted to use id when adding users on trial plan
([ME-532](https://northerntech.atlassian.net/browse/ME-532)) ([20f8936](https://github.com///commit/20f89367ae97779489c2decfc5d38b9b59d9cf02)) 

- *(tenantadm)* Aligned api specs w/ code it should represent
 ([d6b4c7f](https://github.com///commit/d6b4c7f1b23f4e448108c73c3f396f7a7d636d59)) 

- *(useradm)* Always generate a unique user ID for newly created users
([MEN-8514](https://northerntech.atlassian.net/browse/MEN-8514)) ([85e0ea9](https://github.com///commit/85e0ea9351a6afc981f0719e66b69a73aad0a0b9)) 

- Make all routes response with JSON when route or method missing
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([0825b4d](https://github.com///commit/0825b4d8bcaf40e9e747247f7f7f5a5031c37c8a)) 
- Ensure that middlewares are set in the correct order
([MEN-8587](https://northerntech.atlassian.net/browse/MEN-8587)) ([e3d1101](https://github.com///commit/e3d1101bf5dcdf41090ed50ae8c52920b162734e)) 
- Allow user to see devices info when having read permission
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([758214b](https://github.com///commit/758214b50388aa996707caf088db2c3023a86196)) 


  If user have a read permission to a device group, allow the user to see
  the devices information in a deployment sent to the device group.
- Ensure the enterprise backend to return JSON on no method or route
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([b5426ae](https://github.com///commit/b5426ae6d89292e3e4fc414c4f30d355db3783e7)) 




### Documentation


- *(deployments)* Deprecate v1 GET `/artifacts/list` management endpoint
([MEN-8183](https://northerntech.atlassian.net/browse/MEN-8183)) ([2b308d5](https://github.com///commit/2b308d55b0f08bde3a6d845fa260587bac328d7f)) 

- *(tenantadm)* Add API specification for billing profile registration
 ([fb1e172](https://github.com///commit/fb1e1720d05662c8b36f24576ed0fb7fc4d8ccaa)) 





### Features


- *(deployments)* Implement new v2 GET `/artifacts` endpoint
([MEN-8181](https://northerntech.atlassian.net/browse/MEN-8181)) ([8e3e25c](https://github.com///commit/8e3e25c4446630e49cf5b4f9a0e8cb68fb645827)) 

- *(deployments)* New internal endpoint to get deployment device groups
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([1e2e380](https://github.com///commit/1e2e380cdddee6b0450b62fa0869ab631d0d94e5)) 

- *(gui)* Let UI aggregate all device software again - not just rootfs info
 ([cfa3712](https://github.com///commit/cfa3712ecfd833c0c31151e114b4dd2456665666)) 


  - due to the continued absence of the reporting backend this is re-introduced, but now in combination with the report scoped device retrieval

- *(tenantadm)* New endpoint to view current subscription
 ([3a5ceec](https://github.com///commit/3a5ceecac585a4c887b5dede7c6cc715de17de0b)) 


  The new endpoint GET /api/management/v2/billing/subscription
  retrieves the current Subscription.

- *(tenantadm)* API endpoint for registering billing profile
([MEN-8455](https://northerntech.atlassian.net/browse/MEN-8455)) ([ba80ea3](https://github.com///commit/ba80ea345ac2ef3bf320f8e752f967355b049b26)) 


  This is a replacement for the previous /upgrade API.

- *(useradm)* Add rate limiting configuration for authenticated requests
([MEN-7745](https://northerntech.atlassian.net/browse/MEN-7745)) ([172e232](https://github.com///commit/172e23249bfe8bb42d411e584a5a9f3d332e02cf)) 


  Added the following configuration parameters:
  
  ```yaml
  ratelimits:
   # auth configures ratelimits for authenticated requests.
    auth:
      # enable rate limiting also requires redis_connection_string to be effective.
      enable: false
      # default rate limit group is the default ratelimiting parameters used when
      # no group `match`es the expressions.
      default:
        quota: 100    # number of request per
        interval: 60s # interval
        # event_expression is a go template for grouping requests.
        # The following attributes are available in the context:
        # Identity - contains a subset of the JWT claims:
          - .Subject  (jwt:"sub")          string
          - .Tenant   (jwt:"mender.tenant) string
          - .Plan     (jwt:"mender.plan)   string
          - .Addons   (jwt:"mender.addons) struct{Enabled bool; Name string}
          - .IsUser   (jwt:"mender.user)   bool
          - .IsDevice (jwt:"mender.device) bool
          - .Trial    (jwt:"mender.trial)  bool
        event_expression: "{{with .Identity}}{{.Subject}}{{end}}"
      # groups specify rate limiting groups that overrides the parameters in the
      # default group.
      groups: []
      # Example:
      # - name: "slow"
      #   quota: 1
      #   interval: 30s
      #   event_expression: "{{with .Identity}}{{.Tenant}}{{end}}"
      # match specifies matching expressions for mapping API requests to rate
      # limiting groups.
      match: []
      # Example:
      #   # api_pattern specifies an API path pattern as defined by http.ServeMux
      #   # https://pkg.go.dev/net/http#hdr-Patterns-ServeMux
      # - api_pattern: /api/management/v1/useradm/slow/api
      #   # group_expression defines the group for this matching expression.
      #   # a group can be selected dynamically using Go templates.
      #   # The template context is the same as ratelimits.default.event_expression
      #   group_expression: "slow"
  ```

- *(useradm)* Add a deployments client with `AreInDeploymentGroups` method
([MEN-8473](https://northerntech.atlassian.net/browse/MEN-8473)) ([519ba94](https://github.com///commit/519ba94902f3075f50e4bee8bd5d9222a8bd49bb)) 

- Integrate requestsize middleware into deployments
 ([c957f12](https://github.com///commit/c957f1210db1de0e2d748cfff2f348f63d64edd6)) 
- Integrate requestsize middleware into deviceauth
 ([a67ade9](https://github.com///commit/a67ade9d1ea7609df515a44396680e4101c9f5e9)) 
- Integrate requestsize middleware into deviceconfig
 ([5cac8ca](https://github.com///commit/5cac8ca0f260f16966ad3cb5e605dd193833dcb1)) 
- Integrate requestsize middleware into deviceconnect
 ([7ca1025](https://github.com///commit/7ca10258c293d32fdc8e1567811b5ffe1f4a23fb)) 
- Integrate requestsize middleware into inventory
 ([9b2ed08](https://github.com///commit/9b2ed083119aaea30226f1e9cd80025cbd0b4001)) 
- Integrate requestsize middleware into iot-manager
 ([7135c16](https://github.com///commit/7135c16f1fbdcfd75b3eda787d0146b3e0ed3ac8)) 
- Integrate requestsize middleware into reporting
 ([0a1797a](https://github.com///commit/0a1797a636c8400b6027d46f6d703351aa586d32)) 
- Integrate requestsize middleware into useradm
 ([bf7b3b5](https://github.com///commit/bf7b3b591599962839178ce0dc712911a449bd8e)) 




### Refactor


- *(deployments)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8234](https://northerntech.atlassian.net/browse/MEN-8234)) ([a03820f](https://github.com///commit/a03820f22f542b67d8ecb9b37b28faaf57f34df3)) 

- *(gui)* Let chart adding + editing rely on rhf
 ([1f5f43f](https://github.com///commit/1f5f43f83c97808fd08ac29388947d88ecda255c)) 

- *(useradm)* Create utility function to load JWT PKI
 ([e1e9c31](https://github.com///commit/e1e9c31d4f14a906e3c76aba522e2d7c3143ead5)) 


  ... to lower cyclomatic complexity for main.RunServer.

- Remove rest_utils pkg and migrate existing utils to rest.utils
([MEN-8233](https://northerntech.atlassian.net/browse/MEN-8233)) ([b25a5f9](https://github.com///commit/b25a5f944e3c25e6f7552d705c78351a7ce796ae)) 
- Remove unused ant0ine/go-json-rest utilities from deployments
 ([90dd5f8](https://github.com///commit/90dd5f80af8bf35df2461dfe60939700062af8a0)) 
- Move integration fixtures to conftest.py and remove unused imports
 ([dae51c6](https://github.com///commit/dae51c61cbf7a03b487c3307cbcb3c52ebbce44c)) 




### Security


- Bump on-headers, express-session and morgan
 ([873c2c0](https://github.com///commit/873c2c001696c19965980485deb1c9fbcb7eb50f)) 


  Bumps [on-headers](https://github.com/jshttp/on-headers), [express-session](https://github.com/expressjs/session) and [morgan](https://github.com/expressjs/morgan). These dependencies needed to be updated together.
  
  Updates `on-headers` from 1.0.2 to 1.1.0
  - [Release notes](https://github.com/jshttp/on-headers/releases)
  - [Changelog](https://github.com/jshttp/on-headers/blob/master/HISTORY.md)
  - [Commits](https://github.com/jshttp/on-headers/compare/v1.0.2...v1.1.0)
  
  Updates `express-session` from 1.18.1 to 1.18.2
  - [Release notes](https://github.com/expressjs/session/releases)
  - [Changelog](https://github.com/expressjs/session/blob/master/HISTORY.md)
  - [Commits](https://github.com/expressjs/session/compare/v1.18.1...v1.18.2)
  
  Updates `morgan` from 1.10.0 to 1.10.1
  - [Release notes](https://github.com/expressjs/morgan/releases)
  - [Changelog](https://github.com/expressjs/morgan/blob/master/HISTORY.md)
  - [Commits](https://github.com/expressjs/morgan/compare/1.10.0...1.10.1)
  
  ---
  updated-dependencies:
  - dependency-name: on-headers
    dependency-version: 1.1.0
    dependency-type: indirect
  - dependency-name: express-session
    dependency-version: 1.18.2
    dependency-type: indirect
  - dependency-name: morgan
    dependency-version: 1.10.1
    dependency-type: indirect
  ...
- Bump on-headers and compression in /frontend
 ([11cd11c](https://github.com///commit/11cd11c4dce26cc951a7b261cec7efc65b5479c9)) 


  Bumps [on-headers](https://github.com/jshttp/on-headers) and [compression](https://github.com/expressjs/compression). These dependencies needed to be updated together.
  
  Updates `on-headers` from 1.0.2 to 1.1.0
  - [Release notes](https://github.com/jshttp/on-headers/releases)
  - [Changelog](https://github.com/jshttp/on-headers/blob/master/HISTORY.md)
  - [Commits](https://github.com/jshttp/on-headers/compare/v1.0.2...v1.1.0)
  
  Updates `compression` from 1.8.0 to 1.8.1
  - [Release notes](https://github.com/expressjs/compression/releases)
  - [Changelog](https://github.com/expressjs/compression/blob/master/HISTORY.md)
  - [Commits](https://github.com/expressjs/compression/compare/1.8.0...v1.8.1)
  
  ---
  updated-dependencies:
  - dependency-name: on-headers
    dependency-version: 1.1.0
    dependency-type: indirect
  - dependency-name: compression
    dependency-version: 1.8.1
    dependency-type: indirect
  ...
- Bump github.com/go-viper/mapstructure/v2 in /backend
 ([777d367](https://github.com///commit/777d3673eb1bb9b9a3d82aa48cbf8091417f8bb4)) 


  Bumps [github.com/go-viper/mapstructure/v2](https://github.com/go-viper/mapstructure) from 2.2.1 to 2.3.0.
  - [Release notes](https://github.com/go-viper/mapstructure/releases)
  - [Changelog](https://github.com/go-viper/mapstructure/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/go-viper/mapstructure/compare/v2.2.1...v2.3.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/go-viper/mapstructure/v2
    dependency-version: 2.3.0
    dependency-type: indirect
  ...
- Bump the production-dependencies group
 ([8ff713b](https://github.com///commit/8ff713b6206aaa16285056bc693c97a2d022c383)) 


  ---
  updated-dependencies:
  - dependency-name: "@sentry/react"
    dependency-version: 9.34.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: "@stripe/stripe-js"
    dependency-version: 7.4.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: axios
    dependency-version: 1.10.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-big-calendar
    dependency-version: 1.19.4
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  - dependency-name: react-hook-form
    dependency-version: 7.59.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: production-dependencies
  - dependency-name: react-router-dom
    dependency-version: 7.6.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: production-dependencies
  ...
- Bump @playwright/test
 ([0d169e8](https://github.com///commit/0d169e861652ed22ec56df20737d2d51a233b787)) 


  Bumps the playwright group in /frontend/tests/e2e_tests with 1 update: [@playwright/test](https://github.com/microsoft/playwright).
  
  
  Updates `@playwright/test` from 1.53.0 to 1.53.2
  - [Release notes](https://github.com/microsoft/playwright/releases)
  - [Commits](https://github.com/microsoft/playwright/compare/v1.53.0...v1.53.2)
  
  ---
  updated-dependencies:
  - dependency-name: "@playwright/test"
    dependency-version: 1.53.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: playwright
  ...
- Bump urllib3 from 2.4.0 to 2.5.0 in /backend/tests
 ([f7fcb02](https://github.com///commit/f7fcb0283b29b4bb1d56c52e247581d0d486dc67)) 


  Bumps [urllib3](https://github.com/urllib3/urllib3) from 2.4.0 to 2.5.0.
  - [Release notes](https://github.com/urllib3/urllib3/releases)
  - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
  - [Commits](https://github.com/urllib3/urllib3/compare/2.4.0...2.5.0)
  
  ---
  updated-dependencies:
  - dependency-name: urllib3
    dependency-version: 2.5.0
    dependency-type: direct:production
  ...
- Bump pbkdf2 from 3.1.2 to 3.1.3 in /frontend
 ([00e44b0](https://github.com///commit/00e44b08654f8d2c3dedc22159db53fa98e88444)) 


  Bumps [pbkdf2](https://github.com/crypto-browserify/pbkdf2) from 3.1.2 to 3.1.3.
  - [Changelog](https://github.com/browserify/pbkdf2/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/crypto-browserify/pbkdf2/compare/v3.1.2...v3.1.3)
  
  ---
  updated-dependencies:
  - dependency-name: pbkdf2
    dependency-version: 3.1.3
    dependency-type: indirect
  ...
- Bump form-data from 4.0.1 to 4.0.4 in /frontend
 ([1de20af](https://github.com///commit/1de20af63d14ffcad40a756f3e5d65ec6a923dfd)) 


  Bumps [form-data](https://github.com/form-data/form-data) from 4.0.1 to 4.0.4.
  - [Release notes](https://github.com/form-data/form-data/releases)
  - [Changelog](https://github.com/form-data/form-data/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/form-data/form-data/compare/v4.0.1...v4.0.4)
  
  ---
  updated-dependencies:
  - dependency-name: form-data
    dependency-version: 4.0.4
    dependency-type: indirect
  ...
- Bump axios from 1.10.0 to 1.11.0 in /frontend
 ([ec258ce](https://github.com///commit/ec258ce841a5c473515533267253a063db056b7e)) 


  Bumps [axios](https://github.com/axios/axios) from 1.10.0 to 1.11.0.
  - [Release notes](https://github.com/axios/axios/releases)
  - [Changelog](https://github.com/axios/axios/blob/v1.x/CHANGELOG.md)
  - [Commits](https://github.com/axios/axios/compare/v1.10.0...v1.11.0)
  
  ---
  updated-dependencies:
  - dependency-name: axios
    dependency-version: 1.11.0
    dependency-type: direct:production
  ...
- Bump mender-artifact to the latest version
 ([5091cc4](https://github.com///commit/5091cc426c67b6140e7864bb9eedc7629cbed715)) 
- Bump the development-dependencies group across 1 directory with 14 updates
 ([f47ef65](https://github.com///commit/f47ef651009e85b7574879e8702bbc704f1b7348)) 


  ---
  updated-dependencies:
  - dependency-name: "@rspack/cli"
    dependency-version: 1.4.8
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@rspack/core"
    dependency-version: 1.4.8
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@sentry/webpack-plugin"
    dependency-version: 4.0.0
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@types/node"
    dependency-version: 24.0.15
    dependency-type: direct:development
    update-type: version-update:semver-major
    dependency-group: development-dependencies
  - dependency-name: "@typescript-eslint/eslint-plugin"
    dependency-version: 8.37.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitejs/plugin-react"
    dependency-version: 4.7.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: "@vitest/coverage-v8"
    dependency-version: 3.2.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: core-js
    dependency-version: 3.44.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: globals
    dependency-version: 16.3.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: lint-staged
    dependency-version: 16.1.2
    dependency-type: direct:development
    update-type: version-update:semver-patch
    dependency-group: development-dependencies
  - dependency-name: msw
    dependency-version: 2.10.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: prettier
    dependency-version: 3.6.2
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: undici
    dependency-version: 7.12.0
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  - dependency-name: vitest
    dependency-version: 3.2.4
    dependency-type: direct:development
    update-type: version-update:semver-minor
    dependency-group: development-dependencies
  ...
- Bump the mui group in /frontend with 4 updates
 ([0b504f6](https://github.com///commit/0b504f67457dda2b09426895ff0ed2362f865429)) 


  ---
  updated-dependencies:
  - dependency-name: "@emotion/styled"
    dependency-version: 11.14.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.6.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: mui
  ...






## v4.1.0-saas.10 - 2025-07-09


### Bug fixes


- *(deviceauth)* Fix the pagination logic in devices search endpoint
([MEN-8521](https://northerntech.atlassian.net/browse/MEN-8521)) ([5431bc1](https://github.com///commit/5431bc1f6b91379021c633cc2c7d3e29ad31c1d9)) 

- *(gui)* Fixed an issue that would not show progress in the final phase of phased deployments
 ([5f3be23](https://github.com///commit/5f3be23d2aa35f4503979294d8e165c6ca7a9f60)) 

- *(gui)* Fixed an issue that prevented reactivating highlighted tooltips in the UI
 ([4babe2e](https://github.com///commit/4babe2e0a390dd4e7482692c1217342b2c645de2)) 

- *(gui)* Improved likelyhood of getting all device report related data from backend
 ([f429a5d](https://github.com///commit/f429a5ddf0166ffe563ace806a33084003a65746)) 

- *(gui)* Fixed an issue that could limit release selection during deployment creation
([MEN-8421](https://northerntech.atlassian.net/browse/MEN-8421)) ([a7e5352](https://github.com///commit/a7e5352aa2b2491bb61d15142bebab172d906905)) 

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

- *(inventory)* Broken links for legacy endpoints for listing devices
([MEN-8517](https://northerntech.atlassian.net/browse/MEN-8517)) ([9cf39b3](https://github.com///commit/9cf39b34f5ec6fb313a1b0e3c9afe30b5abce73e)) 


  When using the /api/managment/v1/inventory/devices to list devices, the
  path prefix is rewritten to /api/0.1.0/devices. This commit fixes the
  regression.

- *(tenantadm)* Return application/json in case of no route/method
([MEN-8523](https://northerntech.atlassian.net/browse/MEN-8523)) ([1e4a923](https://github.com///commit/1e4a923ead44470b198df26bfcc5d1dfaa50b965)) 


  This is a regression from the migration to gin HTTP framework which
  returns text/plain by default.

- *(useradm)* Use contenttype middleware for login endpoint
 ([1f5bc7d](https://github.com///commit/1f5bc7d624d7bd57b9ee9a7d6fbecdfb88650bd7)) 

- Ensure email is always encoded in lowercase when stored
([MEN-8328](https://northerntech.atlassian.net/browse/MEN-8328)) ([d80c818](https://github.com///commit/d80c818eed43765387cfe81445e187f9c1833156)) 


  Added a bson codec for model.Email that will ensure that emails are
  always encoded in lowercase in the database to ensure case insensitive
  queries.




### Documentation


- *(tenantadm)* Add API documentation for preview invoice API
 ([1d14dc9](https://github.com///commit/1d14dc93fe6db09baa6d187ca7d70d924a53fc5c)) 

- *(useradm)* Add security section to two-factor APIs
 ([cc0736a](https://github.com///commit/cc0736a9d3ad90bf8954277a65f371770515d22f)) 


  The endpoints require authentication.





### Features


- *(gui)* Staggered device report retrieval to further minimize hitting rate limits
 ([02f85ff](https://github.com///commit/02f85ff88f4baf77d445a8c1ae6194d748e1a028)) 

- *(gui)* Let UI aggregate all device software again - not just rootfs info
 ([cfa3712](https://github.com///commit/cfa3712ecfd833c0c31151e114b4dd2456665666)) 


  - due to the continued absence of the reporting backend this is re-introduced, but now in combination with the report scoped device retrieval

- *(tenantadm)* Stripe webhooks handle payed subscription invoices
 ([aa1dece](https://github.com///commit/aa1dece3b93dc4e074a385b162d6276ed3a10788)) 

- *(tenantadm)* Add option to disable downgrades when submitting subscription changes
([MEN-8347](https://northerntech.atlassian.net/browse/MEN-8347)) ([35edaca](https://github.com///commit/35edaca5fbf33820580b7a14e343dc2722665463)) 

- *(tenantadm)* Create invoice preview
([MEN-8349](https://northerntech.atlassian.net/browse/MEN-8349)) ([cb3bea8](https://github.com///commit/cb3bea882d2c55c45ac80313546398419477c3e9)) 

- *(tenantadm)* Get stripe subscription
([MEN-8148](https://northerntech.atlassian.net/browse/MEN-8148)) ([7b7d04f](https://github.com///commit/7b7d04fdbf047199aafe2afaf0104496d88e8767)) 

- Implemented content type checker middleware for gin framework
([MEN-8327](https://northerntech.atlassian.net/browse/MEN-8327)) ([9016554](https://github.com///commit/9016554b702297ad00f1a748d0824fdf19d05678)) 




### Performance


- Put routing path and parameters in separate accesslog fields
 ([51832b6](https://github.com///commit/51832b685d70d6dbe2f8cdf8442b96d6eec843fb)) 


  By separating the two, it is much less complex to index paths in the log
  parser.




### Refactor


- *(deployments)* Migrate from ant0nie/go-json-rest to gin-gonic/gin
([MEN-8234](https://northerntech.atlassian.net/browse/MEN-8234)) ([e8c3289](https://github.com///commit/e8c32890c9905f6f5099d9faadc1b2168af9ff99)) 

- *(deployments)* Migrate deployments enterprise from ant0nie/go-json-rest to gin
([MEN-8234](https://northerntech.atlassian.net/browse/MEN-8234)) ([3ff31a8](https://github.com///commit/3ff31a8ef060e381bddd7d696fbdc3e086fd15c1)) 

- *(gui)* Let chart adding + editing rely on rhf
 ([1f5f43f](https://github.com///commit/1f5f43f83c97808fd08ac29388947d88ecda255c)) 

- *(gui)* Let report data retrieval + generation work per single report
 ([049437f](https://github.com///commit/049437f4410cc51a5a4f76bc90b5b8ed2fc53385)) 

- *(gui)* Let each device report handle data retrieval separately
([ME-542](https://northerntech.atlassian.net/browse/ME-542)) ([23e16b2](https://github.com///commit/23e16b2dc95ce3fd4f5b94ed97198c2d9b0a8e5a)) 


  + limit report retrieval + visibility to reasonably safe request counts
  - this might reduce availability of dashboard widgets for more users, but until backend support arrives we'll remain limited
  - in order to handle the reduced availability & measure interest a support note was added
  
  - to account for the improbability of return of the reporting service the reliance on this was removed too

- *(gui)* Aligned delta artifact generation settings w/ updated design
 ([b3e0587](https://github.com///commit/b3e0587833dade80d103d6db166bcd5cb58683ae)) 


  + moved form to RHF to ease working w/ the changed UX

- *(tenantadm)* Increase type safety and consolidate Stripe iterators
 ([99063d4](https://github.com///commit/99063d49928a456da9d8e52c7ea789df155cb0a4)) 


  Removed the redundant listIter type as it is covered by the firstBatch
  of the stripeIter type. Also added a comment to provide clarity of the
  generic return argument from stripeIter.Next.

- *(useradm)* Remove the redundant authz middleware
 ([49c629d](https://github.com///commit/49c629d0a8bd50314c0c462211e1ea1d29c5dc8d)) 

- *(useradm)* Make the http pkg structure more consistent
 ([f645fe7](https://github.com///commit/f645fe7ce6216cc42a5b11145ff183263c175979)) 


  Move the endpoints to `router.go` and rename `middleware.go` to `utils.go`

- *(useradm)* Migrate useradm enterprise from ant0nie/go-json-rest to gin
([MEN-8237](https://northerntech.atlassian.net/browse/MEN-8237)) ([f313b66](https://github.com///commit/f313b662a022550e85d65dd95579a46280d833fe)) 

- *(useradm)* Move enterprise endpoints uris to `routing.go`
 ([16fcd7b](https://github.com///commit/16fcd7be25adae3e27a7270953926117965280c1)) 

- Remove unused ant0ine/go-json-rest utilities from deployments
 ([42f090b](https://github.com///commit/42f090ba9a5f7fd2a0529688943d3d76646a1cab)) 
- Swap ant0ine/go-json-rest with gin-gonic/gin in routing pkg
 ([b53abcd](https://github.com///commit/b53abcd60631dcbf9a7895af8de2bcdfcc007460)) 




### Security


- Bump urllib3 from 2.4.0 to 2.5.0 in /backend/tests
 ([f7fcb02](https://github.com///commit/f7fcb0283b29b4bb1d56c52e247581d0d486dc67)) 


  Bumps [urllib3](https://github.com/urllib3/urllib3) from 2.4.0 to 2.5.0.
  - [Release notes](https://github.com/urllib3/urllib3/releases)
  - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
  - [Commits](https://github.com/urllib3/urllib3/compare/2.4.0...2.5.0)
  
  ---
  updated-dependencies:
  - dependency-name: urllib3
    dependency-version: 2.5.0
    dependency-type: direct:production
  ...
- Bump github.com/go-viper/mapstructure/v2 in /backend
 ([777d367](https://github.com///commit/777d3673eb1bb9b9a3d82aa48cbf8091417f8bb4)) 


  Bumps [github.com/go-viper/mapstructure/v2](https://github.com/go-viper/mapstructure) from 2.2.1 to 2.3.0.
  - [Release notes](https://github.com/go-viper/mapstructure/releases)
  - [Changelog](https://github.com/go-viper/mapstructure/blob/main/CHANGELOG.md)
  - [Commits](https://github.com/go-viper/mapstructure/compare/v2.2.1...v2.3.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/go-viper/mapstructure/v2
    dependency-version: 2.3.0
    dependency-type: indirect
  ...
- Bump pillow from 11.2.1 to 11.3.0 in /backend/tests
 ([8aef575](https://github.com///commit/8aef575eb2aa55e2ea26cbc5595181166281a639)) 


  Bumps [pillow](https://github.com/python-pillow/Pillow) from 11.2.1 to 11.3.0.
  - [Release notes](https://github.com/python-pillow/Pillow/releases)
  - [Changelog](https://github.com/python-pillow/Pillow/blob/main/CHANGES.rst)
  - [Commits](https://github.com/python-pillow/Pillow/compare/11.2.1...11.3.0)
  
  ---
  updated-dependencies:
  - dependency-name: pillow
    dependency-version: 11.3.0
    dependency-type: direct:production
  ...
- Bump the backend-tests-python-dependencies group across 2 directories with 10 updates
 ([85a6aeb](https://github.com///commit/85a6aebda942e11894a5b1908cf12969d2fcd600)) 


  ---
  updated-dependencies:
  - dependency-name: opensearch-py
    dependency-version: 3.0.0
    dependency-type: direct:production
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pytest
    dependency-version: 8.4.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pymongo
    dependency-version: 4.13.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  - dependency-name: certifi
    dependency-version: 2025.6.15
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: opensearch-py
    dependency-version: 3.0.0
    dependency-type: direct:production
    dependency-group: backend-tests-python-dependencies
  - dependency-name: boto3
    dependency-version: 1.39.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: kubernetes
    dependency-version: 33.1.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pillow
    dependency-version: 11.3.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pytest-xdist
    dependency-version: 3.8.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: stripe
    dependency-version: 12.2.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-tests-python-dependencies
  - dependency-name: pydantic
    dependency-version: 2.11.7
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-tests-python-dependencies
  ...
- Bump the mui group in /frontend with 3 updates
 ([f799717](https://github.com///commit/f799717b655060d17d4565e01c7d48ab8842cb46)) 


  Bumps the mui group in /frontend with 3 updates: [@mui/icons-material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-icons-material), [@mui/material](https://github.com/mui/material-ui/tree/HEAD/packages/mui-material) and [@mui/x-date-pickers](https://github.com/mui/mui-x/tree/HEAD/packages/x-date-pickers).
  
  
  Updates `@mui/icons-material` from 7.0.1 to 7.0.2
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.0.2/packages/mui-icons-material)
  
  Updates `@mui/material` from 7.0.1 to 7.0.2
  - [Release notes](https://github.com/mui/material-ui/releases)
  - [Changelog](https://github.com/mui/material-ui/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/material-ui/commits/v7.0.2/packages/mui-material)
  
  Updates `@mui/x-date-pickers` from 7.28.2 to 8.2.0
  - [Release notes](https://github.com/mui/mui-x/releases)
  - [Changelog](https://github.com/mui/mui-x/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/mui/mui-x/commits/v8.2.0/packages/x-date-pickers)
  
  ---
  updated-dependencies:
  - dependency-name: "@mui/icons-material"
    dependency-version: 7.0.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/material"
    dependency-version: 7.0.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: mui
  - dependency-name: "@mui/x-date-pickers"
    dependency-version: 8.2.0
    dependency-type: direct:production
    update-type: version-update:semver-major
    dependency-group: mui
  ...
- Bump the backend-golang-dependencies group
 ([3068589](https://github.com///commit/3068589de1ccdb2539fcf247a32bc3b71dcefa60)) 


  Bumps the backend-golang-dependencies group in /backend with 14 updates:
  
  | Package | From | To |
  | --- | --- | --- |
  | [github.com/Azure/azure-sdk-for-go/sdk/azcore](https://github.com/Azure/azure-sdk-for-go) | `1.17.1` | `1.18.0` |
  | [github.com/Azure/azure-sdk-for-go/sdk/storage/azblob](https://github.com/Azure/azure-sdk-for-go) | `1.6.0` | `1.6.1` |
  | [github.com/aws/aws-sdk-go-v2/config](https://github.com/aws/aws-sdk-go-v2) | `1.29.12` | `1.29.14` |
  | [github.com/aws/aws-sdk-go-v2/credentials](https://github.com/aws/aws-sdk-go-v2) | `1.17.65` | `1.17.67` |
  | [github.com/aws/aws-sdk-go-v2/service/iot](https://github.com/aws/aws-sdk-go-v2) | `1.64.1` | `1.64.2` |
  | [github.com/aws/aws-sdk-go-v2/service/iotdataplane](https://github.com/aws/aws-sdk-go-v2) | `1.27.1` | `1.27.2` |
  | [github.com/aws/aws-sdk-go-v2/service/s3](https://github.com/aws/aws-sdk-go-v2) | `1.79.0` | `1.79.3` |
  | [github.com/nats-io/nats-server/v2](https://github.com/nats-io/nats-server) | `2.11.1` | `2.11.3` |
  | [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) | `1.40.1` | `1.41.2` |
  | [github.com/redis/go-redis/v9](https://github.com/redis/go-redis) | `9.7.3` | `9.8.0` |
  | [golang.org/x/crypto](https://github.com/golang/crypto) | `0.36.0` | `0.37.0` |
  | [golang.org/x/net](https://github.com/golang/net) | `0.38.0` | `0.39.0` |
  | [golang.org/x/sys](https://github.com/golang/sys) | `0.31.0` | `0.32.0` |
  | [golang.org/x/term](https://github.com/golang/term) | `0.30.0` | `0.31.0` |
  
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/azcore` from 1.17.1 to 1.18.0
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/release.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.17.1...sdk/azcore/v1.18.0)
  
  Updates `github.com/Azure/azure-sdk-for-go/sdk/storage/azblob` from 1.6.0 to 1.6.1
  - [Release notes](https://github.com/Azure/azure-sdk-for-go/releases)
  - [Changelog](https://github.com/Azure/azure-sdk-for-go/blob/main/documentation/release.md)
  - [Commits](https://github.com/Azure/azure-sdk-for-go/compare/sdk/azcore/v1.6.0...sdk/azcore/v1.6.1)
  
  Updates `github.com/aws/aws-sdk-go-v2/config` from 1.29.12 to 1.29.14
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/config/v1.29.12...config/v1.29.14)
  
  Updates `github.com/aws/aws-sdk-go-v2/credentials` from 1.17.65 to 1.17.67
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/credentials/v1.17.65...credentials/v1.17.67)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iot` from 1.64.1 to 1.64.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.64.1...service/iot/v1.64.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/iotdataplane` from 1.27.1 to 1.27.2
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/v1.27.1...v1.27.2)
  
  Updates `github.com/aws/aws-sdk-go-v2/service/s3` from 1.79.0 to 1.79.3
  - [Release notes](https://github.com/aws/aws-sdk-go-v2/releases)
  - [Changelog](https://github.com/aws/aws-sdk-go-v2/blob/main/changelog-template.json)
  - [Commits](https://github.com/aws/aws-sdk-go-v2/compare/service/s3/v1.79.0...service/s3/v1.79.3)
  
  Updates `github.com/nats-io/nats-server/v2` from 2.11.1 to 2.11.3
  - [Release notes](https://github.com/nats-io/nats-server/releases)
  - [Changelog](https://github.com/nats-io/nats-server/blob/main/.goreleaser.yml)
  - [Commits](https://github.com/nats-io/nats-server/compare/v2.11.1...v2.11.3)
  
  Updates `github.com/nats-io/nats.go` from 1.40.1 to 1.41.2
  - [Release notes](https://github.com/nats-io/nats.go/releases)
  - [Commits](https://github.com/nats-io/nats.go/compare/v1.40.1...v1.41.2)
  
  Updates `github.com/redis/go-redis/v9` from 9.7.3 to 9.8.0
  - [Release notes](https://github.com/redis/go-redis/releases)
  - [Changelog](https://github.com/redis/go-redis/blob/master/CHANGELOG.md)
  - [Commits](https://github.com/redis/go-redis/compare/v9.7.3...v9.8.0)
  
  Updates `golang.org/x/crypto` from 0.36.0 to 0.37.0
  - [Commits](https://github.com/golang/crypto/compare/v0.36.0...v0.37.0)
  
  Updates `golang.org/x/net` from 0.38.0 to 0.39.0
  - [Commits](https://github.com/golang/net/compare/v0.38.0...v0.39.0)
  
  Updates `golang.org/x/sys` from 0.31.0 to 0.32.0
  - [Commits](https://github.com/golang/sys/compare/v0.31.0...v0.32.0)
  
  Updates `golang.org/x/term` from 0.30.0 to 0.31.0
  - [Commits](https://github.com/golang/term/compare/v0.30.0...v0.31.0)
  
  ---
  updated-dependencies:
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/azcore
    dependency-version: 1.18.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/Azure/azure-sdk-for-go/sdk/storage/azblob
    dependency-version: 1.6.1
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/config
    dependency-version: 1.29.14
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/credentials
    dependency-version: 1.17.67
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iot
    dependency-version: 1.64.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/iotdataplane
    dependency-version: 1.27.2
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/aws/aws-sdk-go-v2/service/s3
    dependency-version: 1.79.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats-server/v2
    dependency-version: 2.11.3
    dependency-type: direct:production
    update-type: version-update:semver-patch
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/nats-io/nats.go
    dependency-version: 1.41.2
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: github.com/redis/go-redis/v9
    dependency-version: 9.8.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/crypto
    dependency-version: 0.37.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/net
    dependency-version: 0.39.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/sys
    dependency-version: 0.32.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  - dependency-name: golang.org/x/term
    dependency-version: 0.31.0
    dependency-type: direct:production
    update-type: version-update:semver-minor
    dependency-group: backend-golang-dependencies
  ...
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




### Build


- Change default make target to test for backend/pkg
 ([5ba3fd7](https://github.com///commit/5ba3fd7deda6421612029b31317cc61c2b1ef373)) 
- Add make target for pkg unit tests to test-unit root target
 ([5c2e23a](https://github.com///commit/5c2e23a6ff9b073b38cad1ef56e8845264369817)) 




### Revert


- "test: Unit tests for configuring rate limits"
 ([4ef01b1](https://github.com///commit/4ef01b1a66d5f20e10d587fbdfc9d3febe14ee8e)) 


  This reverts commit 16caca6ae355f2dfa843c019f31f0722456b1c96.
- "test: Unit tests for rate limit parameters and applying rate limits"
 ([4102778](https://github.com///commit/4102778ea46ac4bda13db499177cb491362b6000)) 


  This reverts commit 4bf8462399128586238c734fdd14c90ad7ce0479.
- "feat(deviceauth): Rate limit device requests"
 ([9c158a3](https://github.com///commit/9c158a3377fe6b9ac9f98f2b7cb15936237b6de1)) 


  This reverts commit 9c3041f5d54ea06c920ae0cc977c8af594133fb2.
- "feat(deviceauth): Rate limit authenticated devices API"
 ([aa7eff8](https://github.com///commit/aa7eff8de394de13f53008e2aaa5273bf7939a5c)) 


  This reverts commit 8c8028081a54a62ba8673071350414b096aa87b0.
- "test: Fix deviceauth.cache tests after changing client initialization"
 ([9d21a83](https://github.com///commit/9d21a83e05444189a51e197d4d5945d148e2a7f6)) 


  This reverts commit 721a2f760a38a9c25c38e5aa95fbd9f6f180ea7f.
- Gin utility for applying middleware to routes
 ([9f5c79c](https://github.com///commit/9f5c79cc30a4ee2576ef39f650b3a161c5996548)) 


  The func does not implement what it is intended to do and instead
  applies the middleware to all routes in the group.






## v4.1.0-saas.9 - 2025-06-18


### Bug fixes


- *(gui)* Fixed another situation that could cause the organization token to overflow
 ([555cb1e](https://github.com///commit/555cb1e7ec1571bd5ed02104c1185138b6e25d4a)) 







## v4.1.0-saas.8 - 2025-06-18


### Bug fixes


- *(gui)* Fixed a problem that could apply RBAC restrictions on non-RBAC plans
([MEN-8498](https://northerntech.atlassian.net/browse/MEN-8498)) ([c870092](https://github.com///commit/c87009221163505732cb677e44a9c159233c3d68)) 

- *(gui)* Fixed an issue that could cause the organization token to overflow for older tenants
 ([e04f0e9](https://github.com///commit/e04f0e99df3c4edcd932034bc3d0aad31bd8467f)) 







## v4.1.0-saas.7 - 2025-06-18


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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


### Bug fixes


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





