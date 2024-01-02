---
title: mender-gateway
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

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
