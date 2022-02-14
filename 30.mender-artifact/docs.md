---
title: mender-artifact
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-artifact 3.7.0

_Released 01.24.2022_

### Statistics

A total of 2094 lines added, 588 removed (delta 1506)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 6 (33.3%) |
| Lluis Campos | 5 (27.8%) |
| Kristian Amlie | 3 (16.7%) |
| Alan Alberghini | 3 (16.7%) |
| Michael Ho | 1 (5.6%) |

| Developers with the most changed lines | |
|---|---|
| Michael Ho | 1374 (63.5%) |
| Lluis Campos | 699 (32.3%) |
| Ole Petter Orhagen | 64 (3.0%) |
| Alan Alberghini | 14 (0.6%) |
| Kristian Amlie | 12 (0.6%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 14 (77.8%) |
| Tiscali S.p.a. | 3 (16.7%) |
| callmemikeh@gmail.com | 1 (5.6%) |

| Top lines changed by employer | |
|---|---|
| callmemikeh@gmail.com | 1374 (63.5%) |
| Northern.tech | 775 (35.8%) |
| Tiscali S.p.a. | 14 (0.6%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 3 (60.0%) |
| callmemikeh@gmail.com | 1 (20.0%) |
| Tiscali S.p.a. | 1 (20.0%) |

### Changelogs

#### mender-artifact (3.7.0)

New changes in mender-artifact since 3.6.1:

* Add missing error description when artifact header can't be written.
* Makefile: enhance autocomplete scripts install
* cli: Fix parsing of filenames containing ".mender"
  ([MEN-5076](https://tracker.mender.io/browse/MEN-5076))
* Fix the checksum errors encountered in rare cases where the entire byte
  stream is not consumed during verification, and thus giving wrong checksum errors.
  ([MEN-5094](https://tracker.mender.io/browse/MEN-5094))
* Restore SSH snapshot feature on Mac OS
  ([MEN-4362](https://tracker.mender.io/browse/MEN-4362), [MEN-5082](https://tracker.mender.io/browse/MEN-5082))
* Create a new signer using GCP's KMS

  This signs and verifies data using GCP's Key Management Service. This
  allows developers to use mender-artifact without ever accessing the
  private signing key.

  We add a new gcp-kms-key flag that lets users pass in the KMS key's
  resource ID.
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.14.0 to 3.14.1.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps alpine from 3.14.1 to 3.14.2.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps alpine from 3.14.2 to 3.14.3.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```
  * Bumps alpine from 3.14.3 to 3.15.0.

      ```
      updated-dependencies:
      - dependency-name: alpine
        dependency-type: direct:production
        update-type: version-update:semver-minor
      ```


## mender-artifact 3.6.1

_Released 09.28.2021_

### Statistics

A total of 38 lines added, 7 removed (delta 31)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 3 (60.0%) |
| Ole Petter Orhagen | 1 (20.0%) |
| Kristian Amlie | 1 (20.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 28 (73.7%) |
| Ole Petter Orhagen | 8 (21.1%) |
| Kristian Amlie | 2 (5.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 5 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 38 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### mender-artifact (3.6.1)

New changes in mender-artifact since 3.6.0:

* Add missing error description when artifact header can't be written.
* cli: Fix parsing of filenames containing ".mender"
  ([MEN-5076](https://tracker.mender.io/browse/MEN-5076))
* Fix the checksum errors encountered in rare cases where the entire byte
  stream is not consumed during verification, and thus giving wrong checksum errors.
  ([MEN-5094](https://tracker.mender.io/browse/MEN-5094))
* Restore SSH snapshot feature on Mac OS
  ([MEN-4362](https://tracker.mender.io/browse/MEN-4362), [MEN-5082](https://tracker.mender.io/browse/MEN-5082))


## mender-artifact 3.6.0

_Released 07.14.2021_

### Statistics

A total of 482 lines added, 451 removed (delta 31)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 7 (58.3%) |
| Lluis Campos | 3 (25.0%) |
| Alf-Rune Siqveland | 1 (8.3%) |
| Kristian Amlie | 1 (8.3%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 462 (86.7%) |
| Alf-Rune Siqveland | 43 (8.1%) |
| Lluis Campos | 27 (5.1%) |
| Kristian Amlie | 1 (0.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 12 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 533 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### mender-artifact (3.6.0)

New changes in mender-artifact since 3.5.1:

* Do not change the underlying Artifact unnecessarily
  Previously the commands modifying an Artifact would always repack an Artifact,
  no matter whether or not that modifications had actually been made to the
  Artifact. As an example of this, if you had a signed Artifact compressed with
  lzma, running `mender-artifact cat <artifact>:/<path-to-file>` would then cat
  the file, and repack the Artifact with the standard compression, which is
  `gzip`. Along the way the signature would also be lost.
  This fix adds the following changes to the tooling:
  * Modified images are no longer repacked, unless the command run has changed the
  underlying image. This means that cat and copying out of an image will keep your
  image intact. While copying into, installing, and removing files from the image
  will repack the image.
  * If an image is modified, and needs to be repacked, the existing compression
  will be respected when repacking. The only exception is the `--compression` flag
  for `mender-artifact modify` which can override the existing compression when repacking.
  * `mender-artifact {cat,install,cp,rm}` do not respect the `--compression` flag,
  but rather prints a warning, that the flag is ignored. If you want to change the
  compression of your Artifact, run `mender-artifact modify <Artifact>
  --compression <type>`
  ([MEN-4502](https://tracker.mender.io/browse/MEN-4502))
* Add a note about the proper usage of the 'compression' flag in the
  global help text.
* In case of a user trying to add a script with an invalid name, the
  error message now says just so: Invalid script name, instead of simply: Invalid script.
* Remove the 'scripter' prefix in the error messages when adding a
  State Script to an Artifact.
* [] Fix sending on closed signal channel
  ([MEN-4832](https://tracker.mender.io/browse/MEN-4832))
* Aggregated Dependabot Changelogs:
  * Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
    - [Release notes](https://github.com/stretchr/testify/releases)
    - [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
  * Bumps alpine from 3.12.3 to 3.13.1.
  * Bumps alpine from 3.13.1 to 3.13.2.
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...


## mender-artifact 3.5.3

_Release date 09.29.2021_

### Statistics

A total of 38 lines added, 7 removed (delta 31)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 3 (60.0%) |
| Ole Petter Orhagen | 1 (20.0%) |
| Kristian Amlie | 1 (20.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 28 (73.7%) |
| Ole Petter Orhagen | 8 (21.1%) |
| Kristian Amlie | 2 (5.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 5 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 38 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### mender-artifact (3.5.3)

New changes in mender-artifact since 3.5.2:

* Add missing error description when artifact header can't be written.
* cli: Fix parsing of filenames containing ".mender"
  ([MEN-5076](https://tracker.mender.io/browse/MEN-5076))
* Fix the checksum errors encountered in rare cases where the entire byte
  stream is not consumed during verification, and thus giving wrong checksum errors.
  ([MEN-5094](https://tracker.mender.io/browse/MEN-5094))
* Restore SSH snapshot feature on Mac OS
  ([MEN-4362](https://tracker.mender.io/browse/MEN-4362), [MEN-5082](https://tracker.mender.io/browse/MEN-5082))


## mender-artifact 3.5.2

_Released 07.14.2021_

### Statistics

A total of 45 lines added, 40 removed (delta 5)

| Developers with the most changesets | |
|---|---|
| Alf-Rune Siqveland | 1 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Alf-Rune Siqveland | 45 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 45 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |


### Changelogs

#### mender-artifact (3.5.2)

New changes in mender-artifact since 3.5.1:

* [] Fix sending on closed signal channel
  ([MEN-4832](https://tracker.mender.io/browse/MEN-4832))

## mender-artifact 3.5.1

_Released 04.16.2021_

### Changelogs

#### mender-artifact (3.5.1)

New changes in mender-artifact since 3.5.0:

* Do not change the underlying Artifact unnecessarily
Previously the commands modifying an Artifact would always repack an Artifact,
no matter whether or not that modifications had actually been made to the
Artifact. As an example of this, if you had a signed Artifact compressed with
lzma, running `mender-artifact cat <artifact>:/<path-to-file>` would then cat
the file, and repack the Artifact with the standard compression, which is
`gzip`. Along the way the signature would also be lost.
This fix adds the following changes to the tooling:
* Modified images are no longer repacked, unless the command run has changed the
underlying image. This means that cat and copying out of an image will keep your
image intact. While copying into, installing, and removing files from the image
will repack the image.
* If an image is modified, and needs to be repacked, the existing compression
will be respected when repacking. The only exception is the `--compression` flag
for `mender-artifact modify` which can override the existing compression when repacking.
* `mender-artifact {cat,install,cp,rm}` do not respect the `--compression` flag,
but rather prints a warning, that the flag is ignored. If you want to change the
compression of your Artifact, run `mender-artifact modify <Artifact>
--compression <type>`
([MEN-4502](https://tracker.mender.io/browse/MEN-4502))
* Add a note about the proper usage of the 'compression' flag in the
global help text.

## mender-artifact 3.5.1

_Released 16.04.2021_

### Changelogs

#### mender-artifact (3.5.1)

New changes in mender-artifact since 3.5.0:

* Do not change the underlying Artifact unnecessarily
Previously the commands modifying an Artifact would always repack an Artifact,
no matter whether or not that modifications had actually been made to the
Artifact. As an example of this, if you had a signed Artifact compressed with
lzma, running `mender-artifact cat <artifact>:/<path-to-file>` would then cat
the file, and repack the Artifact with the standard compression, which is
`gzip`. Along the way the signature would also be lost.
This fix adds the following changes to the tooling:
* Modified images are no longer repacked, unless the command run has changed the
underlying image. This means that cat and copying out of an image will keep your
image intact. While copying into, installing, and removing files from the image
will repack the image.
* If an image is modified, and needs to be repacked, the existing compression
will be respected when repacking. The only exception is the `--compression` flag
for `mender-artifact modify` which can override the existing compression when repacking.
* `mender-artifact {cat,install,cp,rm}` do not respect the `--compression` flag,
but rather prints a warning, that the flag is ignored. If you want to change the
compression of your Artifact, run `mender-artifact modify <Artifact>
--compression <type>`
([MEN-4502](https://tracker.mender.io/browse/MEN-4502))
* Add a note about the proper usage of the 'compression' flag in the
global help text.

## mender-artifact 3.5.0

_Released 01.20.2021_

### Changelogs

#### mender-artifact (3.5.0)

New changes in mender-artifact since 3.4.0:

* Fix segfault on mender-artifact dump for v2 Artifacts
([MEN-3967](https://tracker.mender.io/browse/MEN-3967))
* Change rootfs_image_checksum over to use namespaced provides
([MEN-3482](https://tracker.mender.io/browse/MEN-3482))
* Implement `clears_artifact_provides` field in Artifact
format. This field can be used to control how Artifacts modify the
record of existing software on the device. For example, a rootfs-image
update can erase the record of other software on the device, whereas a
single-file update can preserve the records. See the Mender
documentation for more information on how to use this, or refer to
`Documentation/artifact-format-v3.md` in the mender-artifact
repository for the reference.
([MEN-3479](https://tracker.mender.io/browse/MEN-3479))
* Add `--print0-cmdline` argument to `dump` command.
Works exactly like `--print-cmdline` but prints null bytes between
arguments instead of spaces. This mirrors the `-print0` argument of
find and complements the `-0` argument of xargs.
([MEN-3483](https://tracker.mender.io/browse/MEN-3483))
* use sudo for snapshots if required.
([MEN-3987](https://tracker.mender.io/browse/MEN-3987))
* Add progress indication to the mender-artifact read and write
commands. So now progress is reported on the terminal TTY when reading and
writing Artifacts.
* run fsck on fs image created via SSH snapshot
([MEN-4362](https://tracker.mender.io/browse/MEN-4362))
* Aggregated Dependabot Changelogs:
* Bumps [github.com/pkg/errors](https://github.com/pkg/errors) from 0.8.1 to 0.9.1.
- [Release notes](https://github.com/pkg/errors/releases)
- [Commits](https://github.com/pkg/errors/compare/v0.8.1...v0.9.1)
* Bumps alpine from 3.9 to 3.12.0.
* Bump alpine from 3.9 to 3.12.0
* Bump github.com/pkg/errors from 0.8.1 to 0.9.1
* Bumps [github.com/klauspost/pgzip](https://github.com/klauspost/pgzip) from 1.2.3 to 1.2.4.
- [Release notes](https://github.com/klauspost/pgzip/releases)
- [Commits](https://github.com/klauspost/pgzip/compare/v1.2.3...v1.2.4)
* Bump github.com/klauspost/pgzip from 1.2.3 to 1.2.4
* Bumps [github.com/klauspost/pgzip](https://github.com/klauspost/pgzip) from 1.2.4 to 1.2.5.
- [Release notes](https://github.com/klauspost/pgzip/releases)
- [Commits](https://github.com/klauspost/pgzip/compare/v1.2.4...v1.2.5)
* Bump github.com/klauspost/pgzip from 1.2.4 to 1.2.5
* Bumps alpine from 3.12.0 to 3.12.1.
* Bump alpine from 3.12.0 to 3.12.1
* Bumps alpine from 3.12.1 to 3.12.2.
* Bump alpine from 3.12.1 to 3.12.2
* Bumps alpine from 3.12.2 to 3.12.3.
* Bump alpine from 3.12.2 to 3.12.3
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)

## mender-artifact 3.4.1

_Released 01.21.2021_

### Changelogs

#### mender-artifact (3.4.1)

New changes in mender-artifact since 3.4.0:

* Fix segfault on mender-artifact dump for v2 Artifacts
([MEN-3967](https://tracker.mender.io/browse/MEN-3967))
* use sudo for snapshots if required.
([MEN-3987](https://tracker.mender.io/browse/MEN-3987))

## mender-artifact 3.4.2

_Released 16.04.2021_

### Changelogs

#### mender-artifact (3.4.2)

New changes in mender-artifact since 3.4.1:

* run fsck on fs image created via SSH snapshot
([MEN-4362](https://tracker.mender.io/browse/MEN-4362))

## mender-artifact 3.4.1

_Released 01.21.2021_

### Changelogs

#### mender-artifact (3.4.1)

New changes in mender-artifact since 3.4.0:

* Fix segfault on mender-artifact dump for v2 Artifacts
([MEN-3967](https://tracker.mender.io/browse/MEN-3967))
* use sudo for snapshots if required.
([MEN-3987](https://tracker.mender.io/browse/MEN-3987))

## mender-artifact 3.4.0

_Released 07.15.2020_

### Changelogs

#### mender-artifact (3.4.0)

New changes in mender-artifact since 3.3.0:

* Accept suffix '.img' for mender-artifact modifiable images
* Fix: Update `rootfs_image_checksum` provide when repacking Artifact.
* Improved error message when an update-module is missing
([MEN-3007](https://tracker.mender.io/browse/MEN-3007))
* Bugfix: ignored signals no longer cause a signal-loop
([MEN-3276](https://tracker.mender.io/browse/MEN-3276))
* Add ability for artifact install to create directories
* Enabled autocompletion of mender-artifact sub-commands in bash & zsh
Now, following the instructions in the Readme file, auto-completion of
mender-artifact commands can be enabled by the user, such that writing:
mender-artifact <TAB>
results in:
```
➜ mender-artifact git:(bashexpansion) ✗ mender-artifact
cat          -- cat [artifact|sdimg|uefiimg]:<filepath>
cp           -- cp <src> <dst>
dump         -- Dump contents from Artifacts
help      h  -- Shows a list of commands or help for one command
install      -- install -m <permissions> <hostfile> [artifact|sdimg|uefiimg]
modify       -- Modifies image or artifact file.
read         -- Reads artifact file.
rm           -- rm [artifact|sdimg|uefiimg]:<filepath>
sign         -- Signs existing artifact file.
validate     -- Validates artifact file.
write        -- Writes artifact file.
```
and
```
➜ mender-artifact git:(bashexpansion) ✗ mender-artifact write
help          h  -- Shows a list of commands or help for one command
module-image     -- Writes Mender artifact for an update module
rootfs-image     -- Writes Mender artifact containing rootfs image
```
for sub-commands.
* The Artifact parser now fails when no 'device-type' is found in a payload.
* Disallow writes of UpdateModule Artifacts with no 'device-type' flag
* Return an error code if CLI read <artifact> fails
* Disallow parsing ArtifactV2 with empty device type field
* Display all CLI commands and flags sorted alplhabetically
* Missing a required CLI flag will now return an error
* Indexed the CLI commands by category
This should make it easier to distinguish the large number of CLI commands
depending on their intended usage.
The two categories added are:
* Artifact creation and validation
* Artifact modification
And should help to roughly set the commands apart depending on if they are
intended to work with a standard Artifact, either creating it or validating it.
The second category is intended for modification of already existing artifacts,
such as adding or removing files, signing or modifying the Artifact name.
* Add(cli): Print the urfave/cli error on error

## mender-artifact 3.3.1

_Released 07.15.2020_

### Changelogs

#### mender-artifact (3.3.1)

New changes in mender-artifact since 3.3.0:

* Bugfix: ignored signals no longer cause a signal-loop
([MEN-3276](https://tracker.mender.io/browse/MEN-3276))


## mender-artifact 3.3.0

_Released 03.05.2020_

### Changelogs

#### mender-artifact (3.3.0)

New changes in mender-artifact since 3.2.1:

* Adds API for returning all Artifact provides and depends
([MEN-2549](https://tracker.mender.io/browse/MEN-2549))
* Enables Artifact Provides and Depends for write rootfs-img
Previously, the `write rootfs-image` command did not have the ability
to set Provides and Depends in the artifact. This was only enabled for
the `write module-image` command. Now the `rootfs-image` update can
also set Provides and Depends. However, please note that meta-data
and augmented Provides and Depends still are unsupported.
([MEN-2812](https://tracker.mender.io/browse/MEN-2812))
* Fix bug that destroys Artifact if any copy/modify command
is used on a non-rootfs-image Artifact.
([MEN-2592](https://tracker.mender.io/browse/MEN-2592))
* The `modify` subcommand has gained the `-k`/`--key`
argument to automatically sign the Artifact after modification.
([MEN-2592](https://tracker.mender.io/browse/MEN-2592))
* Remove superfluous "Files" header from `read` output.
* Fix incorrect help string for signed artifacts.
If no key was provided, it said that the signature verification
failed, but it should instruct the user to provide a key.
* Fix state scripts being lost when modifying artifact.
* One can now use `mender-artifact modify` to change artifact
Depends, Provides and Meta-data attributes. See the help screen for
more information.
([MEN-1669](https://tracker.mender.io/browse/MEN-1669))
* `mender-artifact modify --name` argument renamed to
`--artifact-name` to match the rest of the tool's flags. The old flag
is still kept for compatibility.
([MEN-1669](https://tracker.mender.io/browse/MEN-1669))
* Make artifact install respect the given file permissions
([MEN-2880](https://tracker.mender.io/browse/MEN-2880))
* Added the writing of the `rootfs_image_checksum` provide parameter as
a default to `rootfs-image` Artifacts. This means that now, the
`rootfs_image_checksum` will be written as a provide parameter to the Mender
client's database upon an update with the given Artifact. Please note that for
older clients (i.e. <= 2.1.x) this will not work, and the functionality should
be disabled by the user through the `--no-checksum-provide` flag when writing a
rootfs-image Artifact.
([MEN-2956](https://tracker.mender.io/browse/MEN-2956))
* Create artifact from device snapshot

## mender-artifact 3.2.1

_Released 12.05.2019_

### Changelogs

#### mender-artifact (3.2.1)

New changes in mender-artifact since 3.2.0:

* Make artifact install respect the given file permissions
([MEN-2880](https://tracker.mender.io/browse/MEN-2880))

## mender-artifact 3.2.0

_Released 10.23.2019_

### Changelogs

#### mender-artifact (3.2.0)

New changes in mender-artifact since 3.1.0:

* 'mender-artifact cp' now requires '-' in order to read stdin
([MEN-2745](https://tracker.mender.io/browse/MEN-2745))
* Fix error where files larger than the buffer used by
io.Copy() was not buffered when mender-artifact cp read from stdin.
This means that now, ``` mender-artfact cp - mender.artifact:/in/img/path```
will successfully copy larger files.
* fix erroneously report of "-dirty" in the version
string. ([MEN-2800](https://tracker.mender.io/browse/MEN-2800))
* Fix build-contained Makefile: image was missing make install
* Update the type-info documentation in the version 3 artifact format
This commit updates the description of the values allowed in the type-info
headers in the version 3 of the artifact format. Formerly only the key
`rootfs-image-checksum` was allowed, while now, any key is allowed, with
the only allowed value types being string, or array of strings.
* Allow `--compression` to be specified after command.
This allows it to be appended to the command, which makes it usable
with `--` style arguments to Update Module Artifact generators.
* Enable typeinfo artifact-depends/provides string and []string values
Previously the artifact-depends key in the type-info header was restricted
to contain a single key `rootfs-image-checksum`. This restriction has now
been lifted, and the key can now contain arbitrary string, and []string values.
* Fix: mender-artifact modify did not clean up the
temp-files created
([MEN-2758](https://tracker.mender.io/browse/MEN-2758))
* Mender-Artifact format version 1 is hereby no longer supported,
and neither reading or writing the version 1 of the format is no longer
supported. Please move to using a newer version.
([MEN-2156](https://tracker.mender.io/browse/MEN-2156))
* mender-artifact will now fail to validate a signed Artifact
if no validation key is specified. No behaviour change for unsigned
Artifacts. ([MEN-2802](https://tracker.mender.io/browse/MEN-2802))

## mender-artifact 3.1.1

_Released 12.05.2019_

### Changelogs

#### mender-artifact (3.1.1)

New changes in mender-artifact since 3.1.0:

* fix erroneously report of "-dirty" in the version
string. ([MEN-2800](https://tracker.mender.io/browse/MEN-2800))
* Fix: mender-artifact modify did not clean up the temp-files created
([MEN-2758](https://tracker.mender.io/browse/MEN-2758))
* Fix build-contained Makefile: image was missing make install
* Make artifact install respect the given file permissions
([MEN-2880](https://tracker.mender.io/browse/MEN-2880))


## mender-artifact 3.1.0

_Released 09.16.2019_

### Changelogs

#### mender-artifact (3.1.0)

New changes in mender-artifact since 3.0.1:

* Fix non-rootfs Artifacts being destroyed when signing them.
([MEN-2573](https://tracker.mender.io/browse/MEN-2573))
* The mender-artifact tool now checks whether the required
external binaries can be found on the system, and if not, returns an appropriate
error message.
([MEN-2180](https://tracker.mender.io/browse/MEN-2180))
* Fix name modify command for rootfs-image Artifacts
([MEN-2488](https://tracker.mender.io/browse/MEN-2488))
* Remove documentation for artifact format v1, which is now unsupported.
* `mender-convert` modify for Update Module Artifacts will only
work for options that change the headers or meta-data of the Artifact;
curently only the Artifact name.
([MEN-2487](https://tracker.mender.io/browse/MEN-2487))
* Enable signing of artifacts larger than 1MiB
([MEN-2631](https://tracker.mender.io/browse/MEN-2631))
* Fix "unexpected EOF" errors when the source of the artifact
is a slow network stream.
* Fix spurious upload errors due to wrong EOF handling.
* checking if fsck is on path and returing error if not.
* Add `dump` command to mender-artifact.
It takes an artifact as input, some optional dumping directories, and
writes the various raw files from the artifact into those directories.
The parameter `--print-cmdline` can be used to generate a command line
which can be used to recreate the same artifact from the dumped files.
([MEN-2580](https://tracker.mender.io/browse/MEN-2580))
* Added a build step for macOS to the Travis build.
* `mender-artifact modify` does not support anymore signing the
Artifact after the modification. Use `mender-convert sign` after the
modification to sign the Artifact.
([MEN-2486](https://tracker.mender.io/browse/MEN-2486))

## mender-artifact 3.0.1

_Released 06.24.2019_

### Changelogs

#### mender-artifact (3.0.1)

New changes in mender-artifact since 3.0.0:

* Fix non-rootfs Artifacts being destroyed when signing them.
([MEN-2573](https://tracker.mender.io/browse/MEN-2573))

## mender-artifact 3.0.0

_Released 05.07.2019_

### Changelogs

#### mender-artifact (3.0.0)

New changes in mender-artifact since 3.0.0b1:

* checking if fsck is on path and returing error if not.
* Fix name modify command for rootfs-image Artifacts
([MEN-2488](https://tracker.mender.io/browse/MEN-2488))
* `mender-convert` modify for Update Module Artifacts will only
work for options that change the headers or meta-data of the Artifact;
curently only the Artifact name.
([MEN-2487](https://tracker.mender.io/browse/MEN-2487))
* `mender-artifact modify` does not support anymore signing the
Artifact after the modification. Use `mender-convert sign` after the
modification to sign the Artifact.
([MEN-2486](https://tracker.mender.io/browse/MEN-2486))

New changes in mender-artifact since 2.4.0:

* add support for uncompressed updates
([MEN-2224](https://tracker.mender.io/browse/MEN-2224))
* mender-artifact tool now supports removing a file in either an sdimg,
or in a Mender Artifact, with the rm command.
([MEN-2331](https://tracker.mender.io/browse/MEN-2331))
* FIX: mender-artifact cat now cleans up resources on write-errors.
* Implement reading and writing support for update modules.
([MEN-2004](https://tracker.mender.io/browse/MEN-2004))
* Change rootfs-image `-u` argument to `-f`.
Similarly, change `--update` to `--file`.
([MEN-2286](https://tracker.mender.io/browse/MEN-2286))
* Due to some faulty logic in modify.go:modifyArtifact, the sdimg's
provided were modified, but not repacked. This fix updates the logic, and added
a test specifically for sdimg, as they we're non-existent.
([MEN-2294](https://tracker.mender.io/browse/MEN-2294))
* fixes issue when binary dependencies are not in PATH
([MEN-2180](https://tracker.mender.io/browse/MEN-2180))
* Validate the data update files names in payload filename
([MEN-2319](https://tracker.mender.io/browse/MEN-2319))
* Mender-artifactV3: Bump the artifact-version protocol to version 3.
* Report a human readable error in case the artifact payload is not ext4.
* Add support for compressing artifacts using LZMA.

## mender-artifact 2.4.1

_Released 05.07.2019_

### Changelogs

#### mender-artifact (2.4.1)

New changes in mender-artifact since 2.4.0:

* Report a human readable error in case the artifact payload is not ext4.


## mender-artifact 2.4.0

_Released 12.13.2018_

### Changelogs

#### mender-artifact (2.4.0)

New changes in mender-artifact since 2.3.0:

* FIX: mender-artifact cp no longer renames the artifact.
* FIX: remove leftover tmp files from mender-artifact cp.
* FIX: mender-artifact no longer changes the names of the updates in an artifact
* Updated the JSON format of header-info version 3.
* A command of the form
"mender-artifact validate unsigned.mender -k public.key"
was incorrectly succeeding for an unsigned artifact when a public key
was supplied. Supplying a public key indicates that the caller requires
the artifact to contain a signature that matches that key.
Now this command fails (exits with a nonzero value) as expected.
([MEN-2155](https://tracker.mender.io/browse/MEN-2155))
* FIX: Renaming a file across devices now works.
([MEN-2166](https://tracker.mender.io/browse/MEN-2166))
* FIX: mender-artifact cat,cp,modify etc no longer removes the update.
Previously an update present in a directory, with the same name as the
update present in an update would be removed as a result of what the
functions thought was tmp-files.
([MEN-2171](https://tracker.mender.io/browse/MEN-2171))
* Fixed a bug that caused a command like
"mender-artifact cat signed.mender:/etc/mender/artifact_info"
to fail with the error:
"failed to open the partition reader: err: error validating signature"
There was a similar problem with the "cp" command, and also
the "modify" command when no "-k" was present to replace the
existing signature.

## mender-artifact 2.3.1

_Released 12.13.2018_

### Changelogs

#### mender-artifact (2.3.1)

New changes in mender-artifact since 2.3.0:

* FIX: Renaming a file across devices now works.
([MEN-2166](https://tracker.mender.io/browse/MEN-2166))
* FIX: mender-artifact cat,cp,modify etc no longer removes the update.
Previously an update present in a directory, with the same name as the
update present in an update would be removed as a result of what the
functions thought was tmp-files.
([MEN-2171](https://tracker.mender.io/browse/MEN-2171))



## mender-artifact 2.3.0

_Released 09.18.2018_

### Changelogs

#### mender-artifact (2.3.0)

New changes in mender-artifact since 2.3.0b1:

* FIX: mender-artifact cp no longer renames the artifact.
* FIX: remove leftover tmp files from mender-artifact cp.
* FIX: mender-artifact no longer changes the names of the updates in an artifact

New changes in mender-artifact since 2.2.0:

* Add boot partition as a modify candidate for artifact cp
* Add mtools as a dependency before installing from source, and in travis
* Testify/require files added to the vendor directory
* Small cleanup of license text. No legal difference, just
makes it easier for the tooling.
* Install function added
* Added uefiimg as an option to the cp and cat commands
* modify any file using the mender-artifact tool
([MEN-1741](https://tracker.mender.io/browse/MEN-1741))
* add testify/require to vendor
* modify any file using the mender-artifact tool
([MEN-1741](https://tracker.mender.io/browse/MEN-1741))
* Mender-artifact can now copy to and read from the data partition
([MEN-1953](https://tracker.mender.io/browse/MEN-1953))
* run fsck before modifying image.
([MEN-1798](https://tracker.mender.io/browse/MEN-1798))

## mender-artifact 2.2.0b1

_Released 02.09.2018_

### Changelogs

#### mender-artifact (2.2.0b1)
* Fix ECDSA failures while signing and verifying artifact.
([MEN-1470](https://tracker.mender.io/browse/MEN-1470))
* Fix broken header checksum verification.
([MEN-1412](https://tracker.mender.io/browse/MEN-1412))
* Add modify existing images and artifacts functionality.
([MEN-1213](https://tracker.mender.io/browse/MEN-1213))
* Artifact version 3 format documentation
([MEN-1667](https://tracker.mender.io/browse/MEN-1667))
* Mender-Artifact now returns an error code to the os on cli errors
([MEN-1328](https://tracker.mender.io/browse/MEN-1328))
* mender-artifact now fails with whitespace in the artifact-name
([MEN-1355](https://tracker.mender.io/browse/MEN-1355))

## mender-artifact 2.1.2

_Released 02.09.2018_

### Changelogs

#### mender-artifact (2.1.2)
* Fix ECDSA failures while signing and verifying artifact.
([MEN-1470](https://tracker.mender.io/browse/MEN-1470))


## mender-artifact 2.1.1

_Released 10.02.2017_

### Changelogs

#### mender-artifact (2.1.1)
* Fix broken header checksum verification.
([MEN-1412](https://tracker.mender.io/browse/MEN-1412))


## mender-artifact 2.1.0

_Released 09.05.2017_

### Changelogs

#### mender-artifact (2.1.0)
* Sign existing artifacts using mender-artifact CLI
([MEN-1220](https://tracker.mender.io/browse/MEN-1220))
* Improve error message when private signing key can't be loaded.
* Fix misleading version being displayed for non-tagged builds.
([MEN-1178](https://tracker.mender.io/browse/MEN-1178))
* Mender-Artifact now returns an error code to the os on cli errors
([MEN-1328](https://tracker.mender.io/browse/MEN-1328))
* mender-artifact now fails with whitespace in the artifact-name
([MEN-1355](https://tracker.mender.io/browse/MEN-1355))

## mender-artifact 2.0.2

_(Never released publicly)_

### Changelogs

#### mender-artifact (2.0.2)
* Fix broken header checksum verification.
([MEN-1412](https://tracker.mender.io/browse/MEN-1412))


