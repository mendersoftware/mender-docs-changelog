---
title: Mender Server Enterprise
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

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





