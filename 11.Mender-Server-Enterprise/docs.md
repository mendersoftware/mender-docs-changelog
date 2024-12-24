---
title: Mender Server Enterprise
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## 4.0.0-rc.5 - 2024-12-24


### Bug Fixes


- Stop user from having similar email and password
([MEN-6462](https://northerntech.atlassian.net/browse/MEN-6462)) ([3fa4a43](https://github.com/mendersoftware/mender-server-enterprise/commit/3fa4a432780a40fb9b8c37633c7feca6ba3445c5))  by @bahaa-ghazal






## v4.0.0-rc.4 - 2024-12-18

- CI fixes

## v4.0.0-rc.3 - 2024-12-18


### Bug Fixes


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

- *(iot-manager)* Save events for device inventory webhooks.
([MEN-7802](https://northerntech.atlassian.net/browse/MEN-7802)) ([755601c](https://github.com/mendersoftware/mender-server-enterprise/commit/755601ce9b51361e4433baef1caaf0841db743c4))  by @merlin-northern

- *(useradm)* Added missing textual description to PAT auditlog entries
([MEN-7770](https://northerntech.atlassian.net/browse/MEN-7770)) ([5523537](https://github.com/mendersoftware/mender-server-enterprise/commit/552353752737b2a4000bb69d83b0b77456dc55ed))  by @mzedel

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




### Documentation


- *(README)* Add step to clone repository
 ([f9d3bbd](https://github.com/mendersoftware/mender-server-enterprise/commit/f9d3bbde382bca4592f41e3d6be7e8292dcb221f))  by @alfrunes

- *(README)* Consistently add syntax highlighting to code blocks
 ([8583102](https://github.com/mendersoftware/mender-server-enterprise/commit/8583102cbbf49882b9a9ab1b80257516ec13dc24))  by @alfrunes

- Update README.md
 ([f7a1b09](https://github.com/mendersoftware/mender-server-enterprise/commit/f7a1b097726672dd40ed7df17551229c5cf6ce7f))  by @alfrunes


  Adjusted styling (note color, added 1st level indentation,  taxonomy i.e., Mender Server, Mender Enterprise) to make it easy to follow and read.
- Fix invalid internal API specs
 ([8a89b71](https://github.com/mendersoftware/mender-server-enterprise/commit/8a89b71e6c370da8a7fa467f47396d45b7a3fe52))  by @alfrunes
- Document how to bring up the Virtual Device for enterprise setup
 ([c674566](https://github.com/mendersoftware/mender-server-enterprise/commit/c674566e6d834c64d6e64d321c6e09b5f2a36259))  by @lluiscampos




### Features


- *(deployments)* New endpoint for getting release by name
([MEN-7575](https://northerntech.atlassian.net/browse/MEN-7575)) ([3a18e88](https://github.com/mendersoftware/mender-server-enterprise/commit/3a18e880ec5cddedc19ed08949777caedda4350d))  by @kjaskiewiczz

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




### Performance


- *(generate-delta)* Do not store upload form request in memory
 ([4b5a779](https://github.com/mendersoftware/mender-server-enterprise/commit/4b5a779ab4a3fc17024116a3c998266869a98c88))  by @alfrunes

- Lower storage footprint for generate delta worker
 ([2fb6de2](https://github.com/mendersoftware/mender-server-enterprise/commit/2fb6de2b024bbf49c0752b268afa7f6729e27ca4))  by @alfrunes


  Replaced temporary files with UNIX pipes.




### Refac


- Reimplement stripe.CreateCustomerWithIntent with billing profile
 ([819bf83](https://github.com/mendersoftware/mender-server-enterprise/commit/819bf83477858f0dd22175e061a47aa8ad5f25b8))  by @alfrunes




### Revert


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






## 4.0.0-rc.2 - 2024-10-31


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

- *(iot-core)* Incosistent serialization format for device private key
([MEN-7478](https://northerntech.atlassian.net/browse/MEN-7478)) ([6deadef](https://github.com/mendersoftware/mender-server-enterprise/commit/6deadef48a11f8f845fdb9c1e33ddf33a366d531))  by @alfrunes


  The generated key is serialized using SEC 1 (RFC5915) ASN.1 encoding,
  but encoded to PEM using PKCS8 (RFC5208) block header/trailer.

- *(iot_manager)* Context cancelled fix: cancel() called too early.
 ([d2c5921](https://github.com/mendersoftware/mender-server-enterprise/commit/d2c59211ee0df06eb845d2ba23c7c53b8d1888c5))  by @merlin-northern


  `defer cancel()` was called on a context outside the func(){}
  where it was used making it impossible to actually call the webhook
  on any real-world latency network.

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




### Documentation


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




### Features


- *(billing)* Add option to provide BillingProfile on signup from trial
([MEN-7468](https://northerntech.atlassian.net/browse/MEN-7468)) ([6dfccc4](https://github.com/mendersoftware/mender-server-enterprise/commit/6dfccc433aa6c014d9a1176c8d6020df92e2482d))  by @alfrunes


  Instead of taking the parameters from trial sign-up, the tenant can add
  Address and update company name when signing up for a paid plan.

- *(deployments)* Add filter field to deployment object
([MEN-7416](https://northerntech.atlassian.net/browse/MEN-7416)) ([fec5b91](https://github.com/mendersoftware/mender-server-enterprise/commit/fec5b91d59d07b1a0d85ccf077cd56aa5b192278))  by @kjaskiewiczz


  The filter field contains information about devices targeted by the
  deployment.

- *(gui)* Enabled webhook scope selection
([MEN-7455](https://northerntech.atlassian.net/browse/MEN-7455)) ([21dae98](https://github.com/mendersoftware/mender-server-enterprise/commit/21dae988469d5643a4528bef9a6e68ec75005c63))  by @mzedel

- *(gui)* Extended webhook event details
([MEN-7574](https://northerntech.atlassian.net/browse/MEN-7574)) ([92d7cc6](https://github.com/mendersoftware/mender-server-enterprise/commit/92d7cc667b368ea561576c7bd4a376c966d9e477))  by @mzedel

- *(gui)* Aligned webhook listing with updated design
([MEN-7573](https://northerntech.atlassian.net/browse/MEN-7573)) ([dcca0de](https://github.com/mendersoftware/mender-server-enterprise/commit/dcca0defcedfc62af7b441edf46b7254971a02ac))  by @mzedel

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




### Styling


- Use correct RestErr interface for empty log messages
 ([597a7c1](https://github.com/mendersoftware/mender-server-enterprise/commit/597a7c13a42c8d40d45f87361b762b49416a5a88))  by @alfrunes




### Build


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




