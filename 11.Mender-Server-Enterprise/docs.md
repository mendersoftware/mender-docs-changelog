---
title: Mender Server Enterprise
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## 4.0.0 - 2025-02-10


### Bug Fixes


- *(deployments)* Deprecate v1 endpoint for listing deployments
([MEN-7543](https://northerntech.atlassian.net/browse/MEN-7543)) ([4abf259](https://github.com/mendersoftware/mender-server-enterprise/commit/4abf259bc533c0173b625fb5de5a82771a633074))  by @kjaskiewiczz


  We deprecated GET v1 /deployments/deployments endpoint because of an
  issue with "search" query parameter behavior. As a replacement we
  introduce v2 version of the endpoint, where we replaced "search"
  parameter with "id" and "name" parameters.

- *(deviceauth)* Update default `server_priv_key_path`
([MEN-7589](https://northerntech.atlassian.net/browse/MEN-7589)) ([2b36ee8](https://github.com/mendersoftware/mender-server-enterprise/commit/2b36ee84c806b3668cc5f18a5e291d33690de4e0))  by @alfrunes
  - **BREAKING**: Update `server_priv_key_path` to `/etc/deviceauth/rsa/private.pem`

- *(deviceconfig)* Enable multiplatform build
([QA-673](https://northerntech.atlassian.net/browse/QA-673)) ([fbbe646](https://github.com/mendersoftware/mender-server-enterprise/commit/fbbe6466981015f47f250ad673f35f00004d1589))  by @oldgiova


  The required TARGETOS and TARGETARCH variables were missing from the
  Dockerfile.

- *(gui)* Fixed an issue that could prevent browsers from following programmatically triggered downloads
 ([f2b6189](https://github.com/mendersoftware/mender-server-enterprise/commit/f2b61896fc476d08f65d11a604777bb7809d6de1))  by @mzedel


  - relative download addresses seem not to be followed, switched to absolute instead

- *(gui)* Fixed an issue that would sometimes prevent users from switching between tenants
([MEN-7774](https://northerntech.atlassian.net/browse/MEN-7774)) ([ce777fd](https://github.com/mendersoftware/mender-server-enterprise/commit/ce777fdc9ae558a21a630384152152872c94b7a5))  by @mzedel


  can't rely on the user list data as it doesn't contain all the user details

- *(gui)* Fixed an issue that prevented deployment sizes from being shown
 ([d2bbb8d](https://github.com/mendersoftware/mender-server-enterprise/commit/d2bbb8df54aea9288af6d77944a516a075816928))  by @mzedel

- *(gui)* Fixed an issue that caused number comparisons in device filters to not work
([MEN-7717](https://northerntech.atlassian.net/browse/MEN-7717)) ([84e2398](https://github.com/mendersoftware/mender-server-enterprise/commit/84e2398fece6b10fddcf6f60e3ff744af903c707))  by @mzedel

- *(gui)* Added readable name for ltne device filter
([MEN-7717](https://northerntech.atlassian.net/browse/MEN-7717)) ([a741011](https://github.com/mendersoftware/mender-server-enterprise/commit/a74101176c22df69455a9d0634494912e219daab))  by @mzedel

- *(gui)* Fixed an issue that could lead to unexpected locations in the UI when accessing unauthorized sections while authorized
([MEN-7842](https://northerntech.atlassian.net/browse/MEN-7842)) ([7938291](https://github.com/mendersoftware/mender-server-enterprise/commit/7938291f8ac37c7ee3366c0cf2773e2c0053438f))  by @mzedel

- *(gui)* Enable device configuration for non enterprise users
 ([67170c5](https://github.com/mendersoftware/mender-server-enterprise/commit/67170c5edb27a1061abf2826234fabab45e4dedf))  by @thall


  Currently it's not possible to see device configuration if you host
  Mender self and have environment variable `HAVE_DEVICECONFIG=true`.

  Changes the predicate to be the same as for `hasDeviceConnect`.

- *(gui)* Added missing link to rbac docs in the cooresponding section
([MEN-7826](https://northerntech.atlassian.net/browse/MEN-7826)) ([1d8c4ff](https://github.com/mendersoftware/mender-server-enterprise/commit/1d8c4ff3f71f5918ea98ff277f96c31a85ebffe5))  by @mzedel

- *(gui)* Prevented disabled form inputs from showing validation errors
 ([2e7215a](https://github.com/mendersoftware/mender-server-enterprise/commit/2e7215aa93a3d357cfad34ec24e852ca66faf7df))  by @mzedel

- *(gui)* Aligned quick actions in release details with actually possibile actions
 ([365f564](https://github.com/mendersoftware/mender-server-enterprise/commit/365f5646f2c32956fa8c0cee22c20d8c3757948d))  by @mzedel

- *(gui)* Fixed an issue that would prevent showing deployment reports for phased deployments
 ([132d6b2](https://github.com/mendersoftware/mender-server-enterprise/commit/132d6b2aa932924c6612a8ca39867f246b388a88))  by @mzedel

- *(gui)* Fixed an issue that would prevent upgrading a running session to a different plan
([MEN-7898](https://northerntech.atlassian.net/browse/MEN-7898)) ([7668b29](https://github.com/mendersoftware/mender-server-enterprise/commit/7668b293bc71d4eaffda0c00823cac5026dfbf4c))  by @mzedel

- *(gui)* Fixed an issue that would crash the site when showing release details with multiple artifacts
 ([fd06f66](https://github.com/mendersoftware/mender-server-enterprise/commit/fd06f66516e4f33e52c9f305fb058594eecf714f))  by @mzedel

- *(gui)* Made addon availability rely more on addons where possible to prevent erroneous device config retrieval
([MEN-7895](https://northerntech.atlassian.net/browse/MEN-7895)) ([62d6516](https://github.com/mendersoftware/mender-server-enterprise/commit/62d6516b848b35e493db8be9908abaf7e573e008))  by @mzedel

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

- *(gui)* Ensured target directory is nonempty on artifact generation
([MEN-8010](https://northerntech.atlassian.net/browse/MEN-8010)) ([5616722](https://github.com/mendersoftware/mender-server-enterprise/commit/561672221f31d0be257c4e1da98c63eda40f792d))  by @mzedel

- *(gui)* Fixed an issue that could prevent listing devices with their custom identity in a deployment report
 ([f1fcf26](https://github.com/mendersoftware/mender-server-enterprise/commit/f1fcf26f33a3ae458e60f994fed60231d75abd5c))  by @mzedel

- *(gui)* Fixed an issue that would prevent navigating to devices from a software distribution chart
([MEN-8038](https://northerntech.atlassian.net/browse/MEN-8038)) ([6516986](https://github.com/mendersoftware/mender-server-enterprise/commit/6516986b82ce08ecdfd9ed3c790590796c60da2d))  by @mzedel

- *(gui)* Made user list tracking rely only on backend data instead of local store to prevent duplicate users listed
([MEN-8049](https://northerntech.atlassian.net/browse/MEN-8049)) ([7d1b060](https://github.com/mendersoftware/mender-server-enterprise/commit/7d1b060d096ff2549305cc0f453d8a35b21257b0))  by @mzedel

- *(gui)* Fixed an issue that would cause the ui to crash when creating phased deployments
 ([9827ba9](https://github.com/mendersoftware/mender-server-enterprise/commit/9827ba928889f52e7eb4216b68707386c082dc74))  by @mzedel

- *(gui)* Fixed remaining device percentage not being displayed correctly on phased deployment creation
 ([5600913](https://github.com/mendersoftware/mender-server-enterprise/commit/560091349c778c288ad1bdc5a8bcd9b54c39f399))  by @mzedel

- *(iot-core)* Incosistent serialization format for device private key
([MEN-7478](https://northerntech.atlassian.net/browse/MEN-7478)) ([6deadef](https://github.com/mendersoftware/mender-server-enterprise/commit/6deadef48a11f8f845fdb9c1e33ddf33a366d531))  by @alfrunes


  The generated key is serialized using SEC 1 (RFC5915) ASN.1 encoding,
  but encoded to PEM using PKCS8 (RFC5208) block header/trailer.

- *(iot-manager)* Save events for device inventory webhooks.
([MEN-7802](https://northerntech.atlassian.net/browse/MEN-7802)) ([755601c](https://github.com/mendersoftware/mender-server-enterprise/commit/755601ce9b51361e4433baef1caaf0841db743c4))  by @merlin-northern

- *(iot-manager)* Filter integrations by event scope
([MEN-7956](https://northerntech.atlassian.net/browse/MEN-7956)) ([08f062d](https://github.com/mendersoftware/mender-server-enterprise/commit/08f062db0f1b033bd4cae2052e7b7335e8d56df3))  by @kjaskiewiczz


  Decommission and provision device events and device status change
  event should be sent to integrations containing deviceauth scope.

- *(iot_manager)* Context cancelled fix: cancel() called too early.
 ([d2c5921](https://github.com/mendersoftware/mender-server-enterprise/commit/d2c59211ee0df06eb845d2ba23c7c53b8d1888c5))  by @merlin-northern


  `defer cancel()` was called on a context outside the func(){}
  where it was used making it impossible to actually call the webhook
  on any real-world latency network.

- *(tenantadm)* It should not be possible to make tenant without device limit a Service Provider tenant
([MEN-7954](https://northerntech.atlassian.net/browse/MEN-7954)) ([f144db6](https://github.com/mendersoftware/mender-server-enterprise/commit/f144db677152250baa47ebede394fe8f85ee7d52))  by @kjaskiewiczz

- *(useradm)* Add details to audit logs when creating and updating users
([MEN-7561](https://northerntech.atlassian.net/browse/MEN-7561)) ([5d4c675](https://github.com/mendersoftware/mender-server-enterprise/commit/5d4c675f5b6ed034473e01538ae1dc339ae476e5))  by @kjaskiewiczz

- *(useradm)* Update `server_priv_key_path` and `plan_definitions_path`
([MEN-7589](https://northerntech.atlassian.net/browse/MEN-7589)) ([dd64259](https://github.com/mendersoftware/mender-server-enterprise/commit/dd64259b45c2af38eb67619cf44a76babba8c12f))  by @alfrunes
  - **BREAKING**: Update default `server_priv_key_path` to `/etc/useradm/rsa/private.pem` and `plan_definitions_path` to `/etc/useradm/plans.yaml`

- *(useradm)* Basic permission set allows only to GET the /settings
([MEN-6967](https://northerntech.atlassian.net/browse/MEN-6967)) ([ff57146](https://github.com/mendersoftware/mender-server-enterprise/commit/ff57146b78fc14dcbc53e8957daeb5b5907ac659))  by @merlin-northern


  Basic permission set, which forms the core of:
  * ObserverRole
  * DeploymentsManagerRole
  * RemoteTerminalRole
  now allows only GET operations by default for the global /settings endpoint.

  Before this patch any of the above roles could use all the operations.
  This was a historical leftover; eversince we introduced /me and
  moved the UI to use it, it became an excessive permission.

- *(useradm)* Added missing textual description to PAT auditlog entries
([MEN-7770](https://northerntech.atlassian.net/browse/MEN-7770)) ([5523537](https://github.com/mendersoftware/mender-server-enterprise/commit/552353752737b2a4000bb69d83b0b77456dc55ed))  by @mzedel

- *(useradm)* Increase default limit for number of permission sets per role
([MEN-7870](https://northerntech.atlassian.net/browse/MEN-7870)) ([fc1e03e](https://github.com/mendersoftware/mender-server-enterprise/commit/fc1e03e288d07474222e39ece7ed8530836e6bf9))  by @kjaskiewiczz

- *(useradm)* Resolve user ID to email on AssignUserToTenants.
([MEN-8004](https://northerntech.atlassian.net/browse/MEN-8004)) ([b7229df](https://github.com/mendersoftware/mender-server-enterprise/commit/b7229df43e563cd6fed0ddaab074fb4cae1cb4fd))  by @merlin-northern

- *(workflows)* Update email jobs to not take paths as inputs
([MEN-7545](https://northerntech.atlassian.net/browse/MEN-7545)) ([4505be5](https://github.com/mendersoftware/mender-server-enterprise/commit/4505be5e4edb62e82239a4f06cd599484ed08ae0))  by @alfrunes

- *(workflows)* Remove SMTP message from input parameters
([MEN-7545](https://northerntech.atlassian.net/browse/MEN-7545)) ([3978481](https://github.com/mendersoftware/mender-server-enterprise/commit/3978481530b60b2344230a74dea693e57bd7a9ec))  by @alfrunes

- *(workflows)* Change SMTP template directory to /etc/workflows/data
([MEN-7545](https://northerntech.atlassian.net/browse/MEN-7545)) ([ea389b7](https://github.com/mendersoftware/mender-server-enterprise/commit/ea389b7ae779c6eb0205ae5eb16bd86be2e51bea))  by @alfrunes

- Aligned identity attribute usage with scoped inventory data to prevent overriding custom naming attributes with name tags
([MEN-7218](https://northerntech.atlassian.net/browse/MEN-7218)) ([9d82ea1](https://github.com/mendersoftware/mender-server-enterprise/commit/9d82ea13bbc705dae08f277d3cbd5905386a9452))  by @mzedel
- Document the 409 return for creating deployment to a group
([MEN-7414](https://northerntech.atlassian.net/browse/MEN-7414)) ([5327dac](https://github.com/mendersoftware/mender-server-enterprise/commit/5327daca07acc2e5b955ed2a23ae6ead39182e0d))  by @kjaskiewiczz
- Prevented commercial client components are only selected when plan/ addon accessible
([MEN-7458](https://northerntech.atlassian.net/browse/MEN-7458)) ([81e0b73](https://github.com/mendersoftware/mender-server-enterprise/commit/81e0b73047ba17c2301b080fa5a16f1200d7975a))  by @mzedel
- Fixed an issue that prevented retrieving group devices & related reports
([MEN-7461](https://northerntech.atlassian.net/browse/MEN-7461)) ([95ea85f](https://github.com/mendersoftware/mender-server-enterprise/commit/95ea85f46e26cacd59ce3f8c2a10fc086c756405))  by @mzedel
- Iot-manager: inventory scope webhook only in plan.Professional
 ([605903e](https://github.com/mendersoftware/mender-server-enterprise/commit/605903e610866b44332ef6a21044a85115adf4a0))  by @merlin-northern
- Fixed an issue that prevented showing PATs on page refresh
 ([bde80fe](https://github.com/mendersoftware/mender-server-enterprise/commit/bde80fe781be0c07684d2d4689227708695a548e))  by @mzedel
- Do not apply rate limits when sending the password reset link on user creation
([MEN-7588](https://northerntech.atlassian.net/browse/MEN-7588)) ([8a6a0b9](https://github.com/mendersoftware/mender-server-enterprise/commit/8a6a0b9b969d6af77c3852d2a99d6f99dfcc77ea))  by @tranchitella
- Tenantadm create-org CLI blocks until tenant is created
 ([a12ce6e](https://github.com/mendersoftware/mender-server-enterprise/commit/a12ce6ecdbdb35dcc048c3310d5d075dbd7a11e3))  by @alfrunes
- Fixed an issue that prevented onboarding tips from showing
 ([c2ecfcf](https://github.com/mendersoftware/mender-server-enterprise/commit/c2ecfcffd0a21f17ea8b3485a5d87efa21ab233a))  by @mzedel
- Do not remove Personal Access Tokens on 2FA enable
([MEN-7514](https://northerntech.atlassian.net/browse/MEN-7514)) ([1ab49bb](https://github.com/mendersoftware/mender-server-enterprise/commit/1ab49bb969d352a45e418ec5a99f3047eb3493af))  by @merlin-northern
- Set status `scheduled` instead of `pending` for scheduled deployments
([MEN-7602](https://northerntech.atlassian.net/browse/MEN-7602)) ([7fb1616](https://github.com/mendersoftware/mender-server-enterprise/commit/7fb161652ec19e471eee3806073e1d838cd1ea7e))  by @tranchitella
- Add `check-update` and `send-inventory` to `ConnectToDevices` RBAC permission set
([MEN-7620](https://northerntech.atlassian.net/browse/MEN-7620)) ([1a537d7](https://github.com/mendersoftware/mender-server-enterprise/commit/1a537d70dccec81500350bcbb3a4c61135798bef))  by @tranchitella
- Fixed an issue that prevented the UI from showing deeply nested software installations
([MEN-7640](https://northerntech.atlassian.net/browse/MEN-7640)) ([13496f3](https://github.com/mendersoftware/mender-server-enterprise/commit/13496f3468fd08dcc9656ba07463eba682cfaff4))  by @mzedel
- Populate the deployment's filter property for configuration deployments
([MEN-7821](https://northerntech.atlassian.net/browse/MEN-7821)) ([69a82b0](https://github.com/mendersoftware/mender-server-enterprise/commit/69a82b0655a4b5fe3d70b4df3a92c35ec220a377))  by @tranchitella
- Password reset when creating a new tenant as a service provider
([MEN-7845](https://northerntech.atlassian.net/browse/MEN-7845)) ([009e69b](https://github.com/mendersoftware/mender-server-enterprise/commit/009e69b6c54b10ff2c1e8cec1be63d8d02a0c96a))  by @alfrunes
- Improper error handling while processing password reset requests
([MEN-7834](https://northerntech.atlassian.net/browse/MEN-7834)) ([6eb99c1](https://github.com/mendersoftware/mender-server-enterprise/commit/6eb99c1951dde6493d67d8fca0186d45410a0f5d))  by @alfrunes


  Resetting the password for an email that does not exist no longer
  renders an error. All internal error messages are masked and return 500
  instead of 400.
- Stop user from having similar email and password
([MEN-6462](https://northerntech.atlassian.net/browse/MEN-6462)) ([3fa4a43](https://github.com/mendersoftware/mender-server-enterprise/commit/3fa4a432780a40fb9b8c37633c7feca6ba3445c5))  by @bahaa-ghazal
- Implement signal handler for `server` commands
([QA-782](https://northerntech.atlassian.net/browse/QA-782)) ([6e17ada](https://github.com/mendersoftware/mender-server-enterprise/commit/6e17adaaffa6778dc021353248d83b08cf645182))  by @bahaa-ghazal
- Implement signal handler for tenantadm's `server` command
([QA-782](https://northerntech.atlassian.net/browse/QA-782)) ([927d9a2](https://github.com/mendersoftware/mender-server-enterprise/commit/927d9a21e15d33de7c5c832da2142c579173d3bf))  by @bahaa-ghazal
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
- Grant `Read` role premission to download audit log
([MEN-7869](https://northerntech.atlassian.net/browse/MEN-7869)) ([0aee905](https://github.com/mendersoftware/mender-server-enterprise/commit/0aee905cd5bf48b5951ad8143852d648705d8b80))  by @bahaa-ghazal
- Update outdated api endpoints in the `inventory` service
([MEN-7017](https://northerntech.atlassian.net/browse/MEN-7017)) ([73c7149](https://github.com/mendersoftware/mender-server-enterprise/commit/73c714951a61642b2fc100214c61e5f66c27ee0c))  by @bahaa-ghazal
- Limiting the size of metadata when uploading and generating artifacts
([MEN-7166](https://northerntech.atlassian.net/browse/MEN-7166)) ([9e80728](https://github.com/mendersoftware/mender-server-enterprise/commit/9e8072874c94da9e7a3659207e08c6a05fc48cc4))  by @bahaa-ghazal

- *(auditlogs)* resolveDevice was never called when device was the object of the logs. ([MEN-7268](https://northerntech.atlassian.net/browse/MEN-7268))

*(create-artifact-worker) do not install openssl1.1-compat

  Changes:

  - use mender-artifact which does not depend on openssl1.1-compat
  - do not install openssl1.1-compat

- *(deployments)* Accesslog catches panic traces and remove "dev" middleware ([MC-7155](https://northerntech.atlassian.net/browse/MC-7155))
- *(deployments)* Compatibility with MongoDB \> 5.0 ([MEN-6956](https://northerntech.atlassian.net/browse/MEN-6956))
- *(deployments)* fix filtering out artifacts with unallowed names ([MEN-7074](https://northerntech.atlassian.net/browse/MEN-7074))
- *(deployments)* Improve error message when uploading too large artifacts ([MEN-7175](https://northerntech.atlassian.net/browse/MEN-7175))
- *(deployments)* fix release filtering and RBAC for releases
-  (deployments)* With the old implementation, when using more than one tag in the filter, or when using role which grants access to releases with given tag (and more than one tag was specified), deployments will present only releases containg ALL the tags each. With the new behavior, deployments will retrun all the releases containg ANY of the tags. ([MEN-7272](https://northerntech.atlassian.net/browse/MEN-7272))
- *(deployments)* Invalidate deployments cache on configuration deployments ([MEN-7256](https://northerntech.atlassian.net/browse/MEN-7256))
- *(deployments)* Compatibility with MongoDB \> 5.0 ([MEN-6956](https://northerntech.atlassian.net/browse/MEN-6956))
- *(deviceauth)* Handling preauthorized auth set when device is accepted
- *(deviceauth)  The previous behavior was putting the device in a conflicting state and returning 500 errors on auth requests. With this commit, the preauthorized auth set will take precedence and take over as the accepted auth set. ([ALV-213](https://northerntech.atlassian.net/browse/ALV-213))
- *(deviceauth)* Wrong Content-Type header on successful authentication
- *(deviceauth)  On success, the Content-Type header is set to `application/jwt` instead of invalid `application/json` on 200 responses to POST /api/devices/v1/authentication/auth\_requests ([MEN-6912](https://northerntech.atlassian.net/browse/MEN-6912))
- *(deviceauth)* Fixed caching of tenants after changing Tenant Token format ([MEN-7244](https://northerntech.atlassian.net/browse/MEN-7244))
- *(deviceauth)* Preauthorize force behavior applies to existing auth sets
- *(deviceauth)  Updates the behavior of the Preauthorize endpoint if "force" paremeter is set:
  * If an authset already exist, the status will be forced to "preauthorized".
  * If the auth set does not exist, a new one will be created. ([MEN-7241](https://northerntech.atlassian.net/browse/MEN-7241))
- *(deviceauth)* Inconsistent device `check_in_time` when listing devices
- *(deviceauth)  The lookup for `check_in_time` from the cache does not work when running Redis in cluster mode because of the MGET command requires keys to hash to the same slot. This commit replaces MGET with multiple batched GET commands when running Redis in cluster mode. ([MEN-7337](https://northerntech.atlassian.net/browse/MEN-7337))
- *(deviceauth)* Update check-in-time after 24hours and not at midnight

  The previous implementation would propagate check in time if the UTC date changes \- that is midnight UTC. This commit only propagates the timestamp on check in after 24h.

  NOTE: Data from cahce is updated on every request so it does not affect the response when getting devices. ([MEN-7439](https://northerntech.atlassian.net/browse/MEN-7439))
- *(generate-delta-worker)* do not install openssl1.1-compat

  Changes:

  - use mender-artifact which does not depend on openssl1.1-compat
  - do not install openssl1.1-compat

- *(gui)* fixed missing theme global variables ([MEN-7044](https://northerntech.atlassian.net/browse/MEN-7044))
- *(gui)* fixed terminal closure made by exit command ([MEN-7081](https://northerntech.atlassian.net/browse/MEN-7081))
- *(gui)* Devices tab not showing in the UI with Deployments manager ([MEN-7111](https://northerntech.atlassian.net/browse/MEN-7111))
- *(gui)* fixed Software distribution widget displayed wrong other devices count
- *(gui)* ensured release is retrieved on deployment recreation ([MEN-7228](https://northerntech.atlassian.net/browse/MEN-7228))
- *(gui)* ensured an attempt to show fresh device information is made in every device related auditlog entry ([MEN-7034](https://northerntech.atlassian.net/browse/MEN-7034))
- *(gui)* fixed an issue that sometimes prevented reopening paginated auditlog links
- *(gui)* fixed an issue that could prevent SSO logins depending on the type of SSO
- *(gui)* fixed SSO information not being adjusted depending on the type of SSO configured ([MEN-7277](https://northerntech.atlassian.net/browse/MEN-7277))
- *(gui)* fixed an issue that prevented accessing releases with routing relevant symbols in their name ([MEN-7209](https://northerntech.atlassian.net/browse/MEN-7209))
- *(gui)* ensured browser generated reports are refreshed on every full device data retrieval to prevent partly initialized report data to show misleading software distributions ([MEN-7123](https://northerntech.atlassian.net/browse/MEN-7123))
- *(gui)* fixed an issue that would prevent promoting a device to a gateway device ([MEN-7334](https://northerntech.atlassian.net/browse/MEN-7334))
- *(gui)* limited global settings saving for less privileged users ([MEN-6970](https://northerntech.atlassian.net/browse/MEN-6970))

- *(inventory)* Accesslog middleware log panic traces and remove "dev" middleware ([MC-7155](https://northerntech.atlassian.net/browse/MC-7155))
- *(inventory)* Bound the number of devices considered when aggregating filter attributes to maximum 5,000. ([MEN-6917](https://northerntech.atlassian.net/browse/MEN-6917))
- *(inventory)* do not return updated\_ts as zero time if updated\_ts is not set
- *(inventory)* store "check\_in\_time" attribute as ISODate instead of string ([MEN-7259](https://northerntech.atlassian.net/browse/MEN-7259))
- *(inventory)* attribute modification in the range loop

- *(iot-manager)* Event APIs return OK if event is saved to database ([MEN-6898](https://northerntech.atlassian.net/browse/MEN-6898))
- *(iot-manager)* Create TTL index for removing expired logs ([MEN-7101](https://northerntech.atlassian.net/browse/MEN-7101))
- *(iot-manager)* Incosistent serialization format for device private key

  The generated key is serialized using (RFC5915) ASN.1 encoding, but encoded to PEM using PKCS8 (RFC5208) block header/trailer. ([MEN-7478](https://northerntech.atlassian.net/browse/MEN-7478), \[SEC 1\]([https://northerntech.atlassian.net/browse/SEC](https://northerntech.atlassian.net/browse/SEC) 1))

- *(tenantadm)* New flag automigrate to run migrations before starting server. ([MEN-6999](https://northerntech.atlassian.net/browse/MEN-6999))
- *(tenantadm)* Organization name can be maximum 100 characters and email can be no longer than 254 characters. ([MEN-6883](https://northerntech.atlassian.net/browse/MEN-6883))
- *(tenantadm)* Too long HTTP errors causes `sync-tenants` CLI command to hang ([MEN-7105](https://northerntech.atlassian.net/browse/MEN-7105))
- *(tenantadm)* Prevent syncing multi-tenant users more than once ([MEN-7173](https://northerntech.atlassian.net/browse/MEN-7173))
- *(tenantadm)* Incorrect timestamp parsing when creating organization ([MEN-7399](https://northerntech.atlassian.net/browse/MEN-7399))
- *(tenantadm)* Proper server-side recaptcha response validation ([MEN-7400](https://northerntech.atlassian.net/browse/MEN-7400))
- *(tenantadm)* internal tenant removal endpoint should not return 500 on not found error ([MEN-7321](https://northerntech.atlassian.net/browse/MEN-7321))
- *(tenantadm)* Return appropriate exit code on CLI error ([MEN-7420](https://northerntech.atlassian.net/browse/MEN-7420))

- *(useradm)* Update accesslog middleware to catch panic traces and remove dev mode ([MC-7155](https://northerntech.atlassian.net/browse/MC-7155))
- *(useradm)* remove Roles from user filter
  We added roles to user filter by accident. We never used them and the possibility of using roles in user filter was not documented.
- *(useradm)* OpenID Connect: validate the settings. ([MEN-7047](https://northerntech.atlassian.net/browse/MEN-7047))
- *(useradm)* 'Read releases' lacking permissions to get tags and types ([MEN-7102](https://northerntech.atlassian.net/browse/MEN-7102))
- *(useradm)* if needed, update default tenant when deleting user from particular tenant ([MEN-7063](https://northerntech.atlassian.net/browse/MEN-7063))
- *(useradm)* fix permissions to releases ([MEN-7073](https://northerntech.atlassian.net/browse/MEN-7073))
- *(useradm)* limit ReadDevices and DeployToDevices permissions
  ReadDevices permission set will no longer provide read permissions to releases. DeployToDevices permission set will no longer provide full access to releases (read and manage). To have access to releases users should use ReadReleases and ManageReleases permission sets. When it comes to built-in roles \- Deployments Manager will no longer provide full access to releases. Full access to releases is provided by Release Manager role.
  BREAKING CHANGE: Users with roles containg ReadDevices and DeployToDevices permissions can lose access to some endpoints. ([MEN-7118](https://northerntech.atlassian.net/browse/MEN-7118))
- *(useradm)* remove Roles from user filter
  We added roles to user filter by accident. We never used them and the possibility of using roles in user filter was not documented.
- *(useradm)* if needed, update default tenant when deleting user from particular tenant ([MEN-7063](https://northerntech.atlassian.net/browse/MEN-7063))
- *(useradm)* ReadDevices permission set should not grant access to /deployments/releases
- *(useradm)* two steps login: do not check tenant id when getting user object
- *(useradm)* increase and allow SAML metadata max size limit to be modified.
- *(useradm)* set sso kind on oidc metadata save. ([MEN-7276](https://northerntech.atlassian.net/browse/MEN-7276))
- *(useradm)* in case of sso users return 401 from plan-verify
- *(useradm)* API throttling not working with Redis Cluster mode ([MEN-7338](https://northerntech.atlassian.net/browse/MEN-7338))
- *(useradm)* Use security hardened client when fetching SSO metadata
  When fetching OpenID Connect well-known document from an URL, the URL must use HTTPS and must resolve to a global unicast IP address. The client refuse to follow redirects. ([MEN-7365](https://northerntech.atlassian.net/browse/MEN-7365))
- *(useradm)* Use security hardened client when serving OpenID Authn requests
-  When authenticating clients authenticating using OpenID Connect any external requests (JWK resolution, token exchange etc.) use a hardened client that does not follow redirects and blacklists private IP address ranges. ([MEN-7365](https://northerntech.atlassian.net/browse/MEN-7365))
- *(useradm)* Improve validation of OpenID Connect endpoints
-  The OpenID Connect endpoints must be `https` and the content of the JWK endpoint is validated at configuration time. ([MEN-7365](https://northerntech.atlassian.net/browse/MEN-7365))
- *(useradm)* Changing roles does not show details in audit log ([MEN-7397](https://northerntech.atlassian.net/browse/MEN-7397))
- *(useradm)* properly delete users when deleting a tenant ([MEN-7409](https://northerntech.atlassian.net/browse/MEN-7409))

- *(workflows)* Remove redis dependency from workflows and container image ([MEN-7058](https://northerntech.atlassian.net/browse/MEN-7058))
- *(workflows)* correct link to logo in the emails. ([MEN-7226](https://northerntech.atlassian.net/browse/MEN-7226))
- *(workflows)* switch email logo from svg to png ([MEN-7226](https://northerntech.atlassian.net/browse/MEN-7226))



### Documentation


- *(README)* Add step to clone repository
 ([f9d3bbd](https://github.com/mendersoftware/mender-server-enterprise/commit/f9d3bbde382bca4592f41e3d6be7e8292dcb221f))  by @alfrunes

- *(README)* Consistently add syntax highlighting to code blocks
 ([8583102](https://github.com/mendersoftware/mender-server-enterprise/commit/8583102cbbf49882b9a9ab1b80257516ec13dc24))  by @alfrunes

- *(deployments)* Clarifications for the GET /deployments version 2 endpoint.
([MEN-8053](https://northerntech.atlassian.net/browse/MEN-8053)) ([7851a7c](https://github.com/mendersoftware/mender-server-enterprise/commit/7851a7cf94e27424e326f8b50fb3e975cbc765d1))

- *(inventory)* Describe inventory webhook events.
([MEN-8041](https://northerntech.atlassian.net/browse/MEN-8041)) ([2d59d8a](https://github.com/mendersoftware/mender-server-enterprise/commit/2d59d8a4b8d9d662c621e33ed0a269a7973748a8))

- *(tenantadm)* Extend tenantadm API docs with BillingProfile
 ([30ebc38](https://github.com/mendersoftware/mender-server-enterprise/commit/30ebc38666524f5c54966c3e874da87792473257))  by @alfrunes

- Update README.md with instructions on using the docker composition
 ([c9aa7dc](https://github.com/mendersoftware/mender-server-enterprise/commit/c9aa7dc73db9717f436def2b14dc8f7cce74903f))  by @alfrunes
- Add section about testing build artifacts
 ([f36c340](https://github.com/mendersoftware/mender-server-enterprise/commit/f36c3402b1988ee9b20afc04dcb159d6063be1d5))  by @alfrunes
- Add snippet for starting a mender client to README
 ([a322b2d](https://github.com/mendersoftware/mender-server-enterprise/commit/a322b2d8c22e5e9e409a9a5c96c3b8412cef555f))  by @alfrunes
- Expand BillingProfile with shipping details
 ([305c012](https://github.com/mendersoftware/mender-server-enterprise/commit/305c0127159324128713ffe72d4eebbc5f5e6e9d))  by @alfrunes
- Add missing documentation for GET/PATCH /v2/billing/profile
 ([a1ec5bb](https://github.com/mendersoftware/mender-server-enterprise/commit/a1ec5bbecfd3207723e758cd5bc6b5adcf8181ff))  by @alfrunes
- Add additional schema for BillingProfileUpdate
 ([e623819](https://github.com/mendersoftware/mender-server-enterprise/commit/e62381982d20950266959bb4f7fb00fb1f0c9033))  by @alfrunes
- Update README.md
 ([f7a1b09](https://github.com/mendersoftware/mender-server-enterprise/commit/f7a1b097726672dd40ed7df17551229c5cf6ce7f))  by @alfrunes


  Adjusted styling (note color, added 1st level indentation,  taxonomy i.e., Mender Server, Mender Enterprise) to make it easy to follow and read.
- Fix invalid internal API specs
 ([8a89b71](https://github.com/mendersoftware/mender-server-enterprise/commit/8a89b71e6c370da8a7fa467f47396d45b7a3fe52))  by @alfrunes
- Document how to bring up the Virtual Device for enterprise setup
 ([c674566](https://github.com/mendersoftware/mender-server-enterprise/commit/c674566e6d834c64d6e64d321c6e09b5f2a36259))  by @lluiscampos
- Fix typo in snippet for creating tenant
 ([a346d33](https://github.com/mendersoftware/mender-server-enterprise/commit/a346d33781086d157d831478cfb64bebeef6c3bd))  by @alfrunes
- Docmentation on backend integration tests running separately
([QA-683](https://northerntech.atlassian.net/browse/QA-683)) ([a8f8d54](https://github.com/mendersoftware/mender-server-enterprise/commit/a8f8d545573100186fba953c7179592a23196b23))  by @merlin-northern
- Add missing API parameters to the documentation
 ([7f68520](https://github.com/mendersoftware/mender-server-enterprise/commit/7f68520e8dd4c102b78735b68c0bdbfb986685c7))  by @alfrunes




### Features


- *(billing)* Add option to provide BillingProfile on signup from trial
([MEN-7468](https://northerntech.atlassian.net/browse/MEN-7468)) ([6dfccc4](https://github.com/mendersoftware/mender-server-enterprise/commit/6dfccc433aa6c014d9a1176c8d6020df92e2482d))  by @alfrunes


  Instead of taking the parameters from trial sign-up, the tenant can add
  Address and update company name when signing up for a paid plan.

- *(deployments)* Add filter field to deployment object
([MEN-7416](https://northerntech.atlassian.net/browse/MEN-7416)) ([fec5b91](https://github.com/mendersoftware/mender-server-enterprise/commit/fec5b91d59d07b1a0d85ccf077cd56aa5b192278))  by @kjaskiewiczz


  The filter field contains information about devices targeted by the
  deployment.

- *(deployments)* New endpoint for getting release by name
([MEN-7575](https://northerntech.atlassian.net/browse/MEN-7575)) ([3a18e88](https://github.com/mendersoftware/mender-server-enterprise/commit/3a18e880ec5cddedc19ed08949777caedda4350d))  by @kjaskiewiczz

- *(gui)* Enabled webhook scope selection
([MEN-7455](https://northerntech.atlassian.net/browse/MEN-7455)) ([21dae98](https://github.com/mendersoftware/mender-server-enterprise/commit/21dae988469d5643a4528bef9a6e68ec75005c63))  by @mzedel

- *(gui)* Extended webhook event details
([MEN-7574](https://northerntech.atlassian.net/browse/MEN-7574)) ([92d7cc6](https://github.com/mendersoftware/mender-server-enterprise/commit/92d7cc667b368ea561576c7bd4a376c966d9e477))  by @mzedel

- *(gui)* Aligned webhook listing with updated design
([MEN-7573](https://northerntech.atlassian.net/browse/MEN-7573)) ([dcca0de](https://github.com/mendersoftware/mender-server-enterprise/commit/dcca0defcedfc62af7b441edf46b7254971a02ac))  by @mzedel

- *(gui)* Added the possibility to create service provider administering roles
([MEN-7570](https://northerntech.atlassian.net/browse/MEN-7570)) ([92d7e50](https://github.com/mendersoftware/mender-server-enterprise/commit/92d7e50e311d8c88f9847a83cec7b797ef9cebcc))  by @mzedel

- *(gui)* Aligned role removal dialog with other parts of the UI
 ([8661704](https://github.com/mendersoftware/mender-server-enterprise/commit/866170425bef1f01f3a4a25f0d4e19fe5da94a6e))  by @mzedel

- *(gui)* Added support for Personal Access Token auditlog entries
([MEN-7622](https://northerntech.atlassian.net/browse/MEN-7622)) ([9a9a6c3](https://github.com/mendersoftware/mender-server-enterprise/commit/9a9a6c3829611c35622e3812db7bbedd9bc9f9e5))  by @mzedel

- *(gui)* Added possibility to trigger deployment & inventory data updates when troubleshooting
([MEN-7657](https://northerntech.atlassian.net/browse/MEN-7657)) ([11a9b7a](https://github.com/mendersoftware/mender-server-enterprise/commit/11a9b7a57a179c3d9605779b41f6d10b6dbc72fb))  by @mzedel

- *(gui)* Made deployment targets rely on filter information in the deployment to more reliably display target devices etc.
([MEN-7647](https://northerntech.atlassian.net/browse/MEN-7647)) ([47c92d4](https://github.com/mendersoftware/mender-server-enterprise/commit/47c92d4db494cfc77116258fc2ed7fdca8691400))  by @mzedel

- *(gui)* Aligned notions of "latest device activity" in listing & details
 ([40ee57d](https://github.com/mendersoftware/mender-server-enterprise/commit/40ee57da173c1d5bc2a39b2a5534b62dc986f53c))  by @mzedel

- *(gui)* Limited onboarding to hosted Mender to ensure a streamlined experience
([MEN-7896](https://northerntech.atlassian.net/browse/MEN-7896)) ([cee60f8](https://github.com/mendersoftware/mender-server-enterprise/commit/cee60f8de9eb5b6940828f5e09e11dbd4e2d4059))  by @mzedel

- *(gui)* Added feedback on file size limits to artifact upload dialog
([MEN-7858](https://northerntech.atlassian.net/browse/MEN-7858)) ([d612334](https://github.com/mendersoftware/mender-server-enterprise/commit/d612334ebfae6b1a3d416016ee500b89daa70804))  by @mzedel

- *(gui)* Aligned text input appearance with MUI updated guidelines
([MEN-7838](https://northerntech.atlassian.net/browse/MEN-7838)) ([e5d5672](https://github.com/mendersoftware/mender-server-enterprise/commit/e5d56720b901a451fa47a514424f710763b50291))  by @mzedel

- *(gui)* Added explanation about integration number limitation
([MEN-7899](https://northerntech.atlassian.net/browse/MEN-7899)) ([dbdfa67](https://github.com/mendersoftware/mender-server-enterprise/commit/dbdfa672a62eb30745fb4b0e73bea7d345644932))  by @mzedel

- *(gui)* Clarified user creation capabilities for non-enterprise users
([MEN-7883](https://northerntech.atlassian.net/browse/MEN-7883)) ([d2fd192](https://github.com/mendersoftware/mender-server-enterprise/commit/d2fd192e8c09443dabb694288d73636853b02d86))  by @mzedel

- *(gui)* Added automatic refresh to get webhook events
([MEN-8045](https://northerntech.atlassian.net/browse/MEN-8045)) ([502e06a](https://github.com/mendersoftware/mender-server-enterprise/commit/502e06aab96f3ce980cd6fe197a2fd6d7e99233a))  by @mzedel

- *(inventory)* Add support for "$in" operator in the device search API
([MEN-7667](https://northerntech.atlassian.net/browse/MEN-7667)) ([fd4eaf0](https://github.com/mendersoftware/mender-server-enterprise/commit/fd4eaf0ecc8b72ff7fa9cfe7b6f214bc4678a97f))  by @kjaskiewiczz

- Limit what SP tenants can configure for children tenants
([MEN-7493](https://northerntech.atlassian.net/browse/MEN-7493)) ([d745bbf](https://github.com/mendersoftware/mender-server-enterprise/commit/d745bbf1b5018e0c2912912c2f318bf5c90b8629))  by @tranchitella


  With this commit, the SP tenants can only configure the name of the
  children tenants, the default admin user, enable the propagation of SSO
  and server side binary delta generation, copying the settings from the
  SP tenant itself. All the other settings, including plan and addons, are
  copied over from the SP tenant.
- Update tenant to set as service-provider.
([MEN-7371](https://northerntech.atlassian.net/browse/MEN-7371)) ([eff5d8c](https://github.com/mendersoftware/mender-server-enterprise/commit/eff5d8c88b0dc8ce8a64acfee747919ac1a59d98))  by @merlin-northern
- Limit children tenants
([MEN-7446](https://northerntech.atlassian.net/browse/MEN-7446)) ([4851129](https://github.com/mendersoftware/mender-server-enterprise/commit/4851129cae259b9dd6358336ebb5e80d7c5ab29a))  by @merlin-northern
- Mender Event Model: publish inventory changed event
([MEN-7451](https://northerntech.atlassian.net/browse/MEN-7451)) ([8438a26](https://github.com/mendersoftware/mender-server-enterprise/commit/8438a260a64409c4ecf222f00515bae4046c4fb6))  by @merlin-northern
- Remove children tenants first when removing SP tenants
([MEN-7492](https://northerntech.atlassian.net/browse/MEN-7492)) ([22784fd](https://github.com/mendersoftware/mender-server-enterprise/commit/22784fd684c5dd38847cf43df6bba6ba735ddcc9))  by @tranchitella
- Added option to limit deployments to a maximum number of devices in a dynamic group
([MEN-7403](https://northerntech.atlassian.net/browse/MEN-7403)) ([c04d736](https://github.com/mendersoftware/mender-server-enterprise/commit/c04d736fd58adba549858b86b936d076f855eb7c))  by @mzedel
- Auditlogs: allow tracking of tenant management operations.
([MEN-7444](https://northerntech.atlassian.net/browse/MEN-7444)) ([d6782c1](https://github.com/mendersoftware/mender-server-enterprise/commit/d6782c11825f31b3adb630d421afb81e41ad78e6))  by @merlin-northern


  Service provider tenant feature allows to control the tenants,
  which means we should be able to save autidlogs events
  for instance for tenant create or delete.

  We introduce a new object for the auditlog: Tenant.
- Parse @files using Go template for template extensions
([MEN-7546](https://northerntech.atlassian.net/browse/MEN-7546)) ([2b1105b](https://github.com/mendersoftware/mender-server-enterprise/commit/2b1105bd3bb8a0902484c3f3fcf510d413f48280))  by @alfrunes


  Files referenced by @ prefix and has one of the following file
  extensions will be processed using Go text/template:
   - .gotpl
   - .gotmpl
   - .gotemplate
  Furthermore, files with the following suffixes uses the safer
  html/template parser:
   - .htpl
   - .htmpl
   - .htmltemplate
- Update children tenants' addons when updating a SP tenant
([MEN-7511](https://northerntech.atlassian.net/browse/MEN-7511)) ([86addcc](https://github.com/mendersoftware/mender-server-enterprise/commit/86addcc9762430162c2b4fec00060fad85bdb4fb))  by @tranchitella
- Add support for providing an RBAC role name when assigning users through the internal API end-point
([MEN-7494](https://northerntech.atlassian.net/browse/MEN-7494)) ([f0f41a6](https://github.com/mendersoftware/mender-server-enterprise/commit/f0f41a69a88b0b3d0e4b60a71814b2a10ea1f509))  by @tranchitella
- Made search results reopen whenever the search field is clicked again and has a search term
([MEN-6894](https://northerntech.atlassian.net/browse/MEN-6894)) ([c36eb96](https://github.com/mendersoftware/mender-server-enterprise/commit/c36eb96c9c1790a0b23f05507021378c59267690))  by @mzedel
- Do not allow SSO configuration updates to children tenants
([MEN-7370](https://northerntech.atlassian.net/browse/MEN-7370)) ([e477594](https://github.com/mendersoftware/mender-server-enterprise/commit/e477594471baa8a59916c19403f057d06d16baca))  by @tranchitella
- Allow assigning users to the child tenant when creating it
([MEN-7495](https://northerntech.atlassian.net/browse/MEN-7495)) ([4264c80](https://github.com/mendersoftware/mender-server-enterprise/commit/4264c80803ad8101068479d55d6fd7d592b01bfb))  by @tranchitella
- Emit audit logs when creating, updating and deleting children tenants
([MEN-7445](https://northerntech.atlassian.net/browse/MEN-7445)) ([5ac7d4f](https://github.com/mendersoftware/mender-server-enterprise/commit/5ac7d4f4d4e00aa559f6d69bc3f84593e92f342f))  by @tranchitella
- New permission sets for accessing and managing children tenants
([MEN-7369](https://northerntech.atlassian.net/browse/MEN-7369)) ([695cc94](https://github.com/mendersoftware/mender-server-enterprise/commit/695cc944e070e2c547841583f28eeca0d697c983))  by @kjaskiewiczz
- Internal end-point to retrieve limits for a list of tenants
([MEN-7476](https://northerntech.atlassian.net/browse/MEN-7476)) ([09bc4fd](https://github.com/mendersoftware/mender-server-enterprise/commit/09bc4fdbab0dca8a03c83fe48dcc5b66ef8d09cc))  by @tranchitella
- Internal endpoint to check if delta generation is enabled for a list of tenants
([MEN-7556](https://northerntech.atlassian.net/browse/MEN-7556)) ([235bbac](https://github.com/mendersoftware/mender-server-enterprise/commit/235bbac1eb6f93f8e1d080414abd4b2f6b268089))  by @tranchitella
- New endpoint for checking if a user with the given email address exists
([MEN-7564](https://northerntech.atlassian.net/browse/MEN-7564)) ([0b1bc64](https://github.com/mendersoftware/mender-server-enterprise/commit/0b1bc6400494033cdef86bc8f78221b594d0f5b3))  by @tranchitella
- Calculate the SP tenant device count when creating and updating children tenants
([MEN-7560](https://northerntech.atlassian.net/browse/MEN-7560)) ([87baa8f](https://github.com/mendersoftware/mender-server-enterprise/commit/87baa8f4c2a43c50433a220f0d27699cc32c16be))  by @tranchitella
- Add device limits and binary delta configs when listing children tenants
([MEN-7557](https://northerntech.atlassian.net/browse/MEN-7557)) ([7787597](https://github.com/mendersoftware/mender-server-enterprise/commit/778759705a5fa8cc455166dfb205394cafcee669))  by @tranchitella
- Added feedback dialog
([MEN-7355](https://northerntech.atlassian.net/browse/MEN-7355)) ([8c0a3ba](https://github.com/mendersoftware/mender-server-enterprise/commit/8c0a3baa2fa4e4cf935d818235e651bd4c5ed85c))  by @mzedel
- Cache the number of accepted devices in the tenant limit
([MEN-7607](https://northerntech.atlassian.net/browse/MEN-7607)) ([d28e51d](https://github.com/mendersoftware/mender-server-enterprise/commit/d28e51d707e1c24f16e23103bc0e1176da0e3a89))  by @tranchitella
- Return the count of accepted devices when listing children tenants
([MEN-7608](https://northerntech.atlassian.net/browse/MEN-7608)) ([d7e8084](https://github.com/mendersoftware/mender-server-enterprise/commit/d7e80846b45ce752dd8b83ecb9c359a31f554ae7))  by @tranchitella
- Update the number of accepted devices in the tenant limit when accepting, rejecting and decommissioning devices
([MEN-7607](https://northerntech.atlassian.net/browse/MEN-7607)) ([c5011be](https://github.com/mendersoftware/mender-server-enterprise/commit/c5011be96807d98be9e40559b942c3b6dd6697d5))  by @tranchitella
- New endpoint for listing deployments
([MEN-7541](https://northerntech.atlassian.net/browse/MEN-7541)) ([afb1566](https://github.com/mendersoftware/mender-server-enterprise/commit/afb15665474440751e0463582e5d08d07b626da8))  by @kjaskiewiczz
- Add `version` command to all Go binaries
 ([ff439c9](https://github.com/mendersoftware/mender-server-enterprise/commit/ff439c93552ae7e32d3a0cb932339902f45271ec))  by @alfrunes


  The `version` command will display the app version (linked at build
  time) as well as runtime version and commit SHA1.
- Return device limit and current usage in `user/tenant` for SP tenants
([MEN-7656](https://northerntech.atlassian.net/browse/MEN-7656)) ([bfe2d46](https://github.com/mendersoftware/mender-server-enterprise/commit/bfe2d46b0b261d7beacbf6056f340278353f6262))  by @tranchitella
- Record creation and deletion of Personal Access Tokens
([MEN-6535](https://northerntech.atlassian.net/browse/MEN-6535)) ([93a2b6e](https://github.com/mendersoftware/mender-server-enterprise/commit/93a2b6e6c8db85add1356aa61a0cb5272eee5f24))  by @merlin-northern
- Do not allow device auth requests in Service Provider tenants
([MEN-7715](https://northerntech.atlassian.net/browse/MEN-7715)) ([ac0672a](https://github.com/mendersoftware/mender-server-enterprise/commit/ac0672aad8eff6469cb5cd6a8027f2bf57a77b62))  by @tranchitella
- Set a hard-coded maximum artifact size to enable the server-side generation of delta artifacts
([MEN-7699](https://northerntech.atlassian.net/browse/MEN-7699)) ([9301b19](https://github.com/mendersoftware/mender-server-enterprise/commit/9301b19d7dd130f6a6feba75ed36f7b2f518665c))  by @tranchitella


  `DEPLOYMENTS_SERVER_SIDE_DELTA_GENERATION_MAX_ARTIFACT_SIZE_MB`
  environment variable is the maximum size of the artifact that can be
  used for server-side delta generation. If the artifact size exceeds this
  value, the deployment creation will fail.
- Skip large artifacts when evaluating server-side generation of delta artifacts
([MEN-7699](https://northerntech.atlassian.net/browse/MEN-7699)) ([0bf6547](https://github.com/mendersoftware/mender-server-enterprise/commit/0bf654791c2deba86a2d3ea93b91678fb72d3cfc))  by @tranchitella


  When evaluating whether it is possible to generate server-side delta
  artifacts for a given device deployment, ignore artifacts which are
  bigger than the specified threshold. This way, the deployment will fall
  back to the full artifact instead of generating an (expensive) delta.
- Emit audit logs when assigning users to tenants
([MEN-7784](https://northerntech.atlassian.net/browse/MEN-7784)) ([cf8daae](https://github.com/mendersoftware/mender-server-enterprise/commit/cf8daae29fe42a710991d7f4d55ddd9a35490a09))  by @tranchitella
- Emit auditlog when deleting a single child tenant
([MEN-7805](https://northerntech.atlassian.net/browse/MEN-7805)) ([5c5cde4](https://github.com/mendersoftware/mender-server-enterprise/commit/5c5cde491a3eb934bbea53457d6af24585533d37))  by @tranchitella

- *(auditlogs)* internal endpoint to delete all records related to a tenant ([MEN-7307](https://northerntech.atlassian.net/browse/MEN-7307))

- *(deployments)* apply RBAC based on the release tags ([MEN-6351](https://northerntech.atlassian.net/browse/MEN-6351))
- *(deployments)* Add configuration for max data size when generating artifacts
- *(deployments)* Adds a new configuration option for setting the max data section size when generating an image with a default of 512MiB. The configuraiton path is `storage.max_generate_data_size` or environment variable `DEPLOYMENTS_STORAGE_MAX_GENERATE_DATA_SIZE`. ([MEN-7134](https://northerntech.atlassian.net/browse/MEN-7134))
- *(deployments)* remove delta jobs on image delete and store image ids in jobs ([MEN-7141](https://northerntech.atlassian.net/browse/MEN-7141))
- *(deployments)* extra logs around server-side delta generation.
- *(deployments)* prevent the creation of deployments if there is already an active deployment with the same constructor parameters ([MEN-6622](https://northerntech.atlassian.net/browse/MEN-6622))
- *(deployments)* cache for /next ([MEN-7256](https://northerntech.atlassian.net/browse/MEN-7256))
- *(deployments)* internal endpoint to delete all records related to a tenant ([MEN-7314](https://northerntech.atlassian.net/browse/MEN-7314))
- *(deployments)* New configuration option `mongo_read_preference_devices_api`
  The new configuration option allows overriding the read preference when serving device requests (`/deployments/next`) to allow load balancing the queries across the replicas. The configuration can be overwritten using environment variable `DEPLOYMENTS_MONGO_READ_PREFERENCE_DEVICES_API`. ([MC-7519](https://northerntech.atlassian.net/browse/MC-7519))
- *(deviceauth)* accept and support preauth at any time ([MEN-6961](https://northerntech.atlassian.net/browse/MEN-6961))
- *(deviceauth)* sync check\_in\_time with inventory if reporting is disabled ([MEN-7202](https://northerntech.atlassian.net/browse/MEN-7202))
- *(deviceauth)* automatically accept the device management endpoint ([MEN-7194](https://northerntech.atlassian.net/browse/MEN-7194))
- *(deviceauth)* internal endpoint to delete all records related to a tenant ([MEN-7311](https://northerntech.atlassian.net/browse/MEN-7311))
- *(deviceconfig)* internal endpoint to delete all records related to a tenant ([MEN-7312](https://northerntech.atlassian.net/browse/MEN-7312))
- *(deviceconnect)* Forward filetransfer statuscode from client ([ALV-209](https://northerntech.atlassian.net/browse/ALV-209))
- *(deviceconnect)* internal endpoint to delete all records related to a tenant ([MEN-7317](https://northerntech.atlassian.net/browse/MEN-7317))
- *(devicemonitor)* internal endpoint to delete all records related to a tenant ([MEN-7318](https://northerntech.atlassian.net/browse/MEN-7318))
- *(generate-delta-worker)* notify deployments delta jobs status on image upload ([MEN-7141](https://northerntech.atlassian.net/browse/MEN-7141))

- *(gui)* treat devices which didn't contact server after being accepted as offline ([MEN-6880](https://northerntech.atlassian.net/browse/MEN-6880))
- *(gui)* treat devices without update\_ts as offline
- *(gui)  The new "$ltne" filter operator allows to get list of device where the update\_ts is lower than given value or update\_ts doesn't exist. ([MEN-6880](https://northerntech.atlassian.net/browse/MEN-6880))
- *(gui)* Added UI interface to save the Open ID connect Single sign-on ([MEN-6922](https://northerntech.atlassian.net/browse/MEN-6922))
- *(gui)* allow to save SAML Single Sign-On without config providing
- *(gui)* allow personal access tokens generation for the SSO users ([MEN-6824](https://northerntech.atlassian.net/browse/MEN-6824))
- *(gui)* Added releases quick actions support ([MEN-6859](https://northerntech.atlassian.net/browse/MEN-6859))
- *(gui)* added two-step login for enterprise users ([MEN-6823](https://northerntech.atlassian.net/browse/MEN-6823))
- *(gui)* enabled password reset during user creation ([MEN-7192](https://northerntech.atlassian.net/browse/MEN-7192))
- *(gui)* use inventory's check\_in\_time to extract and list offline devices ([MEN-7251](https://northerntech.atlassian.net/browse/MEN-7251))
- *(gui)* gave device deployment log files more descriptive file names ([MEN-7221](https://northerntech.atlassian.net/browse/MEN-7221))
- *(gui)* made log viewer wider to ease going through deployment logs ([MEN-7220](https://northerntech.atlassian.net/browse/MEN-7220))
- *(gui)* added copyable userid to user information ([MEN-7277](https://northerntech.atlassian.net/browse/MEN-7277))
- *(gui)* allowed adding users by user id in user creation dialog ([MEN-7277](https://northerntech.atlassian.net/browse/MEN-7277))
- *(gui)* restructured account menu & added option to switch tenant in supporting setups ([MEN-6906](https://northerntech.atlassian.net/browse/MEN-6906))
- *(gui)* let device details remain open when adding the device to a group ([MEN-7336](https://northerntech.atlassian.net/browse/MEN-7336))
- *(gui)* added notification about changes to the device offline threshold ([MEN-7288](https://northerntech.atlassian.net/browse/MEN-7288))

- *(inventory)* do not set updated\_ts field when inserting the device ([MEN-6878](https://northerntech.atlassian.net/browse/MEN-6878))
- *(inventory)* introduce "$ltne" operator
  The meaning of the new operator is lower then or doesn't exist. ([MEN-6880](https://northerntech.atlassian.net/browse/MEN-6880))
- *(inventory)* PUT endpoint to update a saved filter ([MEN-7263](https://northerntech.atlassian.net/browse/MEN-7263))
- *(inventory)* internal endpoint to delete all records related to a tenant ([MEN-7310](https://northerntech.atlassian.net/browse/MEN-7310))

- *(iot-manager)* process webhook requests asynchronously, returing `202 Accepted` instead of `204 No Content` or `200 OK` ([MEN-7227](https://northerntech.atlassian.net/browse/MEN-7227))
- *(iot-manager)* add a timeout for webhook requests, defaults to 10 seconds; you can modify it using the `webhooks_timeout_seconds` configuration setting ([MEN-7227](https://northerntech.atlassian.net/browse/MEN-7227))
- *(iot-manager)* internal endpoint to delete all records related to a tenant ([MEN-7319](https://northerntech.atlassian.net/browse/MEN-7319))

- *(tenantadm)* Decommission `server_priv_key_path` configuration
- *(tenantadm)  Generate an opaque random string for tenant token instead of using JWTs.
- *(tenantadm)* Add commandline option to delete expired users from hubspot ([MC-7228](https://northerntech.atlassian.net/browse/MC-7228))
- *(tenantadm)* Add new command `server` and move `--automigrate` to it
  This commit restores the default `automigrate` behavior to the root command, but default for the `server` command is `false`/disabled. This makes the service CLI consistent with the other Mender services without breaking the Docker Compose setup ([MEN-6999](https://northerntech.atlassian.net/browse/MEN-6999))
- *(tenantadm)* internal endpoint to delete all records related to a tenant ([MEN-7321](https://northerntech.atlassian.net/browse/MEN-7321))
- *(tenantadm)* New cli command `tenantadm maintenance delete-suspended-tenants`
  The new command will delete tenants that have been suspended for longer than a given number of days. ([MEN-7412](https://northerntech.atlassian.net/browse/MEN-7412))
- *(tenantadm)* New API to get and update Stripe billing profile
  Two new enpoints are added:

  - GET /api/management/v2/tenantadm/billing/profile
  - PATCH /api/management/v2/tenantadm/billing/profile Which are able to update the billing profile in Stripe. ([MEN-7422](https://northerntech.atlassian.net/browse/MEN-7422))
- *(tenantadm)* endpoint for triggering tenant removal workflow ([MEN-7359](https://northerntech.atlassian.net/browse/MEN-7359))
- *(tenantadm)* management end-point to create new tenants from a service provider tenant ([MEN-7308](https://northerntech.atlassian.net/browse/MEN-7308))
- *(tenantadm)* create an admin user in the newly created child tenant ([MEN-7448](https://northerntech.atlassian.net/browse/MEN-7448))
- *(tenantadm)* new management end-point to list the children tenants ([MEN-7367](https://northerntech.atlassian.net/browse/MEN-7367))
- *(tenantadm)* management endpoint for modifying children tenant configuration ([MEN-7366](https://northerntech.atlassian.net/browse/MEN-7366))
- *(tenantadm)* extend Hubspot cronjob to populate billing contact ([MEN-7423](https://northerntech.atlassian.net/browse/MEN-7423))

- *(useradm)* allow Personal Access Tokens with SAML 2.0 users ([MEN-6725](https://northerntech.atlassian.net/browse/MEN-6725))
- *(useradm)* create and get OpenID Connect providers ([MEN-6611](https://northerntech.atlassian.net/browse/MEN-6611))
- *(useradm)* OpenId Connect support via existing oauth2 code. ([MEN-6611](https://northerntech.atlassian.net/browse/MEN-6611))
- *(useradm)* change RBAC part of user model to allow tenants to share users ([MEN-6901](https://northerntech.atlassian.net/browse/MEN-6901))
- *(useradm)* RBAC for release tags ([MEN-6350](https://northerntech.atlassian.net/browse/MEN-6350))
- *(useradm)* new user model allowing access to multiple tenants by single user ([MEN-6902](https://northerntech.atlassian.net/browse/MEN-6902))
- *(useradm)* assign user to a given tenant ([MEN-6900](https://northerntech.atlassian.net/browse/MEN-6900))
- *(useradm)* return list of tenant Ids user has access to when user is asking for own user data ([MEN-6899](https://northerntech.atlassian.net/browse/MEN-6899))
- *(useradm)* endpoint for getting user token for particular tenant ([MEN-6899](https://northerntech.atlassian.net/browse/MEN-6899))
- *(useradm)* SAML: pass the identity provider metadata via url ([MEN-6731](https://northerntech.atlassian.net/browse/MEN-6731))
- *(useradm)* OIDC PUT with provider settings. ([MEN-7050](https://northerntech.atlassian.net/browse/MEN-7050))
- *(useradm)* support for two-steps log in for users ([MEN-6822](https://northerntech.atlassian.net/browse/MEN-6822))
- *(useradm)* include info about tenant Ids when retruning internal and own user
- *(useradm)* change RBAC part of user model to allow tenants to share users ([MEN-6901](https://northerntech.atlassian.net/browse/MEN-6901))
- *(useradm)* new user model allowing access to multiple tenants by single user ([MEN-6902](https://northerntech.atlassian.net/browse/MEN-6902))
- *(useradm)* assign user to a given tenant ([MEN-6900](https://northerntech.atlassian.net/browse/MEN-6900))
- *(useradm)* return list of tenant Ids user has access to when user is asking for own user data ([MEN-6899](https://northerntech.atlassian.net/browse/MEN-6899))
- *(useradm)* endpoint for getting user token for particular tenant ([MEN-6899](https://northerntech.atlassian.net/browse/MEN-6899))
- *(useradm)* include info about tenant Ids when retruning internal and own user
- *(useradm)* include info about SSO kind when retruning SSO Config from database
- *(useradm)* send password reset on user creation
- *(useradm)* when creating deployment check for permissions to releases
  Creating deployment requires permissions to particular endpoints, permissions to devices user is trying deploy to and permissions to releases user is trying to deploy. Normally, when permissions to devices or releases are needed, user can create permissions with scope to limit access to device groups or releases with given tag. Because of the limitation in current RBAC implementation it's not possible to add more than one scope to single permission. With this PR we introduce additional checks to workaround this limitation. ([MEN-7165](https://northerntech.atlassian.net/browse/MEN-7165))
- *(useradm)* return the SSO info (ID and type) if no password is provided
- *(useradm)* resolve tenant ids in /me to tenant names ([MEN-7279](https://northerntech.atlassian.net/browse/MEN-7279))
- *(useradm)* internal ep to set SSO config for a tenant based on given tenant ([MEN-7309](https://northerntech.atlassian.net/browse/MEN-7309))
- *(useradm)* internal endpoint to delete all records related to a tenant ([MEN-7313](https://northerntech.atlassian.net/browse/MEN-7313))

- *(workflows)* Add encoding option "html" for html-escaping string parameters ([MEN-7003](https://northerntech.atlassian.net/browse/MEN-7003))
- *(workflows)* internal endpoint to delete all records related to a tenant ([MEN-7320](https://northerntech.atlassian.net/browse/MEN-7320))
- *(workflows)* purging a tenant from the database ([MEN-7322](https://northerntech.atlassian.net/browse/MEN-7322))
- *(workflows)* new workflow create\_tenant to create child tenants ([MEN-7308](https://northerntech.atlassian.net/browse/MEN-7308))






### Performance


- *(generate-delta)* Do not store upload form request in memory
 ([4b5a779](https://github.com/mendersoftware/mender-server-enterprise/commit/4b5a779ab4a3fc17024116a3c998266869a98c88))  by @alfrunes

- Lower storage footprint for generate delta worker
 ([2fb6de2](https://github.com/mendersoftware/mender-server-enterprise/commit/2fb6de2b024bbf49c0752b268afa7f6729e27ca4))  by @alfrunes


  Replaced temporary files with UNIX pipes.
- Only count tenants when required
 ([55e953b](https://github.com/mendersoftware/mender-server-enterprise/commit/55e953b3b9112fadd04abe3bfe350afd27b23042))  by @alfrunes


  In most instances the tenant count is discarded.




### Styling


- Use correct RestErr interface for empty log messages
 ([597a7c1](https://github.com/mendersoftware/mender-server-enterprise/commit/597a7c13a42c8d40d45f87361b762b49416a5a88))  by @alfrunes




### Build

- (gui) **BREAKING**: Changed container image to unprivileged port 8090 and unprivileged user ([13b2268](https://github.com/mendersoftware/mender-server/commit/13b2268027f678e52ce69aa8bfa912c713d12093)) by @alfrunes

- (docker) **BREAKING**: Changed container image tag scheme from `mender-x.y.z` to `vX.Y.Z`

  The new versioning scheme uses the **Mender Server** version which is decoupled from the other components in the Mender ecosystem.

- (docker) **BREAKING**: Container repository paths changed for enterprise components

  The following table list the breaking container repository paths starting from 4.0.0:
  |  Docker repository < 4.0.0                                            |  Container repository >= 4.0.0                                            |
  | --------------------------------------------------------------------- | ------------------------------------------------------------------------- |
  | registry.mender.io/mendersoftware/auditlogs:mender-X.Y.Z              | registry.mender.io/mender-server-enterprise/auditlogs:vX.Y.Z              |
  | docker.io/mendersoftware/create-artifact-worker:mender-X.Y.Z          | registry.mender.io/mender-server-enterprise/create-artifact-worker:vX.Y.Z |
  | registry.mender.io/mendersoftware/deployments-enterprise:mender-X.Y.Z | registry.mender.io/mender-server-enterprise/deployments:vX.Y.Z            |
  | registry.mender.io/mendersoftware/deviceauth-enterprise:mender-X.Y.Z  | registry.mender.io/mender-server-enterprise/deviceauth:vX.Y.Z             |
  | docker.io/mendersoftware/deviceconfig:mender-X.Y.Z                    | registry.mender.io/mender-server-enterprise/deviceconfig:vX.Y.Z           |
  | docker.io/mendersoftware/deviceconnect:mender-X.Y.Z                   | registry.mender.io/mender-server-enterprise/deviceconnect:vX.Y.Z          |
  | registry.mender.io/mendersoftware/devicemonitor:mender-X.Y.Z          | registry.mender.io/mender-server-enterprise/devicemonitor:vX.Y.Z          |
  | registry.mender.io/mendersoftware/generate-delta-worker:mender-X.Y.Z  | registry.mender.io/mender-server-enterprise/generate-delta-worker:vX.Y.Z  |
  | registry.mender.io/mendersoftware/inventory-enterprise:mender-X.Y.Z   | registry.mender.io/mender-server-enterprise/inventory:vX.Y.Z              |
  | docker.io/mendersoftware/iot-manager:mender-X.Y.Z                     | registry.mender.io/mender-server-enterprise/iot-manager:vX.Y.Z            |
  | registry.mender.io/mendersoftware/tenantadm:mender-X.Y.Z              | registry.mender.io/mender-server-enterprise/tenantadm:vX.Y.Z              |
  | registry.mender.io/mendersoftware/useradm:mender-X.Y.Z                | registry.mender.io/mender-server-enterprise/useradm:vX.Y.Z                |
  | registry.mender.io/mendersoftware/workflows:mender-X.Y.Z              | registry.mender.io/mender-server-enterprise/workflows:vX.Y.Z              |
  | registry.mender.io/mendersoftware/workflows-worker:mender-X.Y.Z       | registry.mender.io/mender-server-enterprise/workflows:vX.Y.Z              |

- **BREAKING**: Binary names changed for enterprise components

  Binaries that previously contained an enterprise suffix has that suffix removed:

  - deployments-enterprise -> deployments
  - deviceauth-enterprise -> deviceauth
  - inventory-enterprise -> inventory
  - useradm-enterprise -> useradm
  - workflows-enterprise -> workflows

  Following this change, the default configuration path in `/etc` no longer includes the `-enterprise` suffix.

- *(docker)* Add build stage to Dockerfiles
 ([ba3692e](https://github.com/mendersoftware/mender-server-enterprise/commit/ba3692eb52dd146081014de05ffae9b6331d6ff6))  by @alfrunes


  The Dockerfiles are now self-contained by moving the build stage into
  the Dockerfile.

- *(docker)* Build images on BUILDPLATFORM
 ([44e5b7f](https://github.com/mendersoftware/mender-server-enterprise/commit/44e5b7f574f9437ccad0954dafbf75ea78f511f3))  by @alfrunes

- *(docker)* Use make(1) when building inside docker images
 ([153269e](https://github.com/mendersoftware/mender-server-enterprise/commit/153269e6916ddfde68d4846621cd87a8b89c3dcf))  by @alfrunes


  For consistent builds.

- *(docker)* Integrate enterprise services with new Dockerfiles
 ([dacebf6](https://github.com/mendersoftware/mender-server-enterprise/commit/dacebf6411777916beb5b4eb01021d72a099fdc2))  by @alfrunes

- *(make)* Update `docker` targets to use updated Dockerfiles
 ([11f26d6](https://github.com/mendersoftware/mender-server-enterprise/commit/11f26d6684f4732e3003cac69b4d03b11ae9924c))  by @alfrunes


  Refactored common parts to parent directory.

- *(make)* Change default target to `docker` and add variable TAGS
 ([92ac12a](https://github.com/mendersoftware/mender-server-enterprise/commit/92ac12a512235c8b0013513935fe63bb712fea85))  by @alfrunes


  Containers are the primary build artifacts for this repo so it makes
  sense to build them by default.

- *(make)* Fix acceptance test targets after refactor
 ([70919bd](https://github.com/mendersoftware/mender-server-enterprise/commit/70919bdda6ca3af15bdd61f3cbe03f01156fe71c))  by @alfrunes


  Put common acceptance test targets in Makefile.common and made
  exceptions for `create-artifact-worker` and `reporting`.

- *(make)* Do not expand `go` shell commands unconditionally
 ([1c68b83](https://github.com/mendersoftware/mender-server-enterprise/commit/1c68b833d7823f6b0666e0f290ea0c073f482634))  by @alfrunes

- *(make)* Run acceptance tests without rebuilding the containers
 ([ce241cc](https://github.com/mendersoftware/mender-server-enterprise/commit/ce241cc9cb5da92372787fbcd236a8b43c705242))  by @alfrunes


  Removed the dependency on `docker-acceptance` for the
  `test-acceptance-run`.

- *(make)* `test-unit` target runs in same environment as build
 ([141ea40](https://github.com/mendersoftware/mender-server-enterprise/commit/141ea401f90b63d6667d403743b294908fb662b1))  by @alfrunes

- *(make)* Change TAGS behavior to always include required build tags
 ([5bae608](https://github.com/mendersoftware/mender-server-enterprise/commit/5bae608e706384cd5ebb88dbd6869291c1fa33d8))  by @alfrunes

- *(make)* Rename DOCKER_ARGS to DOCKER_BUILDARGS, TAGS to BUILDTAGS
 ([1a97891](https://github.com/mendersoftware/mender-server-enterprise/commit/1a978917316ce620ecc0fee01002ece409437765))  by @alfrunes


  It seems like Gitlab has a built in TAGS env variable which conflicts
  with the Make environment.

- *(make)* Add `docker-pull` target for pulling images
 ([37f4391](https://github.com/mendersoftware/mender-server-enterprise/commit/37f4391dee7624d583c68aba6235f7f61deddd76))  by @alfrunes

- *(make)* Define DOCKER_PLATFORM template as multiline variable
 ([0db0c9a](https://github.com/mendersoftware/mender-server-enterprise/commit/0db0c9ad67430ba3bbe109cb9d5e8613eb2af621))  by @alfrunes

- *(make)* Fix tag override for `docker-acceptance`
 ([7f0b260](https://github.com/mendersoftware/mender-server-enterprise/commit/7f0b26011d422b539cdbdf6acbcb22156ac6a076))  by @alfrunes


  MENDER_IMAGE_TAG_TEST should set the tag when building the target.

- *(make)* Remove make 4.4 function `let`
 ([75f980e](https://github.com/mendersoftware/mender-server-enterprise/commit/75f980eb118298e0fcaf3dc08dcda0eb46131541))  by @alfrunes

- *(make)* Added target `docker-publish` for publishing images
 ([c400b04](https://github.com/mendersoftware/mender-server-enterprise/commit/c400b04c2c30a4a2e2ac5a2e2f53fddf44caeffb))  by @alfrunes

- *(make)* Update publish registry to `registry.mender.io`
 ([b5608ef](https://github.com/mendersoftware/mender-server-enterprise/commit/b5608ef36846f506f842f9a1a66db24927ec2e7a))  by @alfrunes

- *(make)* Split MENDER_PUBLISH_REGISTRY into registry and repository
 ([e27c770](https://github.com/mendersoftware/mender-server-enterprise/commit/e27c77001704218b36442641598e3b3d1ef65fd1))  by @alfrunes

- *(make)* Add enterprise version build id
 ([d115b84](https://github.com/mendersoftware/mender-server-enterprise/commit/d115b848f436aa119f29ad79b8cd7e86b90c8666))  by @alfrunes


  Updates the linked version symbol to contain a suffix `+enterprise`.

- *(test)* Force serialize unit tests for tenantadm
 ([9557aef](https://github.com/mendersoftware/mender-server-enterprise/commit/9557aef4afd32f94d8fdee3bb6c519387cd0c38f))  by @alfrunes

- *(test)* Force serialize unit tests for deviceauth
 ([a0ab55e](https://github.com/mendersoftware/mender-server-enterprise/commit/a0ab55e6f84242b34b176520b7c2218e1c1d678e))  by @alfrunes





### Check


- Make `sed(1)` Linux compatible again
 ([1271396](https://github.com/mendersoftware/mender-server-enterprise/commit/1271396faf49b2220a39cd5e4ef7a1cd1cdee443))  by @alfrunes


  Replace flag `-i=''` with `-i.bak` and removing the files.




### Refac


- *(compose)* Refactor SeaweedFS topology and optimize startup/shutdown time
 ([fe7ee2e](https://github.com/mendersoftware/mender-server-enterprise/commit/fe7ee2eb37177521cb9ab060f551b2d441c86874))  by @alfrunes


  Instead of running SeaweedFS as a monolith using the `server` command,
  we explicitly launch all services in different containers. It appears
  that the `server` command has some issues when initializing the master
  and sometimes enter a deadlock the healthcheck interval is too low at
  startup. Moreover, running the services in different containers makes it
  easier to debug and interpret the logs.

- *(iotcore)* Break on errors instead of falling through
 ([733f8ab](https://github.com/mendersoftware/mender-server-enterprise/commit/733f8ab45cc8a76566b79d86507306b78742f324))  by @alfrunes


  Using long chains of fallthrough error conditions makes it very
  difficult to read and error prone to extend. Refactoring to use common
  coding patterns instead.

- Use an overlay directory to create Makefiles and Dockerfiles
 ([85e93e0](https://github.com/mendersoftware/mender-server-enterprise/commit/85e93e0081410b1fa295ddd6b639af969d3f47ac))  by @alfrunes


  Allows for easier individual customization required for accepatnce
  tests.
- Remove duplication of converting Customer to BillingProfile
 ([4265eea](https://github.com/mendersoftware/mender-server-enterprise/commit/4265eeab625122060bb2eaf4c1648c568cf38b38))  by @alfrunes
- Change schema to align with Stripe APIs
 ([a5b347d](https://github.com/mendersoftware/mender-server-enterprise/commit/a5b347d2db39d25465aacf9c155d4633bf4362a2))  by @alfrunes


  To make the PATCH endpoint follow correct semantics, the schema has been
  changed to allow updating of single fields. Specifically, all attributes
  in the BillingProfile are changed to pointers to allow this behavior.
- Reimplement stripe.CreateCustomerWithIntent with billing profile
 ([819bf83](https://github.com/mendersoftware/mender-server-enterprise/commit/819bf83477858f0dd22175e061a47aa8ad5f25b8))  by @alfrunes
- Move compat tests to dedicated test suite
 ([059f437](https://github.com/mendersoftware/mender-server-enterprise/commit/059f4375d3b33073e711fdbf81212a2cd5dacfbb))  by @alfrunes
- Share path for upserting next deployment for a device
 ([5b863c9](https://github.com/mendersoftware/mender-server-enterprise/commit/5b863c951945528f090b55694d1d18c707940bfa))  by @alfrunes


  Makes conflict resolution with open source easier to manage.




### Revert


- *(docker)* Revert generate-delta-worker dockerfile
 ([d205b3e](https://github.com/mendersoftware/mender-server-enterprise/commit/d205b3e4a279da0ee9660f3e14f828012ff0f5ab))  by @alfrunes


  Reverts the dockerfile to the upstream docker file with the two
  exceptions of copying the binaries from this repositories rather than
  relying on master docker images.

- *(generate-delta-worker)* Entrypoint launches workflows worker
 ([b1bb94f](https://github.com/mendersoftware/mender-server-enterprise/commit/b1bb94f5cc26c4f287b01a6a5196e34681b5e9e3))  by @alfrunes


  This was changed by mistake when composing the new Dockerfile.

- Change docker entrypoint to launch workflows worker
 ([0d39c96](https://github.com/mendersoftware/mender-server-enterprise/commit/0d39c964eeec8b833604b91be7f707c7ce1357a4))  by @alfrunes


  This was done by mistake when updating the Dockerfile for the monorepo.
- "chore: Use the correct license (Apache 2.0)"
 ([127c90f](https://github.com/mendersoftware/mender-server-enterprise/commit/127c90fb49110b42dc260fbf5ebf2318b68aa247))  by @alfrunes


  This reverts commit 8cc0a92533444b5e25cc0ea4115f02448fdb21cb.
- "fix(gui): fixed an issue that caused number comparisons in device filters to not work"
 ([787237e](https://github.com/mendersoftware/mender-server-enterprise/commit/787237ec8689d96c73beefbc74bcea7b96b274ba))  by @mzedel


  This reverts commit 84e2398fece6b10fddcf6f60e3ff744af903c707.
  Signed-off-by: Manuel Zedel <manuel.zedel@northern.tech>
- Revert "docs(deviceauth): migration to OpenAPI3"
 ([93ab08a](https://github.com/mendersoftware/mender-server-enterprise/commit/93ab08ab6051aec3508bb550a4455d30ba2a9b56))  by @kjaskiewiczz


  This reverts commit f7a33e9a71339522ee33f3808e7d6a8598144d2a.
- Revert the stripe interface for creating customers
 ([d6fc8a3](https://github.com/mendersoftware/mender-server-enterprise/commit/d6fc8a397141897f5e0c961819bf6b99d7e28883))  by @alfrunes


  Will create the new signup flow using a reimplementation to prevent
  accidental changes to the old behavior.



