---
title: mender-binary-delta
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---


## mender-binary-delta 1.3.1

_Released 06.14.2022_

For internal consumption only.

## mender-binary-delta 1.3.0

_Released 09.28.2021_

### Changelogs

#### mender-binary-delta (1.3.0)

New changes in mender-binary-delta since 1.2.0:

* Remove harmless warning message about unhandled states.
* Fix failed rollback status when bootloader is the one to roll back.
* Fix integer overflow bug in the Artifact creation logic, where the
  `rootfs_image_checksum` would get truncated through the use of the 32-bit
  interface for JSON values in the JSON libary used.
  ([MEN-4516](https://tracker.mender.io/browse/MEN-4516))
* Detect mismatches between `mender_boot_part` and `RootfsPart(A|B)` variables.
* Support for new grub-mender-grubenv tool names.
  ([MEN-3978](https://tracker.mender.io/browse/MEN-3978))
* Aggregated Dependabot Changelogs:
  * Bumps tests/unit/cmocka from `314602b` to `5a4b158`.
  * Bumps [libntech](https://github.com/cfengine/libntech) from `4b59844` to `f49189e`.
    - [Release notes](https://github.com/cfengine/libntech/releases)
    - [Commits](https://github.com/cfengine/libntech/compare/4b598446c54fd9e784a6dd86be99a317c3531dff...f49189eba92f7a0c9bb37141a7a84dfca7d6ba75)
    ---
    updated-dependencies:
    - dependency-name: libntech
      dependency-type: direct:production
    ...


## mender-binary-delta 1.2.1

_Released 04.16.2021_

### Changelogs

#### mender-binary-delta (1.2.1)

New changes in mender-binary-delta since 1.2.0:

* Remove harmless warning message about unhandled states.
* Fix failed rollback status when bootloader is the one to roll back.
* Detect mismatches between `mender_boot_part` and `RootfsPart(A|B)` variables.
* Fix integer overflow bug in the Artifact creation logic, where the
`rootfs_image_checksum` would get truncated through the use of the 32-bit
interface for JSON values in the JSON libary used.
([MEN-4516](https://tracker.mender.io/browse/MEN-4516))

## mender-binary-delta 1.2.0

_Released 01.11.2021_

### Changelogs

#### mender-binary-delta (1.2.0)

New changes in mender-binary-delta since 1.1.0:

* Improve error message when mender-artifact is not found.
([MEN-4044](https://tracker.mender.io/browse/MEN-4044))
* Mender-binary-delta and its Artifact generator now supports
the new "Provides" fields for individial application software names.
([MEN-3483](https://tracker.mender.io/browse/MEN-3483), [MEN-3484](https://tracker.mender.io/browse/MEN-3484))
* The format of the Artifact checksum field has been changed
in mender-artifact 3.5.0, from `rootfs_image_checksum` to
`rootfs-image.checksum`, to conform to the namespaced "Provides"
fields. Mender-binary-delta now supports this new field. This should
not have any practical effect, but will cause meta data of delta
Artifacts to look different.
([MEN-3483](https://tracker.mender.io/browse/MEN-3483), [MEN-3484](https://tracker.mender.io/browse/MEN-3484))
* Probe U-Boot env before use to support libubootenv fw tools
([MEN-4246](https://tracker.mender.io/browse/MEN-4246))

## mender-binary-delta 1.1.2

_Released 16.04.2021_

#### mender-binary-delta (1.1.2)

New changes in mender-binary-delta since 1.1.0:

* Probe U-Boot env before use to support libubootenv fw tools
([MEN-4246](https://tracker.mender.io/browse/MEN-4246))
* Remove harmless warning message about unhandled states.
* Fix failed rollback status when bootloader is the one to roll back.
* Detect mismatches between `mender_boot_part` and `RootfsPart(A|B)` variables.

## mender-binary-delta 1.1.1

_Released 01.11.2021_

### Changelogs

#### mender-binary-delta (1.1.1)

New changes in mender-binary-delta since 1.1.0:

* Probe U-Boot env before use to support libubootenv fw tools
([MEN-4246](https://tracker.mender.io/browse/MEN-4246))

## mender-binary-delta 1.1.0

_Released 07.15.2020_

#### mender-binary-delta (1.1.0)

New changes in mender-binary-delta since 1.0.1:

* Make the CLI artifact-name argument optional
([MEN-2642](https://tracker.mender.io/browse/MEN-2642))
* Now the binary delta tools supports depends and provides
([MEN-2642](https://tracker.mender.io/browse/MEN-2642))
* Add the ability to write transitional artifacts
([MEN-2948](https://tracker.mender.io/browse/MEN-2948))

## mender-binary-delta 1.0.1

_Released 12.06.2019_

### Changelogs

#### mender-binary-delta (1.0.1)

New changes in mender-binary-delta since 1.0.0:

* MEN-2928: Fix: Enable file-systems larger than approx 2-GiGs
([MEN-2928](https://tracker.mender.io/browse/MEN-2928))

## mender-binary-delta 1.0.0

_Released 10.16.2019_

