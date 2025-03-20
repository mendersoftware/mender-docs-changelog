---
title: Hosted Mender
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

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





