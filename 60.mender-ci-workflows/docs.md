---
title: mender-ci-workflows
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## mender-ci-workflows 2.0.0

_Released 11.16.2026_

### Changelogs

#### mender-ci-workflows (2.0.0)

New changes in mender-ci-workflows since 1.0.0:

##### Bug Fixes

* mender-artifact requires the libssl3 library, so this is now included in the image
* Added ca-certficates package to the Dockerfile
  ([MEN-7830](https://northerntech.atlassian.net/browse/MEN-7830))

##### Features

* Update mender-cli to 2.0.0, mender-artifact to 4.4.2 and the Mender Client
  Artifact generators to 5.2.0
* **BREAKING**: `docker-artifact-gen` is no longer included in the mender-ci-tools image
  ([MEN-7672](https://northerntech.atlassian.net/browse/MEN-7672))
* The mender-ci-tools image is now built for both amd64 and arm64
* Update the base image to Debian 13


## mender-ci-workflows 1.0.0

_Released 12.20.2022_

### Statistics

A total of 1807 lines added, 88 removed (delta 1719)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 10 (52.6%) |
| Alex Miliukov | 9 (47.4%) |

| Developers with the most changed lines | |
|---|---|
| Alex Miliukov | 1584 (87.5%) |
| Lluis Campos | 227 (12.5%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 19 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1811 (100.0%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-ci-workflows (1.0.0)

* First release of mender-ci-workflows
