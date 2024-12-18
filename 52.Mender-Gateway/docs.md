---
title: Mender Gateway
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-gateway 2.0.0

_Released 12.18.2024_

### Changelogs

#### mender-gateway (2.0.0)

New changes in mender-gateway since 1.2.1:

##### Bug Fixes

* allow different keys for auth request and client certificate.
  ([MEN-7046](https://northerntech.atlassian.net/browse/MEN-7046))
* fix: added public CAs to the Docker container build
  ([MC-7281](https://northerntech.atlassian.net/browse/MC-7281))
* Process `--log-level` before loading configuration

##### Features

* mTLS: cache and protect with force the preauth requests.
  ([MEN-6928](https://northerntech.atlassian.net/browse/MEN-6928))
* Configuration for adding trusted certificate authority

  The new configuration `UpstreamServer.CACertificate` (env:
  upstream_server_ca_certificate` specifies a path to a file containing a
  PEM-encoded certificate chain of trusted CAs.
  ([MEN-6174](https://northerntech.atlassian.net/browse/MEN-6174))
* Load config from environment variables

  Exposes the following environment variables to override the config
  loaded from the file:
   - ARTIFACTS_PROXY_CACHE_LINK_EXPIRE_DURATION
   - ARTIFACTS_PROXY_CACHE_ENABLED
   - ARTIFACTS_PROXY_CACHE_PATH
   - ARTIFACTS_PROXY_CACHE_SECRET
   - ARTIFACTS_PROXY_DOMAIN_WHITELIST
   - ARTIFACTS_PROXY_ENABLED
   - ARTIFACTS_PROXY_GATEWAY_URL
   - DEVICE_SYSTEM_ENABLED
   - DEVICE_SYSTEM_ID
   - HTTPS_ENABLED
   - HTTPS_LISTEN
   - HTTPS_MINIMUM_TLS_VERSION
   - HTTPS_SERVER_CERTIFICATE
   - HTTPS_SERVER_KEY
   - HTTP_ENABLED
   - HTTP_LISTEN
   - MTLS_BLACKLIST_PATH
   - MTLS_CA_CERTIFICATE
   - MTLS_ENABLED
   - MTLS_ENABLE_CACHE
   - MTLS_MENDER_PASSWORD
   - MTLS_MENDER_USERNAME
   - UPSTREAM_SERVER_CA_CERTIFICATE
   - UPSTREAM_SERVER_INSECURE_SKIP_VERIFY
   - UPSTREAM_SERVER_URL

  ,
  ([MEN-7051](https://northerntech.atlassian.net/browse/MEN-7051), [MEN-7182](https://northerntech.atlassian.net/browse/MEN-7182))
* add support for running both HTTP and HTTPS servers at the same time
  ([MEN-7193](https://northerntech.atlassian.net/browse/MEN-7193))
* New configuration `MTLS_INSECURE_SKIP_CLIENT_EXPIRE_AFTER`

  This configuration skips checking the "Not After" attribute in client
  certificate in mutual TLS mode. Enabling this configuration is
  discouraged and should not be used in production environments.
  ([MEN-7363](https://northerntech.atlassian.net/browse/MEN-7363))

##### Other

* Bump golang Docker version to 1.22.1-alpine3.19
* use AutoAccept endpoint in mtls mode
  ([MEN-7194](https://northerntech.atlassian.net/browse/MEN-7194))


## mender-gateway 1.2.1

_Released 12.02.2024_

### Changelogs

#### mender-gateway (1.2.1)

New changes in mender-gateway since 1.2.0:

##### Bug Fixes

* set the correct `Content-Length` when modifying the inventory payload
  ([MEN-7738](https://northerntech.atlassian.net/browse/MEN-7738))


## mender-gateway 1.2.0

_Released 12.28.2023_

### Changelogs

#### mender-gateway (1.2.0)

New changes in mender-gateway since 1.1.0:

##### Features

* build and test using the latest version of golang
  ([QA-614](https://northerntech.atlassian.net/browse/QA-614))


## mender-gateway 1.1.0

_Released 02.20.2023_

### Changelogs

#### mender-gateway (1.1.0)

New changes in mender-gateway since 1.0.1:

##### Features

* New configuration DefaultInventory setting common device attributes

  The 'DefaultInventory' attribute in the root of the configuration object
  sets attributes that will be appended to what the device submits to the
  server. The attributes will not overwrite any value that the device may
  submit for the given attribute name.
  ([MEN-5853](https://northerntech.atlassian.net/browse/MEN-5853))
* New configuration option HTTPS.MinimumTLSVersion

  The new configuration sets the minimum TLS version accepted by the
  mender-gateway server.
  ([MEN-6090](https://northerntech.atlassian.net/browse/MEN-6090))
* Add `mender_gateway_system_id` to the mender-gateway
  inventory script installed along the software. This parameter is
  extracted from the `SystemID` filed in the configuration file when
  present. When not present, the inventory key will not be outputted.
  ([MEN-6287](https://northerntech.atlassian.net/browse/MEN-6287))


## mender-gateway 1.0.1

_Released 09.25.2022_

### Changelogs

#### mender-gateway (1.0.1)

New changes in mender-gateway since 1.0.0:

##### Other

* Licenses are now available in the package, instead of only
  online. ([MEN-5517](https://northerntech.atlassian.net/browse/MEN-5517))


## mender-gateway 1.0.0

_Released 06.14.2022_

### Changelogs

#### mender-gateway (1.0.0)

* First release of mender-gateway
