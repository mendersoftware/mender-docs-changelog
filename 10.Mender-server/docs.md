---
title: Mender server
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## Mender 3.0.0

_Released 07.14.2021_

### Statistics

A total of 33744 lines added, 22372 removed (delta 11372)

| Developers with the most changesets | |
|---|---|
| Manuel Zedel | 162 (32.7%) |
| Fabio Tranchitella | 88 (17.7%) |
| Marcin Chalczynski | 66 (13.3%) |
| Krzysztof Jaskiewicz | 40 (8.1%) |
| Lluis Campos | 34 (6.9%) |
| Alex Miliukov | 27 (5.4%) |
| Kristian Amlie | 25 (5.0%) |
| Alf-Rune Siqveland | 22 (4.4%) |
| Ole Petter Orhagen | 14 (2.8%) |
| Peter Grzybowski | 12 (2.4%) |

| Developers with the most changed lines | |
|---|---|
| Manuel Zedel | 18950 (43.9%) |
| Fabio Tranchitella | 4826 (11.2%) |
| Ole Petter Orhagen | 4664 (10.8%) |
| Krzysztof Jaskiewicz | 4326 (10.0%) |
| Marcin Chalczynski | 3583 (8.3%) |
| Alex Miliukov | 2847 (6.6%) |
| Alf-Rune Siqveland | 1902 (4.4%) |
| Lluis Campos | 983 (2.3%) |
| Peter Grzybowski | 618 (1.4%) |
| Kristian Amlie | 429 (1.0%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 4102 (18.3%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Alf-Rune Siqveland | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 390 (78.6%) |
| RnDity | 106 (21.4%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 35298 (81.7%) |
| RnDity | 7909 (18.3%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 13) | |
|---|---|
| Northern.tech | 11 (84.6%) |
| RnDity | 2 (15.4%) |

### Changelogs

#### auditlogs (1.2.0)

New changes in auditlogs since 1.1.0:

* Redact sensitive information from logs
  ([MEN-4332](https://tracker.mender.io/browse/MEN-4332), [MEN-4491](https://tracker.mender.io/browse/MEN-4491))
* Allow filtering logs by object_type='device'
  ([MEN-4332](https://tracker.mender.io/browse/MEN-4332), [MEN-4491](https://tracker.mender.io/browse/MEN-4491))
* New audit log actions: 'open_portforward',
  'close_portforward', 'download_file', 'upload_file',
  'set_configuration', 'deploy_configuration'.
  ([MEN-4332](https://tracker.mender.io/browse/MEN-4332), [MEN-4491](https://tracker.mender.io/browse/MEN-4491))
* Audit log uploading and deleting atifacts
  ([MEN-4047](https://tracker.mender.io/browse/MEN-4047))
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.0 to 3.13.3.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.6.3 to 1.7.1.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.6.3...v1.7.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.3 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.7.1 to 1.7.2.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.7.1...v1.7.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...

#### deployments (3.0.0)

New changes in deployments since 2.3.0:

* device status update handles 'pause' states
  ([MEN-4570](https://tracker.mender.io/browse/MEN-4570))
* Sort parameter for get deployments endpoint
  ([MEN-4665](https://tracker.mender.io/browse/MEN-4665))
* add support for AWS S3 Transfer Acceleration
  ([MEN-3966](https://tracker.mender.io/browse/MEN-3966))
* Deployments devices endpoint deprecation
  ([MEN-3993](https://tracker.mender.io/browse/MEN-3993))
* new deployment devices list endpoint
  ([MEN-3993](https://tracker.mender.io/browse/MEN-3993))
* store information about device groups with the deployment
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.1 to 3.13.3.
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.30 to 1.38.7.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.30...v1.38.7)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.38.7 to 1.38.12.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.38.7...v1.38.12)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.38.12 to 1.38.17.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.38.12...v1.38.17)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...

#### deployments-enterprise (3.0.0)

New changes in deployments-enterprise since 2.3.0:

* docs: Fix naming conflict in v1 and v2 NewDeployment definitions.
* docs: Document missing parameters for NewDeploymentForGroup schema.
* device status update handles 'pause' states
  ([MEN-4570](https://tracker.mender.io/browse/MEN-4570))
* introduce audit log for deployment aborting
* Added new PATCH endpoint for updating update_control_map
* [] Support update_control_map in /deployments/next devices API
  ([MEN-4555](https://tracker.mender.io/browse/MEN-4555))
* extend configuration deployment with update control map
* Sort parameter for get deployments endpoint
  ([MEN-4665](https://tracker.mender.io/browse/MEN-4665))
* add support for AWS S3 Transfer Acceleration
  ([MEN-3966](https://tracker.mender.io/browse/MEN-3966))
* Sort parameter for get deployments endpoint
  ([MEN-4665](https://tracker.mender.io/browse/MEN-4665))
* Deployments devices endpoint deprecation
  ([MEN-3993](https://tracker.mender.io/browse/MEN-3993))
* new deployment devices list endpoint
  ([MEN-3993](https://tracker.mender.io/browse/MEN-3993))
* new end-point: deployments/next v2
  ([MEN-4784](https://tracker.mender.io/browse/MEN-4784))
* store information about device groups with the deployment
* extend RBAC support
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.1 to 3.13.3.
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.30 to 1.38.7.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.30...v1.38.7)
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.30 to 1.38.7.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.30...v1.38.7)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.38.7 to 1.38.12.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.38.7...v1.38.12)
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.38.7 to 1.38.12.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.38.7...v1.38.12)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.38.12 to 1.38.17.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.38.12...v1.38.17)
  * Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.38.12 to 1.38.17.
    - [Release notes](https://github.com/aws/aws-sdk-go/releases)
    - [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/aws/aws-sdk-go/compare/v1.38.12...v1.38.17)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### deviceauth (3.0.0)

New changes in deviceauth since 2.6.0:

* inventory client: update the path of the status endpoint
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.1 to 3.13.3.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.7.1 to 8.8.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.7.1...v8.8.0)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps golang from 1.15.8-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.8.0 to 8.8.2.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.8.0...v8.8.2)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.8.2 to 8.9.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.8.2...v8.9.0)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.9.0 to 8.10.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.9.0...v8.10.0)
    ---
    updated-dependencies:
    - dependency-name: github.com/go-redis/redis/v8
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### deviceconfig (1.1.0)

New changes in deviceconfig since 1.0.0:

* docs: Fix name conflict in Configuration schema.
* extend endpoint for deploying configuration with support for optional update control map parameter
* remove RBAC support; RBAC for this service is handled by the useradm-enterprise serivce
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.6.3 to 1.7.1.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.6.3...v1.7.1)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.7.1 to 1.7.2.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.7.1...v1.7.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### deviceconnect (1.2.0)

New changes in deviceconnect since 1.1.0:

* [] Limit size of messages transferred over websockets
  ([MEN-4803](https://tracker.mender.io/browse/MEN-4803))
* Delay HTTP 200 response to the first file chunk received to
  support errors due to file transfer limits set on the device.
* Aggregated Dependabot Changelogs:
  * Bumps golang from 1.15-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [github.com/vmihailenco/msgpack/v5](https://github.com/vmihailenco/msgpack) from 5.1.0 to 5.3.1.
    - [Release notes](https://github.com/vmihailenco/msgpack/releases)
    - [Commits](https://github.com/vmihailenco/msgpack/compare/v5.1.0...v5.3.1)
  * Bumps alpine from 3.13.0 to 3.13.4.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.6.3 to 1.7.1.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.6.3...v1.7.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [github.com/nats-io/nats.go](https://github.com/nats-io/nats.go) from 1.10.0 to 1.11.0.
    - [Release notes](https://github.com/nats-io/nats.go/releases)
    - [Commits](https://github.com/nats-io/nats.go/compare/v1.10.0...v1.11.0)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.7.1 to 1.7.2.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.7.1...v1.7.2)
  * Bumps [github.com/vmihailenco/msgpack/v5](https://github.com/vmihailenco/msgpack) from 5.3.1 to 5.3.4.
    - [Release notes](https://github.com/vmihailenco/msgpack/releases)
    - [Commits](https://github.com/vmihailenco/msgpack/compare/v5.3.1...v5.3.4)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### gui (3.0.0)

New changes in gui since 2.7.0:

* refactored upgrade page + added support for plan & addon changes
* ensured ungrouped group won't suggest removing device from group
  ([MEN-4609](https://tracker.mender.io/browse/MEN-4609))
* fixed an issue that could prevent cleaning up an expanded device + leak memory
* limited processing of retrieved device attributes to 100
* added port forwarding tooltip to ease access to the feature
  ([MEN-4477](https://tracker.mender.io/browse/MEN-4477))
* made initial past deployment time frame selection depend on most recent deployments
* fixed an issue that prevented automatic redirect to pending/ inprogress deployments after deployment creation
* fixed an issue that caused releases to disappear on deployment creation
* fixed an issue that prevented single device deployment recreation
* fixed an issue that prevented the deployment device list from being updated
* fixed an issue that could crash the deployment page when closing
* fixed a potential memory leak in the deployments list
* fixed an issue that prevented RBAC group based role modifications
  ([MEN-4713](https://tracker.mender.io/browse/MEN-4713))
* made deployments fitlerable by deployment type
  ([MEN-4667](https://tracker.mender.io/browse/MEN-4667))
* Adjustments to height and signup/login padding for display on small screens
* fixed an issue that caused deployment type selection to reset by itself
* fixed an issue that could prevent deployment creation after switching to a lower plan
  ([MEN-4765](https://tracker.mender.io/browse/MEN-4765))
* fixed an issue that might prevent importing a default configuration
  ([MEN-4750](https://tracker.mender.io/browse/MEN-4750))
* added support for synchronized deployments and deployment pause states
  ([MEN-4711](https://tracker.mender.io/browse/MEN-4711))
* fixed an issue that could prevent enterprise users from setting up a phased deployment
* fixed an issue that prevented a previously set default retry value from being used
* fixed an issue that prevented running deployments from being updated
  ([MEN-4802](https://tracker.mender.io/browse/MEN-4802))
* enabled device filtering with multiple values for the same attribute
  ([MEN-4674](https://tracker.mender.io/browse/MEN-4674))
* added device list shortcut filter to ease device list filtering on id-attributes
* migrated tab based device list layout to single filtered list layout
  ([MEN-4662](https://tracker.mender.io/browse/MEN-4662))
* fixed an issue that prevented automatic update of detailed device info
* restored individual scrolling in device list etc.
  ([MEN-4828](https://tracker.mender.io/browse/MEN-4828))
* Aggregated Dependabot Changelogs:
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.10.0 to 3.10.1.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.10.1/packages/core-js)
  * Bumps [@babel/plugin-transform-runtime](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-transform-runtime) from 7.13.10 to 7.13.15.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.13.15/packages/babel-plugin-transform-runtime)
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.2.9 to 8.2.10.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.2.9...8.2.10)
  * Bumps node from 15.13.0-alpine to 15.14.0-alpine.
  * Bumps [cypress-file-upload](https://github.com/abramenal/cypress-file-upload) from 5.0.3 to 5.0.5.
    - [Release notes](https://github.com/abramenal/cypress-file-upload/releases)
    - [Commits](https://github.com/abramenal/cypress-file-upload/compare/v5.0.3...v5.0.5)
  * Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.4.2 to 1.4.3.
    - [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
    - [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.4.2...v1.4.3)
  * Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 13.0.16 to 13.1.2.
    - [Release notes](https://github.com/testing-library/user-event/releases)
    - [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/user-event/compare/v13.0.16...v13.1.2)
  * Bumps cypress/included from 6.8.0 to 7.0.1.
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.13.12 to 7.13.15.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.13.15/packages/babel-preset-env)
  * Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.4.0 to 1.4.1.
    - [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
    - [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.4.0...v1.4.1)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.30.0 to 5.32.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.30.0...v5.32.0)
  * Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 8.0.0 to 8.1.0.
    - [Release notes](https://github.com/webpack-contrib/less-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/less-loader/compare/v8.0.0...v8.1.0)
  * Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.23.1 to 7.23.2.
    - [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
    - [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.23.1...v7.23.2)
  * Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.2.0 to 5.2.1.
    - [Release notes](https://github.com/webpack-contrib/css-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.2.0...v5.2.1)
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.4.13 to 35.5.1.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.4.13...v35.5.1)
  * Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.11.0 to 2.11.1.
    - [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
    - [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.11.0...v2.11.1)
  * Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.5.6 to 4.6.0.
    - [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
    - [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.5.6...4.6.0)
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.13.14 to 7.13.15.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.13.15/packages/babel-core)
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.23.0 to 7.24.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.23.0...v7.24.0)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.32.0 to 5.33.2.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.32.0...v5.33.2)
  * Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.11.1 to 2.12.0.
    - [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
    - [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.11.1...v2.12.0)
  * Bumps [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) from 3.3.1 to 3.4.0.
    - [Release notes](https://github.com/prettier/eslint-plugin-prettier/releases)
    - [Changelog](https://github.com/prettier/eslint-plugin-prettier/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/prettier/eslint-plugin-prettier/commits)
  * Bumps nginx from 1.19.9-alpine to 1.19.10-alpine.
  * Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.4.1 to 1.5.0.
    - [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
    - [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.4.1...v1.5.0)
  * Bumps [cypress-file-upload](https://github.com/abramenal/cypress-file-upload) from 5.0.5 to 5.0.6.
    - [Release notes](https://github.com/abramenal/cypress-file-upload/releases)
    - [Commits](https://github.com/abramenal/cypress-file-upload/compare/v5.0.5...v5.0.6)
  * Bumps cypress/included from 7.0.1 to 7.1.0.
  * Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.2.1 to 5.2.2.
    - [Release notes](https://github.com/webpack-contrib/css-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.2.1...v5.2.2)
  * Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 8.1.0 to 8.1.1.
    - [Release notes](https://github.com/webpack-contrib/less-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/less-loader/compare/v8.1.0...v8.1.1)
  * Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.6.0 to 4.6.1.
    - [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
    - [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.6.0...4.6.1)
  * Bumps [validator](https://github.com/validatorjs/validator.js) from 13.5.2 to 13.6.0.
    - [Release notes](https://github.com/validatorjs/validator.js/releases)
    - [Changelog](https://github.com/validatorjs/validator.js/blob/13.6.0/CHANGELOG.md)
    - [Commits](https://github.com/validatorjs/validator.js/compare/13.5.2...13.6.0)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.33.2 to 5.35.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.33.2...v5.35.0)
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.10.1 to 3.10.2.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.10.2/packages/core-js)
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.13.15 to 7.13.16.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.13.16/packages/babel-core)
  * Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.2.2 to 5.2.4.
    - [Release notes](https://github.com/webpack-contrib/css-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.2.2...v5.2.4)
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.2.10 to 8.2.12.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.2.10...8.2.12)
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.24.0 to 7.25.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.24.0...v7.25.0)
  * Bumps [msw](https://github.com/mswjs/msw) from 0.28.1 to 0.28.2.
    - [Release notes](https://github.com/mswjs/msw/releases)
    - [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/mswjs/msw/compare/v0.28.1...v0.28.2)
  * Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.30.3 to 7.30.4.
    - [Release notes](https://github.com/testing-library/dom-testing-library/releases)
    - [Changelog](https://github.com/testing-library/dom-testing-library/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.30.3...v7.30.4)
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.10.2 to 3.11.0.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.11.0/packages/core-js)
  * Bumps [jest-watch-typeahead](https://github.com/jest-community/jest-watch-typeahead) from 0.6.2 to 0.6.3.
    - [Release notes](https://github.com/jest-community/jest-watch-typeahead/releases)
    - [Changelog](https://github.com/jest-community/jest-watch-typeahead/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/jest-community/jest-watch-typeahead/compare/v0.6.2...v0.6.3)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.35.0 to 5.35.1.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.35.0...v5.35.1)
  * Bumps [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) from 5.11.10 to 5.12.0.
    - [Release notes](https://github.com/testing-library/jest-dom/releases)
    - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/jest-dom/compare/v5.11.10...v5.12.0)
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.2.12 to 8.2.13.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.2.12...8.2.13)
  * Bumps [react-redux](https://github.com/reduxjs/react-redux) from 7.2.3 to 7.2.4.
    - [Release notes](https://github.com/reduxjs/react-redux/releases)
    - [Changelog](https://github.com/reduxjs/react-redux/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/reduxjs/react-redux/compare/v7.2.3...v7.2.4)
  * Bumps [@stripe/stripe-js](https://github.com/stripe/stripe-js) from 1.13.2 to 1.14.0.
    - [Release notes](https://github.com/stripe/stripe-js/releases)
    - [Commits](https://github.com/stripe/stripe-js/compare/v1.13.2...v1.14.0)
  * Bumps [@material-ui/core](https://github.com/mui-org/material-ui/tree/HEAD/packages/material-ui) from 4.11.3 to 4.11.4.
    - [Release notes](https://github.com/mui-org/material-ui/releases)
    - [Changelog](https://github.com/mui-org/material-ui/blob/v4.11.4/CHANGELOG.md)
    - [Commits](https://github.com/mui-org/material-ui/commits/v4.11.4/packages/material-ui)
  * Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.5.0 to 1.6.0.
    - [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
    - [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.5.0...v1.6.0)
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.13.16 to 7.14.0.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.0/packages/babel-core)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.35.1 to 5.36.2.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.35.1...v5.36.2)
  * Bumps [@material-ui/lab](https://github.com/mui-org/material-ui/tree/HEAD/packages/material-ui-lab) from 4.0.0-alpha.57 to 4.0.0-alpha.58.
    - [Release notes](https://github.com/mui-org/material-ui/releases)
    - [Changelog](https://github.com/mui-org/material-ui/blob/next/CHANGELOG.md)
    - [Commits](https://github.com/mui-org/material-ui/commits/HEAD/packages/material-ui-lab)
  * Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.6.1 to 4.6.2.
    - [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
    - [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.6.1...4.6.2)
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.11.0 to 3.11.1.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.11.1/packages/core-js)
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.13.15 to 7.14.0.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.0/packages/babel-preset-env)
  * Bumps node from 15.14.0-alpine to 16.0.0-alpine.
  * Bumps [cypress-file-upload](https://github.com/abramenal/cypress-file-upload) from 5.0.6 to 5.0.7.
    - [Release notes](https://github.com/abramenal/cypress-file-upload/releases)
    - [Commits](https://github.com/abramenal/cypress-file-upload/commits)
  * Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.4.3 to 1.4.4.
    - [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
    - [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.4.3...v1.4.4)
  * Bumps cypress/included from 7.1.0 to 7.2.0.
  * Bumps [lodash](https://github.com/lodash/lodash) from 4.17.19 to 4.17.21.
    - [Release notes](https://github.com/lodash/lodash/releases)
    - [Commits](https://github.com/lodash/lodash/compare/4.17.19...4.17.21)
  * Bumps [lodash](https://github.com/lodash/lodash) from 4.17.20 to 4.17.21.
    - [Release notes](https://github.com/lodash/lodash/releases)
    - [Commits](https://github.com/lodash/lodash/compare/4.17.20...4.17.21)
  * Bumps [ua-parser-js](https://github.com/faisalman/ua-parser-js) from 0.7.20 to 0.7.28.
    - [Release notes](https://github.com/faisalman/ua-parser-js/releases)
    - [Commits](https://github.com/faisalman/ua-parser-js/compare/0.7.20...0.7.28)
  * Bumps [hosted-git-info](https://github.com/npm/hosted-git-info) from 2.8.2 to 2.8.9.
    - [Release notes](https://github.com/npm/hosted-git-info/releases)
    - [Changelog](https://github.com/npm/hosted-git-info/blob/v2.8.9/CHANGELOG.md)
    - [Commits](https://github.com/npm/hosted-git-info/compare/v2.8.2...v2.8.9)
  * Bumps [webpack-cli](https://github.com/webpack/webpack-cli) from 4.6.0 to 4.7.0.
    - [Release notes](https://github.com/webpack/webpack-cli/releases)
    - [Changelog](https://github.com/webpack/webpack-cli/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack/webpack-cli/compare/webpack-cli@4.6.0...webpack-cli@4.7.0)
  * Bumps node from 16.0.0-alpine to 16.1.0-alpine.
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.5.1 to 35.6.2.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.5.1...v35.6.2)
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.2.13 to 8.2.14.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.2.13...8.2.14)
  * Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.12.0 to 2.13.0.
    - [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
    - [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.12.0...v2.13.0)
  * Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.30.4 to 7.31.0.
    - [Release notes](https://github.com/testing-library/dom-testing-library/releases)
    - [Changelog](https://github.com/testing-library/dom-testing-library/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.30.4...v7.31.0)
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.25.0 to 7.26.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.25.0...v7.26.0)
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.11.1 to 3.12.1.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.12.1/packages/core-js)
  * Bumps [lint-staged](https://github.com/okonet/lint-staged) from 10.5.4 to 11.0.0.
    - [Release notes](https://github.com/okonet/lint-staged/releases)
    - [Commits](https://github.com/okonet/lint-staged/compare/v10.5.4...v11.0.0)
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.14.0 to 7.14.1.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.1/packages/babel-preset-env)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.36.2 to 5.37.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.36.2...v5.37.0)
  * Bumps [@testing-library/react](https://github.com/testing-library/react-testing-library) from 11.2.6 to 11.2.7.
    - [Release notes](https://github.com/testing-library/react-testing-library/releases)
    - [Changelog](https://github.com/testing-library/react-testing-library/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/react-testing-library/compare/v11.2.6...v11.2.7)
  * Bumps [postcss-loader](https://github.com/webpack-contrib/postcss-loader) from 5.2.0 to 5.3.0.
    - [Release notes](https://github.com/webpack-contrib/postcss-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/postcss-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/postcss-loader/compare/v5.2.0...v5.3.0)
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.14.0 to 7.14.2.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.2/packages/babel-core)
  * Bumps [xterm](https://github.com/xtermjs/xterm.js) from 4.11.0 to 4.12.0.
    - [Release notes](https://github.com/xtermjs/xterm.js/releases)
    - [Commits](https://github.com/xtermjs/xterm.js/compare/4.11.0...4.12.0)
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.2.14 to 8.2.15.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.2.14...8.2.15)
  * Bumps [@babel/plugin-transform-runtime](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-transform-runtime) from 7.13.15 to 7.14.2.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.2/packages/babel-plugin-transform-runtime)
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.6.2 to 35.7.1.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.6.2...v35.7.1)
  * Bumps [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import) from 2.22.1 to 2.23.2.
    - [Release notes](https://github.com/benmosher/eslint-plugin-import/releases)
    - [Changelog](https://github.com/benmosher/eslint-plugin-import/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/benmosher/eslint-plugin-import/compare/v2.22.1...v2.23.2)
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.14.1 to 7.14.2.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.2/packages/babel-preset-env)
  * Bumps playwright from v1.10.0 to v1.11.0.
  * Bumps [playwright](https://github.com/Microsoft/playwright) from 1.10.0 to 1.11.0.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.10.0...v1.11.0)
  * Bumps [playwright-chromium](https://github.com/Microsoft/playwright) from 1.10.0 to 1.11.0.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.10.0...v1.11.0)
  * Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.13.0 to 2.13.1.
    - [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
    - [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.13.0...v2.13.1)
  * Bumps [playwright](https://github.com/Microsoft/playwright) from 1.11.0 to 1.11.1.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.11.0...v1.11.1)
  * Bumps playwright from v1.11.0 to v1.11.1.
  * Bumps [browserslist](https://github.com/browserslist/browserslist) from 4.16.3 to 4.16.6.
    - [Release notes](https://github.com/browserslist/browserslist/releases)
    - [Changelog](https://github.com/browserslist/browserslist/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/browserslist/browserslist/compare/4.16.3...4.16.6)
  * Bumps [playwright-chromium](https://github.com/Microsoft/playwright) from 1.11.0 to 1.11.1.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.11.0...v1.11.1)
  * Bumps node from 16.1.0-alpine to 16.2.0-alpine.
  * Bumps [@stripe/stripe-js](https://github.com/stripe/stripe-js) from 1.14.0 to 1.15.0.
    - [Release notes](https://github.com/stripe/stripe-js/releases)
    - [Commits](https://github.com/stripe/stripe-js/compare/v1.14.0...v1.15.0)
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.14.2 to 7.14.3.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.3/packages/babel-core)
  * Bumps [ws](https://github.com/websockets/ws) from 7.4.4 to 7.4.6.
    - [Release notes](https://github.com/websockets/ws/releases)
    - [Commits](https://github.com/websockets/ws/compare/7.4.4...7.4.6)
  * Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.2.4 to 5.2.6.
    - [Release notes](https://github.com/webpack-contrib/css-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.2.4...v5.2.6)
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.37.0 to 5.38.1.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.37.0...v5.38.1)
  * Bumps nginx from 1.19.10-alpine to 1.21.0-alpine.
  * Bumps [typescript](https://github.com/Microsoft/TypeScript) from 4.2.4 to 4.3.2.
    - [Release notes](https://github.com/Microsoft/TypeScript/releases)
    - [Commits](https://github.com/Microsoft/TypeScript/compare/v4.2.4...v4.3.2)
  * Bumps [dayjs](https://github.com/iamkun/dayjs) from 1.10.4 to 1.10.5.
    - [Release notes](https://github.com/iamkun/dayjs/releases)
    - [Changelog](https://github.com/iamkun/dayjs/blob/dev/CHANGELOG.md)
    - [Commits](https://github.com/iamkun/dayjs/compare/v1.10.4...v1.10.5)
  * Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 8.1.1 to 9.0.0.
    - [Release notes](https://github.com/webpack-contrib/less-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/less-loader/compare/v8.1.1...v9.0.0)
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.14.2 to 7.14.4.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.4/packages/babel-preset-env)
  * Bumps [jest-resolve](https://github.com/facebook/jest/tree/HEAD/packages/jest-resolve) from 26.6.2 to 27.0.2.
    - [Release notes](https://github.com/facebook/jest/releases)
    - [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/facebook/jest/commits/v27.0.2/packages/jest-resolve)
  * Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.23.2 to 7.24.0.
    - [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
    - [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.23.2...v7.24.0)
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.2.15 to 8.3.0.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.2.15...8.3.0)
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.12.1 to 3.13.1.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.13.1/packages/core-js)
  * Bumps [react-big-calendar](https://github.com/jquense/react-big-calendar) from 0.33.2 to 0.33.4.
    - [Release notes](https://github.com/jquense/react-big-calendar/releases)
    - [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/jquense/react-big-calendar/compare/v0.33.2...v0.33.4)
  * Bumps [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import) from 2.23.2 to 2.23.4.
    - [Release notes](https://github.com/benmosher/eslint-plugin-import/releases)
    - [Changelog](https://github.com/benmosher/eslint-plugin-import/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/benmosher/eslint-plugin-import/compare/v2.23.2...v2.23.4)
  * Bumps [msw](https://github.com/mswjs/msw) from 0.28.2 to 0.29.0.
    - [Release notes](https://github.com/mswjs/msw/releases)
    - [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/mswjs/msw/compare/v0.28.2...v0.29.0)
  * Bumps [jest-watch-typeahead](https://github.com/jest-community/jest-watch-typeahead) from 0.6.3 to 0.6.4.
    - [Release notes](https://github.com/jest-community/jest-watch-typeahead/releases)
    - [Changelog](https://github.com/jest-community/jest-watch-typeahead/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/jest-community/jest-watch-typeahead/compare/v0.6.3...v0.6.4)
  * Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.2.5 to 10.2.6.
    - [Release notes](https://github.com/postcss/autoprefixer/releases)
    - [Changelog](https://github.com/postcss/autoprefixer/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/autoprefixer/compare/10.2.5...10.2.6)
  * Bumps [jest-junit](https://github.com/jest-community/jest-junit) from 12.0.0 to 12.1.0.
    - [Release notes](https://github.com/jest-community/jest-junit/releases)
    - [Commits](https://github.com/jest-community/jest-junit/compare/v12.0.0...v12.1.0)
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.7.1 to 35.8.2.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.7.1...v35.8.2)
  * Bumps [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) from 1.4.0 to 1.4.1.
    - [Release notes](https://github.com/stripe/react-stripe-js/releases)
    - [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/stripe/react-stripe-js/compare/v1.4.0...v1.4.1)
  * Bumps [babel-jest](https://github.com/facebook/jest/tree/HEAD/packages/babel-jest) from 26.6.3 to 27.0.2.
    - [Release notes](https://github.com/facebook/jest/releases)
    - [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/facebook/jest/commits/v27.0.2/packages/babel-jest)
  * Bumps [util](https://github.com/browserify/node-util) from 0.12.3 to 0.12.4.
    - [Release notes](https://github.com/browserify/node-util/releases)
    - [Changelog](https://github.com/browserify/node-util/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/browserify/node-util/compare/v0.12.3...v0.12.4)
  * Bumps [react-big-calendar](https://github.com/jquense/react-big-calendar) from 0.33.4 to 0.33.5.
    - [Release notes](https://github.com/jquense/react-big-calendar/releases)
    - [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/jquense/react-big-calendar/compare/v0.33.4...v0.33.5)
  * Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.6.2 to 4.6.4.
    - [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
    - [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.6.2...4.6.4)
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.26.0 to 7.27.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.26.0...v7.27.0)
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.8.2 to 35.8.3.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.8.2...v35.8.3)
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.8.3 to 35.8.4.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.8.3...v35.8.4)
    ---
    updated-dependencies:
    - dependency-name: victory
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps node from 16.2.0-alpine to 16.3.0-alpine.
    ---
    updated-dependencies:
    - dependency-name: node
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.27.0 to 7.28.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.27.0...v7.28.0)
    ---
    updated-dependencies:
    - dependency-name: eslint
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.31.0 to 7.31.2.
    - [Release notes](https://github.com/testing-library/dom-testing-library/releases)
    - [Changelog](https://github.com/testing-library/dom-testing-library/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.31.0...v7.31.2)
    ---
    updated-dependencies:
    - dependency-name: "@testing-library/dom"
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [jest-resolve](https://github.com/facebook/jest/tree/HEAD/packages/jest-resolve) from 27.0.2 to 27.0.4.
    - [Release notes](https://github.com/facebook/jest/releases)
    - [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/facebook/jest/commits/v27.0.4/packages/jest-resolve)
    ---
    updated-dependencies:
    - dependency-name: jest-resolve
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.13.1 to 3.14.0.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.14.0/packages/core-js)
    ---
    updated-dependencies:
    - dependency-name: core-js
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) from 5.12.0 to 5.13.0.
    - [Release notes](https://github.com/testing-library/jest-dom/releases)
    - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/jest-dom/compare/v5.12.0...v5.13.0)
    ---
    updated-dependencies:
    - dependency-name: "@testing-library/jest-dom"
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [webpack-cli](https://github.com/webpack/webpack-cli) from 4.7.0 to 4.7.2.
    - [Release notes](https://github.com/webpack/webpack-cli/releases)
    - [Changelog](https://github.com/webpack/webpack-cli/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack/webpack-cli/compare/webpack-cli@4.7.0...webpack-cli@4.7.2)
    ---
    updated-dependencies:
    - dependency-name: webpack-cli
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [@reduxjs/toolkit](https://github.com/reduxjs/redux-toolkit) from 1.5.1 to 1.6.0.
    - [Release notes](https://github.com/reduxjs/redux-toolkit/releases)
    - [Commits](https://github.com/reduxjs/redux-toolkit/compare/v1.5.1...v1.6.0)
    ---
    updated-dependencies:
    - dependency-name: "@reduxjs/toolkit"
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [@babel/plugin-proposal-class-properties](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-proposal-class-properties) from 7.13.0 to 7.14.5.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.5/packages/babel-plugin-proposal-class-properties)
    ---
    updated-dependencies:
    - dependency-name: "@babel/plugin-proposal-class-properties"
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.3.0 to 8.3.1.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.3.0...8.3.1)
    ---
    updated-dependencies:
    - dependency-name: postcss
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.14.4 to 7.14.5.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.5/packages/babel-preset-env)
    ---
    updated-dependencies:
    - dependency-name: "@babel/preset-env"
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.14.3 to 7.14.5.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.5/packages/babel-core)
    ---
    updated-dependencies:
    - dependency-name: "@babel/core"
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [jest-junit](https://github.com/jest-community/jest-junit) from 12.1.0 to 12.2.0.
    - [Release notes](https://github.com/jest-community/jest-junit/releases)
    - [Commits](https://github.com/jest-community/jest-junit/compare/v12.1.0...v12.2.0)
    ---
    updated-dependencies:
    - dependency-name: jest-junit
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [@babel/plugin-transform-runtime](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-transform-runtime) from 7.14.2 to 7.14.5.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.5/packages/babel-plugin-transform-runtime)
    ---
    updated-dependencies:
    - dependency-name: "@babel/plugin-transform-runtime"
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 9.0.0 to 9.1.0.
    - [Release notes](https://github.com/webpack-contrib/less-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/less-loader/compare/v9.0.0...v9.1.0)
    ---
    updated-dependencies:
    - dependency-name: less-loader
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [@babel/preset-react](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-react) from 7.13.13 to 7.14.5.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.5/packages/babel-preset-react)
    ---
    updated-dependencies:
    - dependency-name: "@babel/preset-react"
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.3.1 to 8.3.2.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.3.1...8.3.2)
    ---
    updated-dependencies:
    - dependency-name: postcss
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [postcss-loader](https://github.com/webpack-contrib/postcss-loader) from 5.3.0 to 6.1.0.
    - [Release notes](https://github.com/webpack-contrib/postcss-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/postcss-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/postcss-loader/compare/v5.3.0...v6.1.0)
    ---
    updated-dependencies:
    - dependency-name: postcss-loader
      dependency-type: direct:development
      update-type: version-update:semver-major
    ...
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.8.4 to 35.8.5.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.8.4...v35.8.5)
    ---
    updated-dependencies:
    - dependency-name: victory
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) from 5.13.0 to 5.14.1.
    - [Release notes](https://github.com/testing-library/jest-dom/releases)
    - [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/jest-dom/compare/v5.13.0...v5.14.1)
    ---
    updated-dependencies:
    - dependency-name: "@testing-library/jest-dom"
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [xterm](https://github.com/xtermjs/xterm.js) from 4.12.0 to 4.13.0.
    - [Release notes](https://github.com/xtermjs/xterm.js/releases)
    - [Commits](https://github.com/xtermjs/xterm.js/compare/4.12.0...4.13.0)
    ---
    updated-dependencies:
    - dependency-name: xterm
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [playwright](https://github.com/Microsoft/playwright) from 1.11.1 to 1.12.2.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.11.1...v1.12.2)
    ---
    updated-dependencies:
    - dependency-name: playwright
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps playwright from v1.11.1 to v1.12.2.
    ---
    updated-dependencies:
    - dependency-name: playwright
      dependency-type: direct:production
    ...
  * Bumps [playwright-chromium](https://github.com/Microsoft/playwright) from 1.11.1 to 1.12.2.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.11.1...v1.12.2)
    ---
    updated-dependencies:
    - dependency-name: playwright-chromium
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.8.5 to 35.8.6.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.8.5...v35.8.6)
    ---
    updated-dependencies:
    - dependency-name: victory
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.14.5 to 7.14.6.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.6/packages/babel-core)
    ---
    updated-dependencies:
    - dependency-name: "@babel/core"
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.3.2 to 8.3.4.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.3.2...8.3.4)
    ---
    updated-dependencies:
    - dependency-name: postcss
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.38.1 to 5.39.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.38.1...v5.39.0)
    ---
    updated-dependencies:
    - dependency-name: webpack
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [typescript](https://github.com/Microsoft/TypeScript) from 4.3.2 to 4.3.4.
    - [Release notes](https://github.com/Microsoft/TypeScript/releases)
    - [Commits](https://github.com/Microsoft/TypeScript/compare/v4.3.2...v4.3.4)
    ---
    updated-dependencies:
    - dependency-name: typescript
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [postcss](https://github.com/postcss/postcss) from 8.3.4 to 8.3.5.
    - [Release notes](https://github.com/postcss/postcss/releases)
    - [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/postcss/postcss/compare/8.3.4...8.3.5)
    ---
    updated-dependencies:
    - dependency-name: postcss
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 9.1.0 to 10.0.0.
    - [Release notes](https://github.com/webpack-contrib/less-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/less-loader/compare/v9.1.0...v10.0.0)
    ---
    updated-dependencies:
    - dependency-name: less-loader
      dependency-type: direct:development
      update-type: version-update:semver-major
    ...
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.28.0 to 7.29.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.28.0...v7.29.0)
    ---
    updated-dependencies:
    - dependency-name: eslint
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.39.0 to 5.39.1.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.39.0...v5.39.1)
    ---
    updated-dependencies:
    - dependency-name: webpack
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [@stripe/stripe-js](https://github.com/stripe/stripe-js) from 1.15.0 to 1.15.1.
    - [Release notes](https://github.com/stripe/stripe-js/releases)
    - [Commits](https://github.com/stripe/stripe-js/compare/v1.15.0...v1.15.1)
    ---
    updated-dependencies:
    - dependency-name: "@stripe/stripe-js"
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.14.0 to 3.15.0.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.15.0/packages/core-js)
    ---
    updated-dependencies:
    - dependency-name: core-js
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.14.5 to 7.14.7.
    - [Release notes](https://github.com/babel/babel/releases)
    - [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/babel/babel/commits/v7.14.7/packages/babel-preset-env)
    ---
    updated-dependencies:
    - dependency-name: "@babel/preset-env"
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [playwright](https://github.com/Microsoft/playwright) from 1.12.2 to 1.12.3.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.12.2...v1.12.3)
    ---
    updated-dependencies:
    - dependency-name: playwright
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [jest-resolve](https://github.com/facebook/jest/tree/HEAD/packages/jest-resolve) from 27.0.4 to 27.0.5.
    - [Release notes](https://github.com/facebook/jest/releases)
    - [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/facebook/jest/commits/v27.0.5/packages/jest-resolve)
    ---
    updated-dependencies:
    - dependency-name: jest-resolve
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.39.1 to 5.40.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.39.1...v5.40.0)
    ---
    updated-dependencies:
    - dependency-name: webpack
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps playwright from v1.12.2 to v1.12.3.
    ---
    updated-dependencies:
    - dependency-name: playwright
      dependency-type: direct:production
    ...
  * Bumps [jest](https://github.com/facebook/jest) from 27.0.4 to 27.0.5.
    - [Release notes](https://github.com/facebook/jest/releases)
    - [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/facebook/jest/compare/v27.0.4...v27.0.5)
    ---
    updated-dependencies:
    - dependency-name: jest
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [playwright-chromium](https://github.com/Microsoft/playwright) from 1.12.2 to 1.12.3.
    - [Release notes](https://github.com/Microsoft/playwright/releases)
    - [Commits](https://github.com/Microsoft/playwright/compare/v1.12.2...v1.12.3)
    ---
    updated-dependencies:
    - dependency-name: playwright-chromium
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [react-dropzone](https://github.com/react-dropzone/react-dropzone) from 11.3.2 to 11.3.4.
    - [Release notes](https://github.com/react-dropzone/react-dropzone/releases)
    - [Commits](https://github.com/react-dropzone/react-dropzone/compare/v11.3.2...v11.3.4)
    ---
    updated-dependencies:
    - dependency-name: react-dropzone
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) from 5.3.1 to 5.3.2.
    - [Release notes](https://github.com/jantimon/html-webpack-plugin/releases)
    - [Changelog](https://github.com/jantimon/html-webpack-plugin/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/jantimon/html-webpack-plugin/compare/v5.3.1...v5.3.2)
    ---
    updated-dependencies:
    - dependency-name: html-webpack-plugin
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.15.0 to 3.15.1.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.15.1/packages/core-js)
    ---
    updated-dependencies:
    - dependency-name: core-js
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [msw](https://github.com/mswjs/msw) from 0.29.0 to 0.30.0.
    - [Release notes](https://github.com/mswjs/msw/releases)
    - [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/mswjs/msw/compare/v0.29.0...v0.30.0)
    ---
    updated-dependencies:
    - dependency-name: msw
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [victory](https://github.com/formidablelabs/victory) from 35.8.6 to 35.9.0.
    - [Release notes](https://github.com/formidablelabs/victory/releases)
    - [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/formidablelabs/victory/compare/v35.8.6...v35.9.0)
    ---
    updated-dependencies:
    - dependency-name: victory
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.6.0 to 1.6.1.
    - [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
    - [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.6.0...v1.6.1)
    ---
    updated-dependencies:
    - dependency-name: mini-css-extract-plugin
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.40.0 to 5.42.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.40.0...v5.42.0)
    ---
    updated-dependencies:
    - dependency-name: webpack
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [typescript](https://github.com/Microsoft/TypeScript) from 4.3.4 to 4.3.5.
    - [Release notes](https://github.com/Microsoft/TypeScript/releases)
    - [Commits](https://github.com/Microsoft/TypeScript/compare/v4.3.4...v4.3.5)
    ---
    updated-dependencies:
    - dependency-name: typescript
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [husky](https://github.com/typicode/husky) from 6.0.0 to 7.0.0.
    - [Release notes](https://github.com/typicode/husky/releases)
    - [Commits](https://github.com/typicode/husky/compare/v6.0.0...v7.0.0)
    ---
    updated-dependencies:
    - dependency-name: husky
      dependency-type: direct:development
      update-type: version-update:semver-major
    ...
  * Bumps [postcss-loader](https://github.com/webpack-contrib/postcss-loader) from 6.1.0 to 6.1.1.
    - [Release notes](https://github.com/webpack-contrib/postcss-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/postcss-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/postcss-loader/compare/v6.1.0...v6.1.1)
    ---
    updated-dependencies:
    - dependency-name: postcss-loader
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [msw](https://github.com/mswjs/msw) from 0.30.0 to 0.30.1.
    - [Release notes](https://github.com/mswjs/msw/releases)
    - [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/mswjs/msw/compare/v0.30.0...v0.30.1)
    ---
    updated-dependencies:
    - dependency-name: msw
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [jest](https://github.com/facebook/jest) from 27.0.5 to 27.0.6.
    - [Release notes](https://github.com/facebook/jest/releases)
    - [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/facebook/jest/compare/v27.0.5...v27.0.6)
    ---
    updated-dependencies:
    - dependency-name: jest
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.31.2 to 8.1.0.
    - [Release notes](https://github.com/testing-library/dom-testing-library/releases)
    - [Changelog](https://github.com/testing-library/dom-testing-library/blob/main/CHANGELOG.md)
    - [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.31.2...v8.1.0)
    ---
    updated-dependencies:
    - dependency-name: "@testing-library/dom"
      dependency-type: direct:development
      update-type: version-update:semver-major
    ...
  * Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.6.1 to 2.0.0.
    - [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
    - [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.6.1...v2.0.0)
    ---
    updated-dependencies:
    - dependency-name: mini-css-extract-plugin
      dependency-type: direct:development
      update-type: version-update:semver-major
    ...
  * Bumps [eslint](https://github.com/eslint/eslint) from 7.29.0 to 7.30.0.
    - [Release notes](https://github.com/eslint/eslint/releases)
    - [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/eslint/eslint/compare/v7.29.0...v7.30.0)
    ---
    updated-dependencies:
    - dependency-name: eslint
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.15.1 to 3.15.2.
    - [Release notes](https://github.com/zloirock/core-js/releases)
    - [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/zloirock/core-js/commits/v3.15.2/packages/core-js)
    ---
    updated-dependencies:
    - dependency-name: core-js
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 10.0.0 to 10.0.1.
    - [Release notes](https://github.com/webpack-contrib/less-loader/releases)
    - [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/less-loader/compare/v10.0.0...v10.0.1)
    ---
    updated-dependencies:
    - dependency-name: less-loader
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 2.0.0 to 2.1.0.
    - [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
    - [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/v2.1.0/CHANGELOG.md)
    - [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v2.0.0...v2.1.0)
    ---
    updated-dependencies:
    - dependency-name: mini-css-extract-plugin
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.42.0 to 5.42.1.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.42.0...v5.42.1)
    ---
    updated-dependencies:
    - dependency-name: webpack
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...
  * Bumps [webpack](https://github.com/webpack/webpack) from 5.42.1 to 5.43.0.
    - [Release notes](https://github.com/webpack/webpack/releases)
    - [Commits](https://github.com/webpack/webpack/compare/v5.42.1...v5.43.0)
    ---
    updated-dependencies:
    - dependency-name: webpack
      dependency-type: direct:development
      update-type: version-update:semver-minor
    ...
  * Bumps [husky](https://github.com/typicode/husky) from 7.0.0 to 7.0.1.
    - [Release notes](https://github.com/typicode/husky/releases)
    - [Commits](https://github.com/typicode/husky/compare/v7.0.0...v7.0.1)
    ---
    updated-dependencies:
    - dependency-name: husky
      dependency-type: direct:development
      update-type: version-update:semver-patch
    ...

#### inventory (3.0.0)

New changes in inventory since 2.3.0:

* New internal endpoint for getting device's groups
* Modify internal endpoint `/devices/:status` to
  `/devices/status/:status`
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.1 to 3.13.3.
  * Bumps golang from 1.15.8-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [github.com/spf13/viper](https://github.com/spf13/viper) from 1.7.1 to 1.8.0.
    - [Release notes](https://github.com/spf13/viper/releases)
    - [Commits](https://github.com/spf13/viper/compare/v1.7.1...v1.8.0)
    ---
    updated-dependencies:
    - dependency-name: github.com/spf13/viper
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### inventory-enterprise (3.0.0)

New changes in inventory-enterprise since 2.3.0:

* fix RBAC group logic always filtering by group names
  ([MEN-4728](https://tracker.mender.io/browse/MEN-4728))
* New internal endpoint for getting device's groups
* Modify internal endpoint `/devices/:status` to
  `/devices/status/:status`
* New internal endpoint for checking if given devices belong to given groups
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.7.1 to 8.8.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.7.1...v8.8.0)
  * Bumps alpine from 3.13.1 to 3.13.3.
  * Bumps golang from 1.15.8-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.8.0 to 8.8.2.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.8.0...v8.8.2)
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.8.2 to 8.9.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.8.2...v8.9.0)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.9.0 to 8.10.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.9.0...v8.10.0)
    ---
    updated-dependencies:
    - dependency-name: github.com/go-redis/redis/v8
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [github.com/spf13/viper](https://github.com/spf13/viper) from 1.7.1 to 1.8.0.
    - [Release notes](https://github.com/spf13/viper/releases)
    - [Commits](https://github.com/spf13/viper/compare/v1.7.1...v1.8.0)
    ---
    updated-dependencies:
    - dependency-name: github.com/spf13/viper
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [github.com/spf13/viper](https://github.com/spf13/viper) from 1.7.1 to 1.8.0.
    - [Release notes](https://github.com/spf13/viper/releases)
    - [Commits](https://github.com/spf13/viper/compare/v1.7.1...v1.8.0)
    ---
    updated-dependencies:
    - dependency-name: github.com/spf13/viper
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### tenantadm (3.2.0)

New changes in tenantadm since 3.1.0:

* Suspend the tenant on trial cancellation by the user
  ([MEN-4606](https://tracker.mender.io/browse/MEN-4606))
* add suspend-tenants-expired-trial CLI command
  ([MEN-4602](https://tracker.mender.io/browse/MEN-4602))
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...

#### useradm (1.15.0)

New changes in useradm since 1.14.0:

* internal API end-point to remove users
  ([MEN-4628](https://tracker.mender.io/browse/MEN-4628))
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### useradm-enterprise (1.15.0)

New changes in useradm-enterprise since 1.14.0:

* internal API end-point to remove users
  ([MEN-4628](https://tracker.mender.io/browse/MEN-4628))
* internal API end-point to remove users
  ([MEN-4628](https://tracker.mender.io/browse/MEN-4628))
* fix duplicated user email address handling
* 2fa enable/disable endpoints
* security fix: invalidate user JWT token cache on logout
  ([MEN-4754](https://tracker.mender.io/browse/MEN-4754))
* Aggregated Dependabot Changelogs:
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.7.1 to 8.8.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.7.1...v8.8.0)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.8.0 to 8.8.2.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.8.0...v8.8.2)
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.8.2 to 8.9.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.8.2...v8.9.0)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.9.0 to 8.10.0.
    - [Release notes](https://github.com/go-redis/redis/releases)
    - [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/go-redis/redis/compare/v8.9.0...v8.10.0)
    ---
    updated-dependencies:
    - dependency-name: github.com/go-redis/redis/v8
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### workflows (2.0.0)

New changes in workflows since 1.4.0:

* update device status workflow: update the path of the status
  endpoint
* Aggregated Dependabot Changelogs:
  * Bumps golang from 1.14-alpine3.12 to 1.16.2-alpine3.12.
  * Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.6.0 to 1.8.1.
    - [Release notes](https://github.com/sirupsen/logrus/releases)
    - [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/sirupsen/logrus/compare/v1.6.0...v1.8.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.5.0.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...v1.5.0)
  * Bumps alpine from 3.13.0 to 3.13.3.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.6.3 to 1.7.1.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.6.3...v1.7.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.7.1 to 1.7.2.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.7.1...v1.7.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### workflows-enterprise (2.0.0)

New changes in workflows-enterprise since 1.4.0:

* Send alert email workflow for Monitoring
  ([MEN-4650](https://tracker.mender.io/browse/MEN-4650))
* extend deploy device configuration workflow with update control map
* append tenant cancellation data to Google Sheets
  ([MEN-4705](https://tracker.mender.io/browse/MEN-4705))
* update device status workflow: update the path of the status
  endpoint
* Aggregated Dependabot Changelogs:
  * Bumps golang from 1.14-alpine3.12 to 1.16.2-alpine3.12.
  * Bumps golang from 1.14-alpine3.12 to 1.16.2-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
  * Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.6.0 to 1.8.1.
    - [Release notes](https://github.com/sirupsen/logrus/releases)
    - [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/sirupsen/logrus/compare/v1.6.0...v1.8.1)
  * Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.6.0 to 1.8.1.
    - [Release notes](https://github.com/sirupsen/logrus/releases)
    - [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/sirupsen/logrus/compare/v1.6.0...v1.8.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.5.0.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...v1.5.0)
  * Bumps alpine from 3.13.0 to 3.13.3.
  * Bumps alpine from 3.13.2 to 3.13.3.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps golang from 1.16.2-alpine3.12 to 1.16.3-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.0 to 1.5.1.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.0...v1.5.1)
  * Bumps alpine from 3.13.3 to 3.13.4.
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.6.3 to 1.7.1.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.6.3...v1.7.1)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.6.3 to 1.7.1.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.6.3...v1.7.1)
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps alpine from 3.13.4 to 3.13.5.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps golang from 1.16.3-alpine3.12 to 1.16.4-alpine3.12.
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.1 to 1.5.2.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.1...v1.5.2)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.7.1 to 1.7.2.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.7.1...v1.7.2)
  * Bumps [github.com/gin-gonic/gin](https://github.com/gin-gonic/gin) from 1.7.1 to 1.7.2.
    - [Release notes](https://github.com/gin-gonic/gin/releases)
    - [Changelog](https://github.com/gin-gonic/gin/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/gin-gonic/gin/compare/v1.7.1...v1.7.2)
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps golang from 1.16.4-alpine3.12 to 1.16.5-alpine3.12.
    ---
    updated-dependencies:
    - dependency-name: golang
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.5.2 to 1.5.3.
    - [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
    - [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.5.2...v1.5.3)
    ---
    updated-dependencies:
    - dependency-name: go.mongodb.org/mongo-driver
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps alpine from 3.13.5 to 3.14.0.
    ---
    updated-dependencies:
    - dependency-name: alpine
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...

#### integration (3.0.0)

New changes in integration since 2.7.0:

* Remove nginx-based api-gateway and replace with Traefik.
* fix auth verification on useradm APIs
  ([MEN-4623](https://tracker.mender.io/browse/MEN-4623))
* Enforce userauth middleware on non-signup tenantadm endpoints
  ([MEN-4657](https://tracker.mender.io/browse/MEN-4657))
* Full integration test for file limits
  ([MEN-4588](https://tracker.mender.io/browse/MEN-4588))
* [Træfik] Change dynamic config provider from "Docker" to "File"
* Fix mender-configure install in Docker image
  mendersoftware/mender-client-docker-addons
* Upgrade auditlogs to 1.2.0.
* Upgrade deployments to 3.0.0.
* Upgrade deployments-enterprise to 3.0.0.
* Upgrade deviceauth to 3.0.0.
* Upgrade deviceconfig to 1.1.0.
* Upgrade deviceconnect to 1.2.0.
* Upgrade gui to 3.0.0.
* Upgrade integration to 3.0.0.
* Upgrade inventory to 3.0.0.
* Upgrade inventory-enterprise to 3.0.0.
* Upgrade mender to 3.0.0.
* Upgrade mender-artifact to 3.6.0.
* Upgrade mender-connect to 1.2.0.
* Upgrade tenantadm to 3.2.0.
* Upgrade useradm to 1.15.0.
* Upgrade useradm-enterprise to 1.15.0.
* Upgrade workflows to 2.0.0.
* Upgrade workflows-enterprise to 2.0.0.
* Aggregated Dependabot Changelogs:
  * Bumps [python-dotenv](https://github.com/theskumar/python-dotenv) from 0.15.0 to 0.16.0.
    - [Release notes](https://github.com/theskumar/python-dotenv/releases)
    - [Changelog](https://github.com/theskumar/python-dotenv/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/theskumar/python-dotenv/compare/v0.15.0...v0.16.0)
  * Bumps [docker-compose](https://github.com/docker/compose) from 1.28.5 to 1.28.6.
    - [Release notes](https://github.com/docker/compose/releases)
    - [Changelog](https://github.com/docker/compose/blob/1.28.6/CHANGELOG.md)
    - [Commits](https://github.com/docker/compose/compare/1.28.5...1.28.6)
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.6 to 3.4.7.
    - [Release notes](https://github.com/pyca/cryptography/releases)
    - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/pyca/cryptography/compare/3.4.6...3.4.7)
  * Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.6 to 3.4.7.
    - [Release notes](https://github.com/pyca/cryptography/releases)
    - [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/pyca/cryptography/compare/3.4.6...3.4.7)
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.2 to 6.2.3.
    - [Release notes](https://github.com/pytest-dev/pytest/releases)
    - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.2...6.2.3)
  * Bumps [python-dotenv](https://github.com/theskumar/python-dotenv) from 0.16.0 to 0.17.0.
    - [Release notes](https://github.com/theskumar/python-dotenv/releases)
    - [Changelog](https://github.com/theskumar/python-dotenv/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/theskumar/python-dotenv/compare/v0.16.0...v0.17.0)
  * Bumps [pillow](https://github.com/python-pillow/Pillow) from 8.1.2 to 8.2.0.
    - [Release notes](https://github.com/python-pillow/Pillow/releases)
    - [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
    - [Commits](https://github.com/python-pillow/Pillow/compare/8.1.2...8.2.0)
  * Bumps python from 3.9.2 to 3.9.3.
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.2 to 6.2.3.
    - [Release notes](https://github.com/pytest-dev/pytest/releases)
    - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.2...6.2.3)
  * Bumps [docker](https://github.com/docker/docker-py) from 4.4.4 to 5.0.0.
    - [Release notes](https://github.com/docker/docker-py/releases)
    - [Commits](https://github.com/docker/docker-py/compare/4.4.4...5.0.0)
  * Bumps [docker-compose](https://github.com/docker/compose) from 1.28.6 to 1.29.1.
    - [Release notes](https://github.com/docker/compose/releases)
    - [Changelog](https://github.com/docker/compose/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/docker/compose/compare/1.28.6...1.29.1)
  * Bumps python from 3.9.3 to 3.9.5.
  * Bumps [python-dotenv](https://github.com/theskumar/python-dotenv) from 0.17.0 to 0.17.1.
    - [Release notes](https://github.com/theskumar/python-dotenv/releases)
    - [Changelog](https://github.com/theskumar/python-dotenv/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/theskumar/python-dotenv/compare/v0.17.0...v0.17.1)
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.3 to 6.2.4.
    - [Release notes](https://github.com/pytest-dev/pytest/releases)
    - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.3...6.2.4)
  * Bumps [attrs](https://github.com/python-attrs/attrs) from 20.3.0 to 21.2.0.
    - [Release notes](https://github.com/python-attrs/attrs/releases)
    - [Changelog](https://github.com/python-attrs/attrs/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/python-attrs/attrs/compare/20.3.0...21.2.0)
  * Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.3 to 3.11.4.
    - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
    - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/3.11.4/doc/changelog.rst)
    - [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.3...3.11.4)
  * Bumps [websockets](https://github.com/aaugustin/websockets) from 8.1 to 9.0.1.
    - [Release notes](https://github.com/aaugustin/websockets/releases)
    - [Changelog](https://github.com/aaugustin/websockets/blob/main/docs/changelog.rst)
    - [Commits](https://github.com/aaugustin/websockets/compare/8.1...9.0.1)
  * Bumps [websocket-client](https://github.com/websocket-client/websocket-client) from 0.58.0 to 0.59.0.
    - [Release notes](https://github.com/websocket-client/websocket-client/releases)
    - [Changelog](https://github.com/websocket-client/websocket-client/blob/master/ChangeLog)
    - [Commits](https://github.com/websocket-client/websocket-client/compare/v0.58.0...v0.59.0)
  * Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.3 to 6.2.4.
    - [Release notes](https://github.com/pytest-dev/pytest/releases)
    - [Changelog](https://github.com/pytest-dev/pytest/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/pytest/compare/6.2.3...6.2.4)
  * Bumps [websockets](https://github.com/aaugustin/websockets) from 9.0.1 to 9.0.2.
    - [Release notes](https://github.com/aaugustin/websockets/releases)
    - [Changelog](https://github.com/aaugustin/websockets/blob/9.0.2/docs/changelog.rst)
    - [Commits](https://github.com/aaugustin/websockets/compare/9.0.1...9.0.2)
  * Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.3 to 3.11.4.
    - [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
    - [Changelog](https://github.com/mongodb/mongo-python-driver/blob/3.11.4/doc/changelog.rst)
    - [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.3...3.11.4)
  * Bumps [attrs](https://github.com/python-attrs/attrs) from 20.3.0 to 21.2.0.
    - [Release notes](https://github.com/python-attrs/attrs/releases)
    - [Changelog](https://github.com/python-attrs/attrs/blob/main/CHANGELOG.rst)
    - [Commits](https://github.com/python-attrs/attrs/compare/20.3.0...21.2.0)
  * Bumps [stripe](https://github.com/stripe/stripe-python) from 2.56.0 to 2.57.0.
    - [Release notes](https://github.com/stripe/stripe-python/releases)
    - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/stripe/stripe-python/compare/v2.56.0...v2.57.0)
  * Bumps [six](https://github.com/benjaminp/six) from 1.15.0 to 1.16.0.
    - [Release notes](https://github.com/benjaminp/six/releases)
    - [Changelog](https://github.com/benjaminp/six/blob/master/CHANGES)
    - [Commits](https://github.com/benjaminp/six/compare/1.15.0...1.16.0)
  * Bumps [docker-compose](https://github.com/docker/compose) from 1.29.1 to 1.29.2.
    - [Release notes](https://github.com/docker/compose/releases)
    - [Changelog](https://github.com/docker/compose/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/docker/compose/compare/1.29.1...1.29.2)
  * Bumps [stripe](https://github.com/stripe/stripe-python) from 2.56.0 to 2.57.0.
    - [Release notes](https://github.com/stripe/stripe-python/releases)
    - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/stripe/stripe-python/compare/v2.56.0...v2.57.0)
  * Bumps [certifi](https://github.com/certifi/python-certifi) from 2020.12.5 to 2021.5.30.
    - [Release notes](https://github.com/certifi/python-certifi/releases)
    - [Commits](https://github.com/certifi/python-certifi/compare/2020.12.05...2021.05.30)
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.4 to 1.26.5.
    - [Release notes](https://github.com/urllib3/urllib3/releases)
    - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
    - [Commits](https://github.com/urllib3/urllib3/compare/1.26.4...1.26.5)
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.4 to 1.26.5.
    - [Release notes](https://github.com/urllib3/urllib3/releases)
    - [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
    - [Commits](https://github.com/urllib3/urllib3/compare/1.26.4...1.26.5)
  * Bumps [websockets](https://github.com/aaugustin/websockets) from 9.0.2 to 9.1.
    - [Release notes](https://github.com/aaugustin/websockets/releases)
    - [Changelog](https://github.com/aaugustin/websockets/blob/9.1/docs/changelog.rst)
    - [Commits](https://github.com/aaugustin/websockets/compare/9.0.2...9.1)
  * Bumps [execnet](https://github.com/pytest-dev/execnet) from 1.8.0 to 1.8.1.
    - [Release notes](https://github.com/pytest-dev/execnet/releases)
    - [Changelog](https://github.com/pytest-dev/execnet/blob/master/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/execnet/compare/v1.8.0...v1.8.1)
  * Bumps [stripe](https://github.com/stripe/stripe-python) from 2.57.0 to 2.58.0.
    - [Release notes](https://github.com/stripe/stripe-python/releases)
    - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/stripe/stripe-python/compare/v2.57.0...v2.58.0)
    ---
    updated-dependencies:
    - dependency-name: stripe
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [stripe](https://github.com/stripe/stripe-python) from 2.57.0 to 2.58.0.
    - [Release notes](https://github.com/stripe/stripe-python/releases)
    - [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/stripe/stripe-python/compare/v2.57.0...v2.58.0)
    ---
    updated-dependencies:
    - dependency-name: stripe
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [certifi](https://github.com/certifi/python-certifi) from 2020.12.5 to 2021.5.30.
    - [Release notes](https://github.com/certifi/python-certifi/releases)
    - [Commits](https://github.com/certifi/python-certifi/compare/2020.12.05...2021.05.30)
    ---
    updated-dependencies:
    - dependency-name: certifi
      dependency-type: direct:production
      update-type: version-update:semver-major
    ...
  * Bumps [execnet](https://github.com/pytest-dev/execnet) from 1.8.1 to 1.9.0.
    - [Release notes](https://github.com/pytest-dev/execnet/releases)
    - [Changelog](https://github.com/pytest-dev/execnet/blob/master/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/execnet/compare/v1.8.1...v1.9.0)
    ---
    updated-dependencies:
    - dependency-name: execnet
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [python-dotenv](https://github.com/theskumar/python-dotenv) from 0.17.1 to 0.18.0.
    - [Release notes](https://github.com/theskumar/python-dotenv/releases)
    - [Changelog](https://github.com/theskumar/python-dotenv/blob/master/CHANGELOG.md)
    - [Commits](https://github.com/theskumar/python-dotenv/compare/v0.17.1...v0.18.0)
    ---
    updated-dependencies:
    - dependency-name: python-dotenv
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [pytest-xdist](https://github.com/pytest-dev/pytest-xdist) from 2.2.1 to 2.3.0.
    - [Release notes](https://github.com/pytest-dev/pytest-xdist/releases)
    - [Changelog](https://github.com/pytest-dev/pytest-xdist/blob/master/CHANGELOG.rst)
    - [Commits](https://github.com/pytest-dev/pytest-xdist/compare/v2.2.1...v2.3.0)
    ---
    updated-dependencies:
    - dependency-name: pytest-xdist
      dependency-type: direct:production
      update-type: version-update:semver-minor
    ...
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.5 to 1.26.6.
    - [Release notes](https://github.com/urllib3/urllib3/releases)
    - [Changelog](https://github.com/urllib3/urllib3/blob/1.26.6/CHANGES.rst)
    - [Commits](https://github.com/urllib3/urllib3/compare/1.26.5...1.26.6)
    ---
    updated-dependencies:
    - dependency-name: urllib3
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.5 to 1.26.6.
    - [Release notes](https://github.com/urllib3/urllib3/releases)
    - [Changelog](https://github.com/urllib3/urllib3/blob/1.26.6/CHANGES.rst)
    - [Commits](https://github.com/urllib3/urllib3/compare/1.26.5...1.26.6)
    ---
    updated-dependencies:
    - dependency-name: urllib3
      dependency-type: direct:production
      update-type: version-update:semver-patch
    ...
  * Bumps [contextlib2](https://github.com/jazzband/contextlib2) from 0.6.0.post1 to 21.6.0.
    - [Release notes](https://github.com/jazzband/contextlib2/releases)
    - [Changelog](https://github.com/jazzband/contextlib2/blob/master/NEWS.rst)
    - [Commits](https://github.com/jazzband/contextlib2/compare/v0.6.0.post1...21.6.0)
    ---
    updated-dependencies:
    - dependency-name: contextlib2
      dependency-type: direct:production
      update-type: version-update:semver-major
    ...

## Mender 2.7.0

_Released 04.16.2021_

### Changelogs

#### auditlogs (1.1.0)

New changes in auditlogs since 1.0.0:

* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps golang from 1.14-alpine3.12 to 1.15.6-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...1.4.6)
* Bumps golang from 1.15.6-alpine3.12 to 1.16.0-alpine3.12.
* Bumps golang from 1.16.0-alpine3.12 to 1.16.2-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)

#### create-artifact-worker (1.0.2)

New changes in create-artifact-worker since 1.0.1:

* bugfix to allow spaces in artifact names
([MEN-4179](https://tracker.mender.io/browse/MEN-4179))
* upgrade mender-artifact to version 3.5.0.
This enables the create-artifact-worker to generate artifacts that
implement the provides and clear provides fields.
([MEN-4409](https://tracker.mender.io/browse/MEN-4409))

#### deployments (2.3.0)

New changes in deployments since 2.2.0:

* New internal endpoint for creating configuration deployments
* extend get /deployment query params with optional deployment type
* New endpoint for generating configuration artifacts on the fly
* Handle configuration artifacts on /device/deployments/next
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.24 to 1.36.28.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.24...v1.36.28)
* Bumps [github.com/google/uuid](https://github.com/google/uuid) from 1.1.4 to 1.1.5.
- [Release notes](https://github.com/google/uuid/releases)
- [Commits](https://github.com/google/uuid/compare/v1.1.4...v1.1.5)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.28 to 1.37.1.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.28...v1.37.1)
* Bumps [github.com/google/uuid](https://github.com/google/uuid) from 1.1.5 to 1.2.0.
- [Release notes](https://github.com/google/uuid/releases)
- [Commits](https://github.com/google/uuid/compare/v1.1.5...v1.2.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...1.4.6)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.1 to 1.37.10.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.1...v1.37.10)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.10 to 1.37.20.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.10...v1.37.20)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.20 to 1.37.25.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.20...v1.37.25)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.1)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.25 to 1.37.30.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.25...v1.37.30)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)

#### deployments-enterprise (2.3.0)

New changes in deployments-enterprise since 2.2.0:

* New internal endpoint for creating configuration deployments
* extend get /deployment query params with optional deployment type
* New endpoint for generating configuration artifacts on the fly
* Handle configuration artifacts on /device/deployments/next
* FIX: Phased deployments getting stuck on retries
* Fix: do not increment attempts on multiple subsequent failure status reports
* docs: Fix naming conflict in v1 and v2 NewDeployment definitions.
* docs: Document missing parameters for NewDeploymentForGroup schema.
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.24 to 1.36.28.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.24...v1.36.28)
* Bumps [github.com/google/uuid](https://github.com/google/uuid) from 1.1.4 to 1.1.5.
- [Release notes](https://github.com/google/uuid/releases)
- [Commits](https://github.com/google/uuid/compare/v1.1.4...v1.1.5)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.23 to 1.36.28.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.23...v1.36.28)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.28 to 1.37.1.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.28...v1.37.1)
* Bumps [github.com/google/uuid](https://github.com/google/uuid) from 1.1.5 to 1.2.0.
- [Release notes](https://github.com/google/uuid/releases)
- [Commits](https://github.com/google/uuid/compare/v1.1.5...v1.2.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...1.4.6)
* Bumps [github.com/google/uuid](https://github.com/google/uuid) from 1.1.5 to 1.2.0.
- [Release notes](https://github.com/google/uuid/releases)
- [Commits](https://github.com/google/uuid/compare/v1.1.5...v1.2.0)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.28 to 1.37.7.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.28...v1.37.7)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.1 to 1.37.10.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.1...v1.37.10)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.7 to 1.37.10.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.7...v1.37.10)
* Bumps alpine from 3.13.1 to 3.13.2.
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.10 to 1.37.20.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.10...v1.37.20)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.10 to 1.37.20.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.10...v1.37.20)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.20 to 1.37.25.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.20...v1.37.25)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.20 to 1.37.25.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.20...v1.37.25)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.1)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.25 to 1.37.30.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.25...v1.37.30)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.37.25 to 1.37.30.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/main/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.37.25...v1.37.30)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.1)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)

#### deviceauth (2.6.0)

New changes in deviceauth since 2.5.0:

* Enable support for using the service with Traefik.
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.8 to 8.4.10.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.8...v8.4.10)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps golang from 1.15.7-alpine3.12 to 1.15.8-alpine3.12.
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.10 to 8.5.0.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.10...v8.5.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.5.0 to 8.7.1.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.5.0...v8.7.1)

#### deviceconfig (1.0.0)

* First release of deviceconfig

#### deviceconnect (1.1.0)

New changes in deviceconnect since 1.0.0:

* New API end-points to trigger check-update and send-inventory on device
* New internal API end-points to trigger check-update and send-inventory
* , implement file upload and download end-points
([MEN-4418](https://tracker.mender.io/browse/MEN-4418), [MEN-4482](https://tracker.mender.io/browse/MEN-4482))
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...1.4.6)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)

#### gui (2.7.0)

New changes in gui since 2.6.0:

* Rename Retry deployment to Recreate deployment.
* fix page number on rowsPerPage change
([MEN-4364](https://tracker.mender.io/browse/MEN-4364))
* fixed an issue that prevented existing user roles from being removed
* fixed an issue that prevented loading dynamic group devices when navigating to device groups
* fixed an issue that prevented the deployment attempt count from being shown in the deployment report
([MEN-4399](https://tracker.mender.io/browse/MEN-4399))
* added single device configuration editor
* fixed onboarding tips dismissal not being saved right away
* switched auditlogs to drawer interaction for details
([MEN-4313](https://tracker.mender.io/browse/MEN-4313))
* onboarding: Pass `--demo` flag to `get.mender.io` script.
([MEN-4461](https://tracker.mender.io/browse/MEN-4461))
* extend RBAC with "Deployments Manager" role
* added user verification requirement for 2fa activation
([MEN-4484](https://tracker.mender.io/browse/MEN-4484))
* improved deployment creation for large device fleets
* fixed an error that prevented deployment timeframe selection
* prevented enter press on 2fa code entry causing a redirect
* Aggregated Dependabot Changelogs:
* Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.29.2 to 7.29.4.
- [Release notes](https://github.com/testing-library/dom-testing-library/releases)
- [Changelog](https://github.com/testing-library/dom-testing-library/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.29.2...v7.29.4)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.12.3 to 5.15.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.12.3...v5.15.0)
* Bumps [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) from 1.1.2 to 1.2.0.
- [Release notes](https://github.com/stripe/react-stripe-js/releases)
- [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/react-stripe-js/compare/v1.1.2...v1.2.0)
* Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.3.3 to 1.3.4.
- [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.3.3...v1.3.4)
* Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.3.1 to 1.4.0.
- [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
- [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
- [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.3.1...v1.4.0)
* Bumps [@cypress/skip-test](https://github.com/cypress-io/cypress-skip-test) from 2.5.1 to 2.6.0.
- [Release notes](https://github.com/cypress-io/cypress-skip-test/releases)
- [Commits](https://github.com/cypress-io/cypress-skip-test/compare/v2.5.1...v2.6.0)
* Bumps [generate-password](https://github.com/brendanashworth/generate-password) from 1.5.1 to 1.6.0.
- [Release notes](https://github.com/brendanashworth/generate-password/releases)
- [Changelog](https://github.com/brendanashworth/generate-password/blob/master/CHANGELOG.md)
- [Commits](https://github.com/brendanashworth/generate-password/commits)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.17.0 to 7.18.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.17.0...v7.18.0)
* Bumps [husky](https://github.com/typicode/husky) from 4.3.7 to 4.3.8.
- [Release notes](https://github.com/typicode/husky/releases)
- [Commits](https://github.com/typicode/husky/compare/v4.3.7...v4.3.8)
* Bumps [react-copy-to-clipboard](https://github.com/nkbt/react-copy-to-clipboard) from 5.0.2 to 5.0.3.
- [Release notes](https://github.com/nkbt/react-copy-to-clipboard/releases)
- [Commits](https://github.com/nkbt/react-copy-to-clipboard/compare/v5.0.2...v5.0.3)
* Bumps [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) from 5.11.8 to 5.11.9.
- [Release notes](https://github.com/testing-library/jest-dom/releases)
- [Changelog](https://github.com/testing-library/jest-dom/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/jest-dom/compare/v5.11.8...v5.11.9)
* Bumps [core-js](https://github.com/zloirock/core-js) from 3.8.2 to 3.8.3.
- [Release notes](https://github.com/zloirock/core-js/releases)
- [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/zloirock/core-js/compare/v3.8.2...v3.8.3)
* Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.5.1 to 4.5.2.
- [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
- [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.5.1...4.5.2)
* Bumps [@mdi/js](https://github.com/Templarian/MaterialDesign-JS) from 5.8.55 to 5.9.55.
- [Release notes](https://github.com/Templarian/MaterialDesign-JS/releases)
- [Commits](https://github.com/Templarian/MaterialDesign-JS/compare/v5.8.55...v5.9.55)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.15.0 to 5.17.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.15.0...v5.17.0)
* Bumps node from 15.5.1-alpine to 15.6.0-alpine.
* Bumps [dayjs](https://github.com/iamkun/dayjs) from 1.10.3 to 1.10.4.
- [Release notes](https://github.com/iamkun/dayjs/releases)
- [Changelog](https://github.com/iamkun/dayjs/blob/v1.10.4/CHANGELOG.md)
- [Commits](https://github.com/iamkun/dayjs/compare/v1.10.3...v1.10.4)
* Bumps [cypress](https://github.com/cypress-io/cypress) from 6.2.1 to 6.3.0.
- [Release notes](https://github.com/cypress-io/cypress/releases)
- [Changelog](https://github.com/cypress-io/cypress/blob/develop/.releaserc.base.js)
- [Commits](https://github.com/cypress-io/cypress/compare/v6.2.1...v6.3.0)
* Bumps [cypress-image-snapshot](https://github.com/palmerhq/cypress-image-snapshot) from 4.0.0 to 4.0.1.
- [Release notes](https://github.com/palmerhq/cypress-image-snapshot/releases)
- [Changelog](https://github.com/jaredpalmer/cypress-image-snapshot/blob/master/CHANGELOG.md)
- [Commits](https://github.com/palmerhq/cypress-image-snapshot/compare/v4.0.0...v4.0.1)
* Bumps cypress/included from 6.2.1 to 6.3.0.
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.2.1 to 10.2.3.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/10.2.1...10.2.3)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 12.6.0 to 12.6.2.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v12.6.0...v12.6.2)
* Bumps [cypress-file-upload](https://github.com/abramenal/cypress-file-upload) from 4.1.1 to 5.0.2.
- [Release notes](https://github.com/abramenal/cypress-file-upload/releases)
- [Commits](https://github.com/abramenal/cypress-file-upload/compare/v4.1.1...v5.0.2)
* Bumps [webpack-cli](https://github.com/webpack/webpack-cli) from 4.3.1 to 4.4.0.
- [Release notes](https://github.com/webpack/webpack-cli/releases)
- [Changelog](https://github.com/webpack/webpack-cli/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack/webpack-cli/compare/webpack-cli@4.3.1...webpack-cli@4.4.0)
* Bumps [postcss-loader](https://github.com/webpack-contrib/postcss-loader) from 4.1.0 to 4.2.0.
- [Release notes](https://github.com/webpack-contrib/postcss-loader/releases)
- [Changelog](https://github.com/webpack-contrib/postcss-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/postcss-loader/compare/v4.1.0...v4.2.0)
* Bumps node from 15.6.0-alpine to 15.7.0-alpine.
* Bumps [eslint](https://github.com/eslint/eslint) from 7.18.0 to 7.19.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.18.0...v7.19.0)
* Bumps [less](https://github.com/less/less.js) from 4.1.0 to 4.1.1.
- [Release notes](https://github.com/less/less.js/releases)
- [Changelog](https://github.com/less/less.js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/less/less.js/compare/v4.1.0...v4.1.1)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.17.0 to 5.19.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.17.0...v5.19.0)
* Bumps [xterm-addon-search](https://github.com/xtermjs/xterm.js) from 0.7.0 to 0.8.0.
- [Release notes](https://github.com/xtermjs/xterm.js/releases)
- [Commits](https://github.com/xtermjs/xterm.js/compare/0.7...0.8)
* Bumps [react-big-calendar](https://github.com/jquense/react-big-calendar) from 0.30.0 to 0.31.0.
- [Release notes](https://github.com/jquense/react-big-calendar/releases)
- [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jquense/react-big-calendar/compare/v0.30.0...v0.31.0)
* Bumps [xterm-addon-fit](https://github.com/xtermjs/xterm.js) from 0.4.0 to 0.5.0.
- [Release notes](https://github.com/xtermjs/xterm.js/releases)
- [Commits](https://github.com/xtermjs/xterm.js/compare/0.4...0.5)
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.2.3 to 10.2.4.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/10.2.3...10.2.4)
* Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.3.4 to 1.3.5.
- [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.3.4...v1.3.5)
* Bumps [@stripe/react-stripe-js](https://github.com/stripe/react-stripe-js) from 1.2.0 to 1.2.1.
- [Release notes](https://github.com/stripe/react-stripe-js/releases)
- [Changelog](https://github.com/stripe/react-stripe-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/react-stripe-js/compare/v1.2.0...v1.2.1)
* Bumps [msw](https://github.com/mswjs/msw) from 0.25.0 to 0.26.0.
- [Release notes](https://github.com/mswjs/msw/releases)
- [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mswjs/msw/compare/v0.25.0...v0.26.0)
* Bumps [victory](https://github.com/formidablelabs/victory) from 35.4.6 to 35.4.8.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v35.4.6...v35.4.8)
* Bumps [msw](https://github.com/mswjs/msw) from 0.26.0 to 0.26.1.
- [Release notes](https://github.com/mswjs/msw/releases)
- [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mswjs/msw/compare/v0.26.0...v0.26.1)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 12.6.3 to 12.7.0.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v12.6.3...v12.7.0)
* Bumps [msgpack5](https://github.com/mcollina/msgpack5) from 5.0.0 to 5.1.0.
- [Release notes](https://github.com/mcollina/msgpack5/releases)
- [Commits](https://github.com/mcollina/msgpack5/compare/v5.0.0...v5.1.0)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.19.0 to 7.20.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.19.0...v7.20.0)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.12.13 to 7.12.16.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.16/packages/babel-core)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.12.13 to 7.12.16.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.16/packages/babel-preset-env)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 12.7.0 to 12.7.1.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v12.7.0...v12.7.1)
* Bumps [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) from 5.0.0 to 5.1.0.
- [Release notes](https://github.com/jantimon/html-webpack-plugin/releases)
- [Changelog](https://github.com/jantimon/html-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jantimon/html-webpack-plugin/compare/v5.0.0...v5.1.0)
* Bumps [react-big-calendar](https://github.com/jquense/react-big-calendar) from 0.31.0 to 0.32.0.
- [Release notes](https://github.com/jquense/react-big-calendar/releases)
- [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jquense/react-big-calendar/compare/v0.31.0...v0.32.0)
* Bumps [victory](https://github.com/formidablelabs/victory) from 35.4.8 to 35.4.9.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v35.4.8...v35.4.9)
* Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.9.1 to 2.9.2.
- [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
- [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.9.1...v2.9.2)
* Bumps cypress/included from 6.4.0 to 6.5.0.
* Bumps [@babel/plugin-transform-runtime](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-transform-runtime) from 7.12.15 to 7.13.9.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.9/packages/babel-plugin-transform-runtime)
* Bumps [@stripe/stripe-js](https://github.com/stripe/stripe-js) from 1.12.1 to 1.13.1.
- [Release notes](https://github.com/stripe/stripe-js/releases)
- [Commits](https://github.com/stripe/stripe-js/compare/v1.12.1...v1.13.1)
* Bumps [elliptic](https://github.com/indutny/elliptic) from 6.5.3 to 6.5.4.
- [Release notes](https://github.com/indutny/elliptic/releases)
- [Commits](https://github.com/indutny/elliptic/compare/v6.5.3...v6.5.4)
* Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.5.5 to 4.5.6.
- [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
- [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.5.5...4.5.6)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.21.0 to 7.22.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.21.0...v7.22.0)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 12.8.1 to 12.8.3.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v12.8.1...v12.8.3)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.24.3 to 5.25.1.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.24.3...v5.25.1)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.13.9 to 7.13.10.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.10/packages/babel-preset-env)
* Bumps nginx from 1.19.7-alpine to 1.19.8-alpine.
* Bumps [@material-ui/pickers](https://github.com/mui-org/material-ui-pickers) from 3.2.10 to 3.3.10.
- [Release notes](https://github.com/mui-org/material-ui-pickers/releases)
- [Changelog](https://github.com/mui-org/material-ui-pickers/blob/next/CHANGELOG.md)
- [Commits](https://github.com/mui-org/material-ui-pickers/compare/v3.2.10...v3.3.10)
* Bumps [msw](https://github.com/mswjs/msw) from 0.27.0 to 0.27.1.
- [Release notes](https://github.com/mswjs/msw/releases)
- [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mswjs/msw/compare/v0.27.0...v0.27.1)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.13.8 to 7.13.10.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.10/packages/babel-core)
* Bumps [postcss](https://github.com/postcss/postcss) from 8.2.7 to 8.2.8.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.2.7...8.2.8)
* Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.9.2 to 2.10.0.
- [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
- [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.9.2...v2.10.0)
* Bumps [@babel/plugin-transform-runtime](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-transform-runtime) from 7.13.9 to 7.13.10.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.10/packages/babel-plugin-transform-runtime)
* Bumps [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) from 5.3.0 to 5.3.1.
- [Release notes](https://github.com/jantimon/html-webpack-plugin/releases)
- [Changelog](https://github.com/jantimon/html-webpack-plugin/blob/main/CHANGELOG.md)
- [Commits](https://github.com/jantimon/html-webpack-plugin/compare/v5.3.0...v5.3.1)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.25.1 to 5.26.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.25.1...v5.26.0)
* Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.1.1 to 5.1.3.
- [Release notes](https://github.com/webpack-contrib/css-loader/releases)
- [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.1.1...v5.1.3)
* Bumps [jest](https://github.com/facebook/jest) from 27.0.0-next.4 to 27.0.0-next.5.
- [Release notes](https://github.com/facebook/jest/releases)
- [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
- [Commits](https://github.com/facebook/jest/compare/v27.0.0-next.4...v27.0.0-next.5)
* Bumps [xterm](https://github.com/xtermjs/xterm.js) from 4.10.0 to 4.11.0.
- [Release notes](https://github.com/xtermjs/xterm.js/releases)
- [Commits](https://github.com/xtermjs/xterm.js/compare/4.10.0...4.11.0)
* Bumps [postcss-loader](https://github.com/webpack-contrib/postcss-loader) from 5.1.0 to 5.2.0.
- [Release notes](https://github.com/webpack-contrib/postcss-loader/releases)
- [Changelog](https://github.com/webpack-contrib/postcss-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/postcss-loader/compare/v5.1.0...v5.2.0)
* Bumps [victory](https://github.com/formidablelabs/victory) from 35.4.11 to 35.4.12.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v35.4.11...v35.4.12)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 12.8.3 to 13.0.6.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v12.8.3...v13.0.6)
* Bumps [husky](https://github.com/typicode/husky) from 5.1.3 to 5.2.0.
- [Release notes](https://github.com/typicode/husky/releases)
- [Commits](https://github.com/typicode/husky/compare/v5.1.3...v5.2.0)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.26.0 to 5.27.1.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.26.0...v5.27.1)
* Bumps node from 15.11.0-alpine to 15.12.0-alpine.
* Bumps [cypress-file-upload](https://github.com/abramenal/cypress-file-upload) from 5.0.2 to 5.0.3.
- [Release notes](https://github.com/abramenal/cypress-file-upload/releases)
- [Commits](https://github.com/abramenal/cypress-file-upload/compare/v5.0.2...v5.0.3)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 13.0.6 to 13.0.7.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v13.0.6...v13.0.7)
* Bumps [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) from 5.11.9 to 5.11.10.
- [Release notes](https://github.com/testing-library/jest-dom/releases)
- [Changelog](https://github.com/testing-library/jest-dom/blob/main/CHANGELOG.md)
- [Commits](https://github.com/testing-library/jest-dom/compare/v5.11.9...v5.11.10)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.13.10 to 7.13.12.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.12/packages/babel-preset-env)
* Bumps [esbuild-loader](https://github.com/privatenumber/esbuild-loader) from 2.10.0 to 2.11.0.
- [Release notes](https://github.com/privatenumber/esbuild-loader/releases)
- [Commits](https://github.com/privatenumber/esbuild-loader/compare/v2.10.0...v2.11.0)
* Bumps [msw](https://github.com/mswjs/msw) from 0.27.1 to 0.28.0.
- [Release notes](https://github.com/mswjs/msw/releases)
- [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mswjs/msw/compare/v0.27.1...v0.28.0)
* Bumps [msgpack5](https://github.com/mcollina/msgpack5) from 5.3.1 to 5.3.2.
- [Release notes](https://github.com/mcollina/msgpack5/releases)
- [Commits](https://github.com/mcollina/msgpack5/compare/v5.3.1...v5.3.2)
* Bumps [react-redux](https://github.com/reduxjs/react-redux) from 7.2.2 to 7.2.3.
- [Release notes](https://github.com/reduxjs/react-redux/releases)
- [Changelog](https://github.com/reduxjs/react-redux/blob/master/CHANGELOG.md)
- [Commits](https://github.com/reduxjs/react-redux/compare/v7.2.2...v7.2.3)
* Bumps [webpack-cli](https://github.com/webpack/webpack-cli) from 4.5.0 to 4.6.0.
- [Release notes](https://github.com/webpack/webpack-cli/releases)
- [Changelog](https://github.com/webpack/webpack-cli/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack/webpack-cli/compare/webpack-cli@4.5.0...webpack-cli@4.6.0)
* Bumps [@testing-library/user-event](https://github.com/testing-library/user-event) from 13.0.7 to 13.0.16.
- [Release notes](https://github.com/testing-library/user-event/releases)
- [Changelog](https://github.com/testing-library/user-event/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/user-event/compare/v13.0.7...v13.0.16)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.22.0 to 7.23.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.22.0...v7.23.0)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.13.10 to 7.13.13.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.13/packages/babel-core)
* Bumps [@stripe/stripe-js](https://github.com/stripe/stripe-js) from 1.13.1 to 1.13.2.
- [Release notes](https://github.com/stripe/stripe-js/releases)
- [Commits](https://github.com/stripe/stripe-js/compare/v1.13.1...v1.13.2)
* Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.3.9 to 1.4.0.
- [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.3.9...v1.4.0)
* Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.22.0 to 7.23.1.
- [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
- [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.22.0...v7.23.1)
* Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.30.0 to 7.30.1.
- [Release notes](https://github.com/testing-library/dom-testing-library/releases)
- [Changelog](https://github.com/testing-library/dom-testing-library/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.30.0...v7.30.1)
* Bumps [react-dropzone](https://github.com/react-dropzone/react-dropzone) from 11.3.1 to 11.3.2.
- [Release notes](https://github.com/react-dropzone/react-dropzone/releases)
- [Commits](https://github.com/react-dropzone/react-dropzone/compare/v11.3.1...v11.3.2)
* Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.1.3 to 5.2.0.
- [Release notes](https://github.com/webpack-contrib/css-loader/releases)
- [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.1.3...v5.2.0)
* Bumps [husky](https://github.com/typicode/husky) from 5.2.0 to 6.0.0.
- [Release notes](https://github.com/typicode/husky/releases)
- [Commits](https://github.com/typicode/husky/compare/v5.2.0...v6.0.0)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.27.1 to 5.28.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.27.1...v5.28.0)
* Bumps [@babel/preset-react](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-react) from 7.12.13 to 7.13.13.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.13/packages/babel-preset-react)
* Bumps [y18n](https://github.com/yargs/y18n) from 3.2.1 to 3.2.2.
- [Release notes](https://github.com/yargs/y18n/releases)
- [Changelog](https://github.com/yargs/y18n/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yargs/y18n/commits)
* Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.30.1 to 7.30.3.
- [Release notes](https://github.com/testing-library/dom-testing-library/releases)
- [Changelog](https://github.com/testing-library/dom-testing-library/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.30.1...v7.30.3)
* Bumps [postcss](https://github.com/postcss/postcss) from 8.2.8 to 8.2.9.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.2.8...8.2.9)
* Bumps [victory](https://github.com/formidablelabs/victory) from 35.4.12 to 35.4.13.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v35.4.12...v35.4.13)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.28.0 to 5.30.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.28.0...v5.30.0)
* Bumps [core-js](https://github.com/zloirock/core-js/tree/HEAD/packages/core-js) from 3.9.1 to 3.10.0.
- [Release notes](https://github.com/zloirock/core-js/releases)
- [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/zloirock/core-js/commits/v3.10.0/packages/core-js)
* Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.4.1 to 1.4.2.
- [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
- [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
- [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.4.1...v1.4.2)
* Bumps node from 15.12.0-alpine to 15.13.0-alpine.
* Bumps nginx from 1.19.8-alpine to 1.19.9-alpine.
* Bumps [jest-watch-typeahead](https://github.com/jest-community/jest-watch-typeahead) from 0.6.1 to 0.6.2.
- [Release notes](https://github.com/jest-community/jest-watch-typeahead/releases)
- [Changelog](https://github.com/jest-community/jest-watch-typeahead/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jest-community/jest-watch-typeahead/compare/v0.6.1...v0.6.2)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.13.13 to 7.13.14.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.13.14/packages/babel-core)
* Bumps [@testing-library/react](https://github.com/testing-library/react-testing-library) from 11.2.5 to 11.2.6.
- [Release notes](https://github.com/testing-library/react-testing-library/releases)
- [Changelog](https://github.com/testing-library/react-testing-library/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/react-testing-library/compare/v11.2.5...v11.2.6)
* Bumps [mzedel-cypress-image-snapshot](https://github.com/mzedel/cypress-image-snapshot) from 4.0.3 to 4.0.5.
- [Release notes](https://github.com/mzedel/cypress-image-snapshot/releases)
- [Changelog](https://github.com/mzedel/cypress-image-snapshot/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mzedel/cypress-image-snapshot/compare/v4.0.3...v4.0.5)
* Bumps [cypress](https://github.com/cypress-io/cypress) from 6.8.0 to 6.9.1.
- [Release notes](https://github.com/cypress-io/cypress/releases)
- [Changelog](https://github.com/cypress-io/cypress/blob/develop/.releaserc.base.js)
- [Commits](https://github.com/cypress-io/cypress/commits)
* Bumps [msw](https://github.com/mswjs/msw) from 0.28.0 to 0.28.1.
- [Release notes](https://github.com/mswjs/msw/releases)
- [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mswjs/msw/compare/v0.28.0...v0.28.1)

#### integration (2.7.0)

New changes in integration since 2.6.0:

* demo script, include docker-compose.connect.yml by default
([MEN-4357](https://tracker.mender.io/browse/MEN-4357))
* Add auditlogs and deviceconnect to production templates
* migrated gateway service to use traefik
* production template: configure mender-api-gateway as a storage proxy
* Include the configuration add-on in the demo script
* Remove nginx-based api-gateway and replace with Traefik.
* fix auth verification on useradm APIs
([MEN-4623](https://tracker.mender.io/browse/MEN-4623))
* Upgrade auditlogs to 1.1.0.
* Upgrade create-artifact-worker to 1.0.2.
* Upgrade deployments to 2.3.0.
* Upgrade deployments-enterprise to 2.3.0.
* Upgrade deviceauth to 2.6.0.
* Add deviceconfig 1.0.0.
* Upgrade deviceconnect to 1.1.0.
* Upgrade gui to 2.7.0.
* Upgrade integration to 2.7.0.
* Upgrade inventory to 2.3.0.
* Upgrade inventory-enterprise to 2.3.0.
* Upgrade mender to 2.6.0.
* Upgrade mender-artifact to 3.5.1.
* Upgrade mender-cli to 1.7.0.
* Upgrade mender-connect to 1.1.0.
* Upgrade tenantadm to 3.1.0.
* Upgrade useradm to 1.14.0.
* Upgrade useradm-enterprise to 1.14.0.
* Upgrade workflows to 1.4.0.
* Upgrade workflows-enterprise to 1.4.0.
* Aggregated Dependabot Changelogs:
* Bumps [docker-compose](https://github.com/docker/compose) from 1.27.4 to 1.28.0.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.28.0/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.27.4...1.28.0)
* Bumps [fabric](http://fabfile.org) from 2.5.0 to 2.6.0.
* Bumps [docker-compose](https://github.com/docker/compose) from 1.28.0 to 1.28.2.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.28.2/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.28.0...1.28.2)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.1 to 6.2.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.2.1...6.2.2)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.1 to 6.2.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.2.1...6.2.2)
* Bumps [pyotp](https://github.com/pyotp/pyotp) from 2.4.1 to 2.5.1.
- [Release notes](https://github.com/pyotp/pyotp/releases)
- [Changelog](https://github.com/pyauth/pyotp/blob/develop/Changes.rst)
- [Commits](https://github.com/pyotp/pyotp/compare/v2.4.1...v2.5.1)
* Bumps [pyotp](https://github.com/pyotp/pyotp) from 2.5.1 to 2.6.0.
- [Release notes](https://github.com/pyotp/pyotp/releases)
- [Changelog](https://github.com/pyauth/pyotp/blob/develop/Changes.rst)
- [Commits](https://github.com/pyotp/pyotp/compare/v2.5.1...v2.6.0)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.55.1 to 2.55.2.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.55.1...v2.55.2)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.2 to 3.11.3.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/3.11.3/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.2...3.11.3)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.2 to 3.11.3.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/3.11.3/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.2...3.11.3)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.3.1 to 3.4.4.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.3.1...3.4.4)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.3.2 to 3.4.4.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.3.2...3.4.4)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.3.2 to 3.4.4.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.3.2...3.4.4)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.4 to 3.4.5.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.4.4...3.4.5)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.4 to 3.4.5.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.4.4...3.4.5)
* Bumps python from 3.9.1 to 3.9.2.
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.5 to 3.4.6.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.4.5...3.4.6)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.28.2 to 1.28.4.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.28.4/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.28.2...1.28.4)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.4.5 to 3.4.6.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/main/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.4.5...3.4.6)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.55.2 to 2.56.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.55.2...v2.56.0)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.28.4 to 1.28.5.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.28.5/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.28.4...1.28.5)
* Bumps [pillow](https://github.com/python-pillow/Pillow) from 8.1.0 to 8.1.2.
- [Release notes](https://github.com/python-pillow/Pillow/releases)
- [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
- [Commits](https://github.com/python-pillow/Pillow/compare/8.1.0...8.1.2)
* Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.3 to 1.26.4.
- [Release notes](https://github.com/urllib3/urllib3/releases)
- [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
- [Commits](https://github.com/urllib3/urllib3/compare/1.26.3...1.26.4)
* Bumps [urllib3](https://github.com/urllib3/urllib3) from 1.26.2 to 1.26.4.
- [Release notes](https://github.com/urllib3/urllib3/releases)
- [Changelog](https://github.com/urllib3/urllib3/blob/main/CHANGES.rst)
- [Commits](https://github.com/urllib3/urllib3/compare/1.26.2...1.26.4)
* Bumps [contextlib2](https://github.com/jazzband/contextlib2) from 0.6.0 to 0.6.0.post1.
- [Release notes](https://github.com/jazzband/contextlib2/releases)
- [Commits](https://github.com/jazzband/contextlib2/compare/v0.6.0...v0.6.0.post1)

#### inventory (2.3.0)

New changes in inventory since 2.2.0:

* Support returning a subset of attributes in filters/search
* docs: deprecate DELETE /devices/{id} management endpoint
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps golang from 1.15.7-alpine3.12 to 1.15.8-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...v1.5.0)

#### inventory-enterprise (2.3.0)

New changes in inventory-enterprise since 2.2.0:

* Support returning a subset of attributes in filters/search
* docs: deprecate DELETE /devices/{id} management endpoint
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.8 to 8.4.10.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.8...v8.4.10)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps golang from 1.15.7-alpine3.12 to 1.15.8-alpine3.12.
* Bumps alpine from 3.13.1 to 3.13.2.
* Bumps golang from 1.15.7-alpine3.12 to 1.16.0-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.10 to 8.7.1.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.10...v8.7.1)
* Bumps golang from 1.16.0-alpine3.12 to 1.16.2-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...v1.5.0)

#### tenantadm (3.1.0)

New changes in tenantadm since 3.0.0:

* Return Add-ons in GET user/tenant
([MEN-4306](https://tracker.mender.io/browse/MEN-4306))
* internal api: PUT /tenant/:id accepts addons
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps golang from 1.15.7-alpine3.12 to 1.15.8-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps golang from 1.15.8-alpine3.12 to 1.16.0-alpine3.12.
* Bumps alpine from 3.13.1 to 3.13.2.
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.0.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.8.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.8.0...v1.8.1)
* Bumps golang from 1.16.0-alpine3.12 to 1.16.2-alpine3.12.

#### useradm (1.14.0)

New changes in useradm since 1.13.0:

* use traefik's X-Forwarded-* headers
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps alpine from 3.13.1 to 3.13.2.
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.0.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.0)
* Bumps golang from 1.15.7-alpine3.12 to 1.16.2-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.8.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.8.0...v1.8.1)

#### useradm-enterprise (1.14.0)

New changes in useradm-enterprise since 1.13.0:

* use traefik's X-Forwarded-* headers
* New endpoints for email verification.
Introduce new endpoints that enable email verification.
The first endpoint starts the email verification procedure.
As a part of this procedure, we are sending a verification email to the user.
The verification email contains a link for email verification.
The second endpoint can be used to finalize email verification.
Only users with a verified email address have access to two factor
authentication settings.
* rbac: extend observer role by adding access to device configuration
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.8 to 8.4.10.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.8...v8.4.10)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps golang from 1.14-alpine3.12 to 1.15.7-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.10 to 8.4.11.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.10...v8.4.11)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps alpine from 3.13.1 to 3.13.2.
* Bumps golang from 1.15.7-alpine3.12 to 1.16.0-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps alpine from 3.13.1 to 3.13.2.
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.0.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.0)
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.11 to 8.7.1.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.11...v8.7.1)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.7.0 to 1.8.0.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.7.0...v1.8.0)
* Bumps golang from 1.15.7-alpine3.12 to 1.16.2-alpine3.12.
* Bumps golang from 1.16.0-alpine3.12 to 1.16.2-alpine3.12.
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.8.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.8.0...v1.8.1)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.6 to 1.5.0.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/1.4.6...v1.5.0)
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.8.0 to 1.8.1.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.8.0...v1.8.1)

#### workflows (1.4.0)

New changes in workflows since 1.3.0:

* Update workflow definitions for
provisioning/decomissioning devices in deviceconfig service
([MEN-4383](https://tracker.mender.io/browse/MEN-4383), [MEN-4429](https://tracker.mender.io/browse/MEN-4429))
* New workflow deploy_device_configuration
([MEN-4383](https://tracker.mender.io/browse/MEN-4383), [MEN-4429](https://tracker.mender.io/browse/MEN-4429))
* Configuration deployment triggers device update check
([MEN-4383](https://tracker.mender.io/browse/MEN-4383), [MEN-4429](https://tracker.mender.io/browse/MEN-4429))
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)

#### workflows-enterprise (1.4.0)

New changes in workflows-enterprise since 1.3.0:

* Update workflow definitions for
provisioning/decomissioning devices in deviceconfig service
([MEN-4383](https://tracker.mender.io/browse/MEN-4383), [MEN-4429](https://tracker.mender.io/browse/MEN-4429))
* New workflow deploy_device_configuration
([MEN-4383](https://tracker.mender.io/browse/MEN-4383), [MEN-4429](https://tracker.mender.io/browse/MEN-4429))
* Configuration deployment triggers device update check
([MEN-4383](https://tracker.mender.io/browse/MEN-4383), [MEN-4429](https://tracker.mender.io/browse/MEN-4429))
* Fix password reset button text
* Add workflow for sending password verification email
* New workflow contact_support for handling inbound email
requests to Mender support
* New workflow clear_tenant_tokens for puriging tenant JWTs
* Aggregated Dependabot Changelogs:
* Bumps alpine from 3.12 to 3.13.0.
* Bumps alpine from 3.12 to 3.13.0.
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.4 to 1.4.5.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.4...v1.4.5)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.5 to 1.4.6.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.5...1.4.6)
* Bumps alpine from 3.13.0 to 3.13.1.
* Bumps alpine from 3.13.1 to 3.13.2.

## Mender 2.6.1

_Released 16.04.2021_

### Changelogs

#### create-artifact-worker (1.0.2)

New changes in create-artifact-worker since 1.0.1:

* bugfix to allow spaces in artifact names
([MEN-4179](https://tracker.mender.io/browse/MEN-4179))
* upgrade mender-artifact to version 3.5.0.
This enables the create-artifact-worker to generate artifacts that
implement the provides and clear provides fields.
([MEN-4409](https://tracker.mender.io/browse/MEN-4409))

#### deployments-enterprise (2.2.1)

New changes in deployments-enterprise since 2.2.0:

* FIX: Phased deployments getting stuck on retries

#### integration (2.6.1)

New changes in integration since 2.6.0:

* Upgrade create-artifact-worker to 1.0.2.
* Upgrade deployments to 2.2.1.
* Upgrade deployments-enterprise to 2.2.1.
* Upgrade inventory to 2.2.1.
* Upgrade inventory-enterprise to 2.2.1.
* Upgrade mender to 2.5.1.
* Upgrade mender-artifact to 3.5.1.
* Upgrade mender-cli to 1.6.1.
* Upgrade mender-connect to 1.0.1.
## Mender 2.6.0

_Released 01.20.2021_

### Changelogs

#### auditlogs (1.0.0)

* First release of auditlogs

#### deployments (2.2.0)

New changes in deployments since 2.1.0:

* Vendor mender-artifact with `clears_artifact_provides` support.
([MEN-3480](https://tracker.mender.io/browse/MEN-3480))
* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* include clears_artifact_provides in Artifact objects
([MEN-4050](https://tracker.mender.io/browse/MEN-4050))
* add the possibility of creating deployments for all accepted devices
* Aggregated Dependabot Changelogs:
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.8 to 1.35.33.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.8...v1.35.33)
* Bump github.com/aws/aws-sdk-go from 1.35.8 to 1.35.33
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.33 to 1.36.2.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.33...v1.36.2)
* Bump github.com/aws/aws-sdk-go from 1.35.33 to 1.36.2
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.2 to 1.36.7.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.2...v1.36.7)
* Bump github.com/aws/aws-sdk-go from 1.36.2 to 1.36.7
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.7 to 1.36.12.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.7...v1.36.12)
* Bump github.com/aws/aws-sdk-go from 1.36.7 to 1.36.12
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.12 to 1.36.15.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.12...v1.36.15)
* Bump github.com/aws/aws-sdk-go from 1.36.12 to 1.36.15
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.15 to 1.36.23.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.15...v1.36.23)
* Bump github.com/aws/aws-sdk-go from 1.36.15 to 1.36.23

#### deployments-enterprise (2.2.0)

New changes in deployments-enterprise since 2.1.0:

* Vendor mender-artifact with `clears_artifact_provides` support.
([MEN-3480](https://tracker.mender.io/browse/MEN-3480))
* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* include clears_artifact_provides in Artifact objects
([MEN-4050](https://tracker.mender.io/browse/MEN-4050))
* include clears_artifact_provides in Artifact objects
([MEN-4050](https://tracker.mender.io/browse/MEN-4050))
* add the possibility of creating deployments for all accepted devices
* Aggregated Dependabot Changelogs:
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.8 to 1.35.33.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.8...v1.35.33)
* Bump github.com/aws/aws-sdk-go from 1.35.8 to 1.35.33
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.33 to 1.35.35.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.33...v1.35.35)
* Bump github.com/aws/aws-sdk-go from 1.35.33 to 1.35.35
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.8 to 1.35.33.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.8...v1.35.33)
* Bump github.com/aws/aws-sdk-go from 1.35.8 to 1.35.33
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.33 to 1.36.2.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.33...v1.36.2)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.35.35 to 1.36.2.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.35.35...v1.36.2)
* Bump github.com/aws/aws-sdk-go from 1.35.35 to 1.36.2
* Bump github.com/aws/aws-sdk-go from 1.35.33 to 1.36.2
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.2 to 1.36.7.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.2...v1.36.7)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.2 to 1.36.7.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.2...v1.36.7)
* Bump github.com/aws/aws-sdk-go from 1.36.2 to 1.36.7
* Bump github.com/aws/aws-sdk-go from 1.36.2 to 1.36.7
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.7 to 1.36.12.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.7...v1.36.12)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.7 to 1.36.12.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.7...v1.36.12)
* Bump github.com/aws/aws-sdk-go from 1.36.7 to 1.36.12
* Bump github.com/aws/aws-sdk-go from 1.36.7 to 1.36.12
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.12 to 1.36.15.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.12...v1.36.15)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.12 to 1.36.15.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.12...v1.36.15)
* Bump github.com/aws/aws-sdk-go from 1.36.12 to 1.36.15
* Bump github.com/aws/aws-sdk-go from 1.36.12 to 1.36.15
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.15 to 1.36.23.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.15...v1.36.23)
* Bumps [github.com/aws/aws-sdk-go](https://github.com/aws/aws-sdk-go) from 1.36.15 to 1.36.23.
- [Release notes](https://github.com/aws/aws-sdk-go/releases)
- [Changelog](https://github.com/aws/aws-sdk-go/blob/master/CHANGELOG.md)
- [Commits](https://github.com/aws/aws-sdk-go/compare/v1.36.15...v1.36.23)
* Bump github.com/aws/aws-sdk-go from 1.36.15 to 1.36.23
* Bump github.com/aws/aws-sdk-go from 1.36.15 to 1.36.23

#### deviceauth (2.5.0)

New changes in deviceauth since 2.4.0:

* New query parameter id for GET /api/management/v1/devices
* add internal end-point to retrieve the count of devices
([MEN-3923](https://tracker.mender.io/browse/MEN-3923))
* New command for warning tenants approaching their device limit
* propagate device identity using workflows
([MEN-3979](https://tracker.mender.io/browse/MEN-3979))
* ignore tenant claim in single tenant setup
([MEN-3972](https://tracker.mender.io/browse/MEN-3972))
* New device auth query endpoint POST /api/management/v2/devauth/devices/search
* Aggregated Dependabot Changelogs:
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.3.1 to 8.4.2.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.3.1...v8.4.2)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4
* Bump github.com/go-redis/redis/v8 from 8.3.1 to 8.4.2
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.2 to 8.4.4.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.2...v8.4.4)
* Bump github.com/go-redis/redis/v8 from 8.4.2 to 8.4.4
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.4 to 8.4.8.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.4...v8.4.8)
* Bump github.com/go-redis/redis/v8 from 8.4.4 to 8.4.8

#### deviceconnect (1.0.0)

* First release of deviceconnect

#### gui (2.6.0)

New changes in gui since 2.5.0:

* added additional password validation to prevent email reuse
([MEN-3948](https://tracker.mender.io/browse/MEN-3948))
* added security measures to prevent clickjacking
* isolated single authset handling to prevent confusing authstate notifications
([MEN-3988](https://tracker.mender.io/browse/MEN-3988))
* implemented auditloglist to reflect user & deployment changes
* fixed a navigation issue that prevented deployment report navigation
* fixed an error caused by showing timeframe selection for a longer time
* removed sorting limitations for device id column
([MEN-3879](https://tracker.mender.io/browse/MEN-3879))
* disabled sorting for status column in devices list
([MEN-3969](https://tracker.mender.io/browse/MEN-3969))
* allowed setting equality filters through url to ease navigation
([MEN-3991](https://tracker.mender.io/browse/MEN-3991))
* fixed an issue that prevented admin access to user management settings
* added possibility to update credit card in organization settings
([MEN-3823](https://tracker.mender.io/browse/MEN-3823))
* fixed an issue that lead certain update module configurations to crash the app
* switched device attributes from local deducation to backend retrieval
* Update "Connect a device" onboarding dialog
([MEN-3999](https://tracker.mender.io/browse/MEN-3999))
* device remote shell/terminal
([MEN-4091](https://tracker.mender.io/browse/MEN-4091))
* fixed an error that prevented phased dynamic deployments + scheduled single device deployments
([MEN-4122](https://tracker.mender.io/browse/MEN-4122))
* fixed deployment creation not using single devices as deployment name
([MEN-4182](https://tracker.mender.io/browse/MEN-4182))
* fixed an issue that prevented deployment device count from being shown in single device deployments
* ensured settings show also after stripe initialization
([MEN-4275](https://tracker.mender.io/browse/MEN-4275))
* fixed cookie paths to work with ui redirect to subpath
* Rename Retry deployment to Recreate deployment.
* fix page number on rowsPerPage change
([MEN-4364](https://tracker.mender.io/browse/MEN-4364))
* fixed an issue that prevented existing user roles from being removed
* fixed an issue that prevented loading dynamic group devices when navigating to device groups
* Aggregated Dependabot Changelogs:
* Bumps [file-loader](https://github.com/webpack-contrib/file-loader) from 6.0.0 to 6.1.0.
- [Release notes](https://github.com/webpack-contrib/file-loader/releases)
- [Changelog](https://github.com/webpack-contrib/file-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/file-loader/compare/v6.0.0...v6.1.0)
* Bumps [less](https://github.com/less/less.js) from 3.11.3 to 3.12.2.
- [Release notes](https://github.com/less/less.js/releases)
- [Changelog](https://github.com/less/less.js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/less/less.js/commits)
* Bumps [copy-webpack-plugin](https://github.com/webpack-contrib/copy-webpack-plugin) from 6.0.3 to 6.1.0.
- [Release notes](https://github.com/webpack-contrib/copy-webpack-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/copy-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/copy-webpack-plugin/compare/v6.0.3...v6.1.0)
* Bump file-loader from 6.0.0 to 6.1.0
* Bump less from 3.11.3 to 3.12.2
* Bump copy-webpack-plugin from 6.0.3 to 6.1.0
* Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 6.1.1 to 7.0.1.
- [Release notes](https://github.com/webpack-contrib/less-loader/releases)
- [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/less-loader/compare/v6.1.1...v7.0.1)
* Bump less-loader from 6.1.1 to 7.0.1
* Bumps node from 14.9.0-alpine to 14.10.1-alpine.
* Bumps [lint-staged](https://github.com/okonet/lint-staged) from 10.2.11 to 10.3.0.
- [Release notes](https://github.com/okonet/lint-staged/releases)
- [Commits](https://github.com/okonet/lint-staged/compare/v10.2.11...v10.3.0)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.10.2 to 7.11.6.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.11.6/packages/babel-core)
* Bump @babel/core from 7.10.2 to 7.11.6
* Bump lint-staged from 10.2.11 to 10.3.0
* Bump node from 14.9.0-alpine to 14.10.1-alpine
* Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.20.1 to 7.20.6.
- [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
- [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.20.1...v7.20.6)
* Bumps [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) from 4.3.0 to 4.4.1.
- [Release notes](https://github.com/jantimon/html-webpack-plugin/releases)
- [Changelog](https://github.com/jantimon/html-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jantimon/html-webpack-plugin/compare/v4.3.0...v4.4.1)
* Bumps [copy-webpack-plugin](https://github.com/webpack-contrib/copy-webpack-plugin) from 6.1.0 to 6.1.1.
- [Release notes](https://github.com/webpack-contrib/copy-webpack-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/copy-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/copy-webpack-plugin/compare/v6.1.0...v6.1.1)
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 9.8.4 to 9.8.6.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/9.8.4...9.8.6)
* Bumps [victory](https://github.com/formidablelabs/victory) from 35.0.8 to 35.0.9.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v35.0.8...v35.0.9)
* Bumps node from 14.10.1-alpine to 14.11.0-alpine.
* Bump node from 14.10.1-alpine to 14.11.0-alpine
* Bump eslint-plugin-react from 7.20.1 to 7.20.6
* Bump copy-webpack-plugin from 6.1.0 to 6.1.1
* Bump autoprefixer from 9.8.4 to 9.8.6
* Bump victory from 35.0.8 to 35.0.9
* Bump html-webpack-plugin from 4.3.0 to 4.4.1
* Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.20.6 to 7.21.2.
- [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
- [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yannickcr/eslint-plugin-react/commits)
* Bumps [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import) from 2.22.0 to 2.22.1.
- [Release notes](https://github.com/benmosher/eslint-plugin-import/releases)
- [Changelog](https://github.com/benmosher/eslint-plugin-import/blob/master/CHANGELOG.md)
- [Commits](https://github.com/benmosher/eslint-plugin-import/compare/v2.22.0...v2.22.1)
* Bumps [enzyme-adapter-react-16](https://github.com/enzymejs/enzyme/tree/HEAD/packages/enzyme-adapter-react-16) from 1.15.4 to 1.15.5.
- [Release notes](https://github.com/enzymejs/enzyme/releases)
- [Changelog](https://github.com/enzymejs/enzyme/blob/master/CHANGELOG.md)
- [Commits](https://github.com/enzymejs/enzyme/commits/enzyme-adapter-react-16@1.15.5/packages/enzyme-adapter-react-16)
* Bumps [universal-cookie](https://github.com/reactivestack/cookies) from 4.0.3 to 4.0.4.
- [Release notes](https://github.com/reactivestack/cookies/releases)
- [Changelog](https://github.com/reactivestack/cookies/blob/master/CHANGELOG.md)
- [Commits](https://github.com/reactivestack/cookies/compare/v4.0.3...v4.0.4)
* Bump universal-cookie from 4.0.3 to 4.0.4
* Bump enzyme-adapter-react-16 from 1.15.4 to 1.15.5
* Bump eslint-plugin-import from 2.22.0 to 2.22.1
* Bump eslint-plugin-react from 7.20.6 to 7.21.2
* Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 0.11.2 to 0.11.3.
- [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v0.11.2...v0.11.3)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.9.0 to 7.10.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.9.0...v7.10.0)
* Bumps [yarn](https://github.com/yarnpkg/yarn) from 1.22.5 to 1.22.10.
- [Release notes](https://github.com/yarnpkg/yarn/releases)
- [Changelog](https://github.com/yarnpkg/yarn/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yarnpkg/yarn/compare/v1.22.5...1.22.10)
* Bumps [jwt-decode](https://github.com/auth0/jwt-decode) from 2.2.0 to 3.0.0.
- [Release notes](https://github.com/auth0/jwt-decode/releases)
- [Changelog](https://github.com/auth0/jwt-decode/blob/master/CHANGELOG.md)
- [Commits](https://github.com/auth0/jwt-decode/compare/v2.2.0...v3.0.0)
* Bumps node from 14.11.0-alpine to 14.12.0-alpine.
* Bump node from 14.11.0-alpine to 14.12.0-alpine
* Bump jwt-decode from 2.2.0 to 3.0.0
* Bump yarn from 1.22.5 to 1.22.10
* Bump eslint from 7.9.0 to 7.10.0
* Bump mini-css-extract-plugin from 0.11.2 to 0.11.3
* Bumps [copy-webpack-plugin](https://github.com/webpack-contrib/copy-webpack-plugin) from 6.1.1 to 6.2.1.
- [Release notes](https://github.com/webpack-contrib/copy-webpack-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/copy-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/copy-webpack-plugin/compare/v6.1.1...v6.2.1)
* Bumps [jest](https://github.com/facebook/jest) from 26.4.2 to 26.5.3.
- [Release notes](https://github.com/facebook/jest/releases)
- [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
- [Commits](https://github.com/facebook/jest/compare/v26.4.2...v26.5.3)
* Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.21.2 to 7.21.4.
- [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
- [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.21.2...v7.21.4)
* Bumps node from 14.12.0-alpine to 14.13.1-alpine.
* Bumps nginx from 1.19.2-alpine to 1.19.3-alpine.
* Bump nginx from 1.19.2-alpine to 1.19.3-alpine
* Bump node from 14.12.0-alpine to 14.13.1-alpine
* Bump eslint-plugin-react from 7.21.2 to 7.21.4
* Bump jest from 26.4.2 to 26.5.3
* Bump copy-webpack-plugin from 6.1.1 to 6.2.1
* Bumps [url-loader](https://github.com/webpack-contrib/url-loader) from 4.1.0 to 4.1.1.
- [Release notes](https://github.com/webpack-contrib/url-loader/releases)
- [Changelog](https://github.com/webpack-contrib/url-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/url-loader/compare/v4.1.0...v4.1.1)
* Bumps [file-loader](https://github.com/webpack-contrib/file-loader) from 6.1.0 to 6.1.1.
- [Release notes](https://github.com/webpack-contrib/file-loader/releases)
- [Changelog](https://github.com/webpack-contrib/file-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/file-loader/compare/v6.1.0...v6.1.1)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.11.6 to 7.12.3.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.3/packages/babel-core)
* Bumps node from 14.13.1-alpine to 14.14.0-alpine.
* Bump @babel/core from 7.11.6 to 7.12.3
* Bump file-loader from 6.1.0 to 6.1.1
* Bump url-loader from 4.1.0 to 4.1.1
* Bump node from 14.13.1-alpine to 14.14.0-alpine
* Bumps [react-dropzone](https://github.com/react-dropzone/react-dropzone) from 11.2.0 to 11.2.1.
- [Release notes](https://github.com/react-dropzone/react-dropzone/releases)
- [Commits](https://github.com/react-dropzone/react-dropzone/compare/v11.2.0...v11.2.1)
* Bumps [resolve-url-loader](https://github.com/bholloway/resolve-url-loader) from 3.1.1 to 3.1.2.
- [Release notes](https://github.com/bholloway/resolve-url-loader/releases)
- [Commits](https://github.com/bholloway/resolve-url-loader/compare/3.1.1...3.1.2)
* Bumps node from 14.14.0-alpine to 15.0.1-alpine.
* Bump resolve-url-loader from 3.1.1 to 3.1.2
* Bump react-dropzone from 11.2.0 to 11.2.1
* Bump node from 14.14.0-alpine to 15.0.1-alpine
* Bumps [react-ga](https://github.com/react-ga/react-ga) from 3.1.2 to 3.2.0.
- [Release notes](https://github.com/react-ga/react-ga/releases)
- [Commits](https://github.com/react-ga/react-ga/compare/v3.1.2...v3.2.0)
* Bump react-ga from 3.1.2 to 3.2.0
* Bumps [@babel/preset-react](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-react) from 7.10.4 to 7.12.1.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.1/packages/babel-preset-react)
* Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.3.6 to 4.5.0.
- [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
- [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.3.6...4.5.0)
* Bumps [@mdi/js](https://github.com/Templarian/MaterialDesign-JS) from 5.6.55 to 5.8.55.
- [Release notes](https://github.com/Templarian/MaterialDesign-JS/releases)
- [Commits](https://github.com/Templarian/MaterialDesign-JS/compare/v5.6.55...v5.8.55)
* Bump @mdi/js from 5.6.55 to 5.8.55
* Bump react-idle-timer from 4.3.6 to 4.5.0
* Bump @babel/preset-react from 7.10.4 to 7.12.1
* Bumps node from 15.0.1-alpine to 15.1.0-alpine.
* Bumps nginx from 1.19.3-alpine to 1.19.4-alpine.
* Bump nginx from 1.19.3-alpine to 1.19.4-alpine
* Bump node from 15.0.1-alpine to 15.1.0-alpine
* Bumps [postcss](https://github.com/postcss/postcss) from 8.1.4 to 8.1.6.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/master/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.1.4...8.1.6)
* Bump postcss from 8.1.4 to 8.1.6
* Bumps node from 15.1.0-alpine to 15.2.0-alpine.
* Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.2.3 to 1.2.4.
- [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
- [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
- [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.2.3...v1.2.4)
* Bumps [jwt-decode](https://github.com/auth0/jwt-decode) from 2.2.0 to 3.1.1.
- [Release notes](https://github.com/auth0/jwt-decode/releases)
- [Changelog](https://github.com/auth0/jwt-decode/blob/master/CHANGELOG.md)
- [Commits](https://github.com/auth0/jwt-decode/compare/v2.2.0...v3.1.1)
* Bumps [cypress](https://github.com/cypress-io/cypress) from 5.4.0 to 5.6.0.
- [Release notes](https://github.com/cypress-io/cypress/releases)
- [Changelog](https://github.com/cypress-io/cypress/blob/develop/.releaserc.base.js)
- [Commits](https://github.com/cypress-io/cypress/compare/v5.4.0...v5.6.0)
* Bumps [eslint-plugin-cypress](https://github.com/cypress-io/eslint-plugin-cypress) from 2.11.1 to 2.11.2.
- [Release notes](https://github.com/cypress-io/eslint-plugin-cypress/releases)
- [Commits](https://github.com/cypress-io/eslint-plugin-cypress/compare/v2.11.1...v2.11.2)
* Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 7.0.2 to 7.1.0.
- [Release notes](https://github.com/webpack-contrib/less-loader/releases)
- [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/less-loader/compare/v7.0.2...v7.1.0)
* Bump node from 15.1.0-alpine to 15.2.0-alpine
* Bump jwt-decode from 2.2.0 to 3.1.1 in /tests/e2e_tests
* Bump eslint-plugin-cypress from 2.11.1 to 2.11.2
* Bump less-loader from 7.0.2 to 7.1.0
* Bump cypress from 5.4.0 to 5.6.0 in /tests/e2e_tests
* Bump cypress-localstorage-commands from 1.2.3 to 1.2.4 in /tests/e2e_tests
* Bumps [react](https://github.com/facebook/react/tree/HEAD/packages/react) from 16.13.1 to 16.14.0.
- [Release notes](https://github.com/facebook/react/releases)
- [Changelog](https://github.com/facebook/react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/facebook/react/commits/v16.14.0/packages/react)
* Bump react from 16.13.1 to 16.14.0
* Bumps cypress/included from 5.4.0 to 5.6.0.
* Bump cypress/included from 5.4.0 to 5.6.0 in /tests/e2e_tests
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.0.1 to 10.0.2.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/10.0.1...10.0.2)
* Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.2.1 to 1.3.1.
- [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.2.1...v1.3.1)
* Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 5.0.0 to 5.0.1.
- [Release notes](https://github.com/webpack-contrib/css-loader/releases)
- [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/css-loader/compare/v5.0.0...v5.0.1)
* Bump css-loader from 5.0.0 to 5.0.1
* Bump mini-css-extract-plugin from 1.2.1 to 1.3.1
* Bump autoprefixer from 10.0.1 to 10.0.2
* Bumps [react-dom](https://github.com/facebook/react/tree/HEAD/packages/react-dom) from 16.13.1 to 16.14.0.
- [Release notes](https://github.com/facebook/react/releases)
- [Changelog](https://github.com/facebook/react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/facebook/react/commits/v16.14.0/packages/react-dom)
* Bumps [react-big-calendar](https://github.com/jquense/react-big-calendar) from 0.28.2 to 0.28.6.
- [Release notes](https://github.com/jquense/react-big-calendar/releases)
- [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jquense/react-big-calendar/compare/v0.28.2...v0.28.6)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.12.1 to 7.12.7.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.7/packages/babel-preset-env)
* Bumps node from 15.2.0-alpine to 15.2.1-alpine.
* Bumps [jwt-decode](https://github.com/auth0/jwt-decode) from 3.1.1 to 3.1.2.
- [Release notes](https://github.com/auth0/jwt-decode/releases)
- [Changelog](https://github.com/auth0/jwt-decode/blob/master/CHANGELOG.md)
- [Commits](https://github.com/auth0/jwt-decode/compare/v3.1.1...v3.1.2)
* Bump jwt-decode from 3.1.1 to 3.1.2 in /tests/e2e_tests
* Bump node from 15.2.0-alpine to 15.2.1-alpine
* Bump @babel/preset-env from 7.12.1 to 7.12.7
* Bump react-big-calendar from 0.28.2 to 0.28.6
* Bump react-dom from 16.13.1 to 16.14.0
* Bumps [lint-staged](https://github.com/okonet/lint-staged) from 10.5.1 to 10.5.2.
- [Release notes](https://github.com/okonet/lint-staged/releases)
- [Commits](https://github.com/okonet/lint-staged/compare/v10.5.1...v10.5.2)
* Bumps [@babel/preset-react](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-react) from 7.12.5 to 7.12.7.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.7/packages/babel-preset-react)
* Bumps [@material-ui/core](https://github.com/mui-org/material-ui/tree/HEAD/packages/material-ui) from 4.11.0 to 4.11.1.
- [Release notes](https://github.com/mui-org/material-ui/releases)
- [Changelog](https://github.com/mui-org/material-ui/blob/v4.11.1/CHANGELOG.md)
- [Commits](https://github.com/mui-org/material-ui/commits/v4.11.1/packages/material-ui)
* Bumps [buffer](https://github.com/feross/buffer) from 6.0.0 to 6.0.3.
- [Release notes](https://github.com/feross/buffer/releases)
- [Commits](https://github.com/feross/buffer/compare/v6.0.0...v6.0.3)
* Bumps nginx from 1.19.4-alpine to 1.19.5-alpine.
* Bumps node from 15.2.1-alpine to 15.3.0-alpine.
* Bump lint-staged from 10.5.1 to 10.5.2
* Bump @babel/preset-react from 7.12.5 to 7.12.7
* Bump @material-ui/core from 4.11.0 to 4.11.1
* Bump node from 15.2.1-alpine to 15.3.0-alpine
* Bump buffer from 6.0.0 to 6.0.3
* Bump nginx from 1.19.4-alpine to 1.19.5-alpine
* Bumps cypress/included from 5.6.0 to 6.0.0.
* Bump cypress/included from 5.6.0 to 6.0.0 in /tests/e2e_tests
* Bumps [eslint](https://github.com/eslint/eslint) from 7.12.1 to 7.14.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.12.1...v7.14.0)
* Bumps [postcss](https://github.com/postcss/postcss) from 8.1.6 to 8.1.10.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/master/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.1.6...8.1.10)
* Bumps [@babel/core](https://github.com/babel/babel/tree/HEAD/packages/babel-core) from 7.12.3 to 7.12.9.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.9/packages/babel-core)
* Bumps [react-dropzone](https://github.com/react-dropzone/react-dropzone) from 11.2.3 to 11.2.4.
- [Release notes](https://github.com/react-dropzone/react-dropzone/releases)
- [Commits](https://github.com/react-dropzone/react-dropzone/compare/v11.2.3...v11.2.4)
* Bump react-dropzone from 11.2.3 to 11.2.4
* Bump @babel/core from 7.12.3 to 7.12.9
* Bump postcss from 8.1.6 to 8.1.10
* Bump eslint from 7.12.1 to 7.14.0
* Bumps [webpack](https://github.com/webpack/webpack) from 5.4.0 to 5.9.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.4.0...v5.9.0)
* Bumps [prettier](https://github.com/prettier/prettier) from 2.1.2 to 2.2.1.
- [Release notes](https://github.com/prettier/prettier/releases)
- [Changelog](https://github.com/prettier/prettier/blob/master/CHANGELOG.md)
- [Commits](https://github.com/prettier/prettier/compare/2.1.2...2.2.1)
* Bumps [react-ga](https://github.com/react-ga/react-ga) from 3.2.0 to 3.3.0.
- [Release notes](https://github.com/react-ga/react-ga/releases)
- [Commits](https://github.com/react-ga/react-ga/compare/v3.2.0...v3.3.0)
* Bump react-ga from 3.2.0 to 3.3.0
* Bump prettier from 2.1.2 to 2.2.1
* Bump webpack from 5.4.0 to 5.9.0
* Bumps [postcss-loader](https://github.com/webpack-contrib/postcss-loader) from 4.0.4 to 4.1.0.
- [Release notes](https://github.com/webpack-contrib/postcss-loader/releases)
- [Changelog](https://github.com/webpack-contrib/postcss-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/postcss-loader/compare/v4.0.4...v4.1.0)
* Bump postcss-loader from 4.0.4 to 4.1.0
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.0.2 to 10.0.4.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/10.0.2...10.0.4)
* Bumps [babel-loader](https://github.com/babel/babel-loader) from 8.1.0 to 8.2.2.
- [Release notes](https://github.com/babel/babel-loader/releases)
- [Changelog](https://github.com/babel/babel-loader/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel-loader/compare/v8.1.0...v8.2.2)
* Bumps [core-js](https://github.com/zloirock/core-js) from 3.6.5 to 3.8.0.
- [Release notes](https://github.com/zloirock/core-js/releases)
- [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/zloirock/core-js/compare/v3.6.5...v3.8.0)
* Bump babel-loader from 8.1.0 to 8.2.2
* Bump autoprefixer from 10.0.2 to 10.0.4
* Bump core-js from 3.6.5 to 3.8.0
* Bumps [jwt-decode](https://github.com/auth0/jwt-decode) from 3.0.0 to 3.1.2.
- [Release notes](https://github.com/auth0/jwt-decode/releases)
- [Changelog](https://github.com/auth0/jwt-decode/blob/master/CHANGELOG.md)
- [Commits](https://github.com/auth0/jwt-decode/compare/v3.0.0...v3.1.2)
* Bumps [validator](https://github.com/chriso/validator.js) from 13.1.17 to 13.5.1.
- [Release notes](https://github.com/chriso/validator.js/releases)
- [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/chriso/validator.js/compare/13.1.17...13.5.1)
* Bump jwt-decode from 3.0.0 to 3.1.2
* Bump validator from 13.1.17 to 13.5.1
* Bumps [core-js](https://github.com/zloirock/core-js) from 3.8.0 to 3.8.1.
- [Release notes](https://github.com/zloirock/core-js/releases)
- [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/zloirock/core-js/compare/v3.8.0...v3.8.1)
* Bumps [mini-css-extract-plugin](https://github.com/webpack-contrib/mini-css-extract-plugin) from 1.3.1 to 1.3.2.
- [Release notes](https://github.com/webpack-contrib/mini-css-extract-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/mini-css-extract-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/mini-css-extract-plugin/compare/v1.3.1...v1.3.2)
* Bumps [@cypress/skip-test](https://github.com/cypress-io/cypress-skip-test) from 2.5.0 to 2.5.1.
- [Release notes](https://github.com/cypress-io/cypress-skip-test/releases)
- [Commits](https://github.com/cypress-io/cypress-skip-test/compare/v2.5.0...v2.5.1)
* Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.2.4 to 1.2.5.
- [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
- [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
- [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.2.4...v1.2.5)
* Bumps cypress/included from 6.0.0 to 6.0.1.
* Bump mini-css-extract-plugin from 1.3.1 to 1.3.2
* Bump @cypress/skip-test from 2.5.0 to 2.5.1 in /tests/e2e_tests
* Bump cypress-localstorage-commands from 1.2.4 to 1.2.5 in /tests/e2e_tests
* Bump cypress/included from 6.0.0 to 6.0.1 in /tests/e2e_tests
* Bump core-js from 3.8.0 to 3.8.1
* Bumps [webpack](https://github.com/webpack/webpack) from 5.9.0 to 5.10.0.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.9.0...v5.10.0)
* Bump webpack from 5.9.0 to 5.10.0
* Bumps [lint-staged](https://github.com/okonet/lint-staged) from 10.5.2 to 10.5.3.
- [Release notes](https://github.com/okonet/lint-staged/releases)
- [Commits](https://github.com/okonet/lint-staged/compare/v10.5.2...v10.5.3)
* Bumps [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) from 3.1.4 to 3.2.0.
- [Release notes](https://github.com/prettier/eslint-plugin-prettier/releases)
- [Changelog](https://github.com/prettier/eslint-plugin-prettier/blob/master/CHANGELOG.md)
- [Commits](https://github.com/prettier/eslint-plugin-prettier/compare/v3.1.4...v3.2.0)
* Bumps [postcss](https://github.com/postcss/postcss) from 8.1.10 to 8.1.14.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.1.10...8.1.14)
* Bump lint-staged from 10.5.2 to 10.5.3
* Bump postcss from 8.1.10 to 8.1.14
* Bump eslint-plugin-prettier from 3.1.4 to 3.2.0
* Bumps [ini](https://github.com/isaacs/ini) from 1.3.5 to 1.3.7.
- [Release notes](https://github.com/isaacs/ini/releases)
- [Commits](https://github.com/isaacs/ini/compare/v1.3.5...v1.3.7)
* Bumps [ini](https://github.com/isaacs/ini) from 1.3.5 to 1.3.8.
- [Release notes](https://github.com/isaacs/ini/releases)
- [Commits](https://github.com/isaacs/ini/compare/v1.3.5...v1.3.8)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.12.7 to 7.12.10.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.10/packages/babel-preset-env)
* Bumps [webpack](https://github.com/webpack/webpack) from 5.10.0 to 5.10.1.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.10.0...v5.10.1)
* Bumps [cypress-localstorage-commands](https://github.com/javierbrea/cypress-localstorage-commands) from 1.2.5 to 1.3.1.
- [Release notes](https://github.com/javierbrea/cypress-localstorage-commands/releases)
- [Changelog](https://github.com/javierbrea/cypress-localstorage-commands/blob/master/CHANGELOG.md)
- [Commits](https://github.com/javierbrea/cypress-localstorage-commands/compare/v1.2.5...v1.3.1)
* Bumps [uuid](https://github.com/uuidjs/uuid) from 8.3.1 to 8.3.2.
- [Release notes](https://github.com/uuidjs/uuid/releases)
- [Changelog](https://github.com/uuidjs/uuid/blob/master/CHANGELOG.md)
- [Commits](https://github.com/uuidjs/uuid/compare/v8.3.1...v8.3.2)
* Bumps node from 15.3.0-alpine to 15.4.0-alpine.
* Bumps cypress/included from 6.0.1 to 6.1.0.
* Bump cypress/included from 6.0.1 to 6.1.0 in /tests/e2e_tests
* Bump node from 15.3.0-alpine to 15.4.0-alpine
* Bump uuid from 8.3.1 to 8.3.2 in /tests/e2e_tests
* Bump cypress-localstorage-commands from 1.2.5 to 1.3.1 in /tests/e2e_tests
* Bump @babel/preset-env from 7.12.7 to 7.12.10
* Bump ini from 1.3.5 to 1.3.8 in /tests/e2e_tests
* Bump webpack from 5.10.0 to 5.10.1
* Bump ini from 1.3.5 to 1.3.7
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.0.4 to 10.1.0.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/10.0.4...10.1.0)
* Bumps [@babel/preset-react](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-react) from 7.12.7 to 7.12.10.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.12.10/packages/babel-preset-react)
* Bumps nginx from 1.19.5-alpine to 1.19.6-alpine.
* Bump nginx from 1.19.5-alpine to 1.19.6-alpine
* Bump autoprefixer from 10.0.4 to 10.1.0
* Bump @babel/preset-react from 7.12.7 to 7.12.10
* Bumps node from 15.4.0-alpine to 15.5.0-alpine.
* Bump node from 15.4.0-alpine to 15.5.0-alpine
* Bumps [@testing-library/jest-dom](https://github.com/testing-library/jest-dom) from 5.11.6 to 5.11.8.
- [Release notes](https://github.com/testing-library/jest-dom/releases)
- [Changelog](https://github.com/testing-library/jest-dom/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/jest-dom/compare/v5.11.6...v5.11.8)
* Bump @testing-library/jest-dom from 5.11.6 to 5.11.8
* Bumps [core-js](https://github.com/zloirock/core-js) from 3.8.1 to 3.8.2.
- [Release notes](https://github.com/zloirock/core-js/releases)
- [Changelog](https://github.com/zloirock/core-js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/zloirock/core-js/compare/v3.8.1...v3.8.2)
* Bump core-js from 3.8.1 to 3.8.2
* Bumps [@testing-library/dom](https://github.com/testing-library/dom-testing-library) from 7.29.0 to 7.29.1.
- [Release notes](https://github.com/testing-library/dom-testing-library/releases)
- [Changelog](https://github.com/testing-library/dom-testing-library/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/dom-testing-library/compare/v7.29.0...v7.29.1)
* Bumps [msgpack5](https://github.com/mcollina/msgpack5) from 4.2.1 to 5.0.0.
- [Release notes](https://github.com/mcollina/msgpack5/releases)
- [Commits](https://github.com/mcollina/msgpack5/commits/v5.0.0)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.16.0 to 7.17.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.16.0...v7.17.0)
* Bumps [html-webpack-plugin](https://github.com/jantimon/html-webpack-plugin) from 4.5.0 to 4.5.1.
- [Release notes](https://github.com/jantimon/html-webpack-plugin/releases)
- [Changelog](https://github.com/jantimon/html-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/jantimon/html-webpack-plugin/compare/v4.5.0...v4.5.1)
* Bump html-webpack-plugin from 4.5.0 to 4.5.1
* Bump eslint from 7.16.0 to 7.17.0
* Bump @testing-library/dom from 7.29.0 to 7.29.1
* Bumps [webpack](https://github.com/webpack/webpack) from 5.11.0 to 5.11.1.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.11.0...v5.11.1)
* Bumps [eslint-plugin-prettier](https://github.com/prettier/eslint-plugin-prettier) from 3.3.0 to 3.3.1.
- [Release notes](https://github.com/prettier/eslint-plugin-prettier/releases)
- [Changelog](https://github.com/prettier/eslint-plugin-prettier/blob/master/CHANGELOG.md)
- [Commits](https://github.com/prettier/eslint-plugin-prettier/compare/v3.3.0...v3.3.1)
* Bump eslint-plugin-prettier from 3.3.0 to 3.3.1
* Bump webpack from 5.11.0 to 5.11.1
* Bumps [msw](https://github.com/mswjs/msw) from 0.24.2 to 0.25.0.
- [Release notes](https://github.com/mswjs/msw/releases)
- [Changelog](https://github.com/mswjs/msw/blob/master/CHANGELOG.md)
- [Commits](https://github.com/mswjs/msw/compare/v0.24.2...v0.25.0)
* Bumps [postcss](https://github.com/postcss/postcss) from 8.2.1 to 8.2.2.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.2.1...8.2.2)
* Bumps [less](https://github.com/less/less.js) from 3.12.2 to 3.13.1.
- [Release notes](https://github.com/less/less.js/releases)
- [Changelog](https://github.com/less/less.js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/less/less.js/compare/v3.12.2...v3.13.1)
* Bumps [axios](https://github.com/axios/axios) from 0.21.0 to 0.21.1.
- [Release notes](https://github.com/axios/axios/releases)
- [Changelog](https://github.com/axios/axios/blob/v0.21.1/CHANGELOG.md)
- [Commits](https://github.com/axios/axios/compare/v0.21.0...v0.21.1)
* Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.21.5 to 7.22.0.
- [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
- [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.21.5...v7.22.0)
* Bump axios from 0.21.0 to 0.21.1
* Bump eslint-plugin-react from 7.21.5 to 7.22.0
* Bumps [less-loader](https://github.com/webpack-contrib/less-loader) from 7.1.0 to 7.2.1.
- [Release notes](https://github.com/webpack-contrib/less-loader/releases)
- [Changelog](https://github.com/webpack-contrib/less-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/less-loader/compare/v7.1.0...v7.2.1)
* Bump msgpack5 from 4.2.1 to 5.0.0
* Bumps [webpack](https://github.com/webpack/webpack) from 5.11.1 to 5.12.1.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.11.1...v5.12.1)
* Bumps [react-idle-timer](https://github.com/supremetechnopriest/react-idle-timer) from 4.5.0 to 4.5.1.
- [Release notes](https://github.com/supremetechnopriest/react-idle-timer/releases)
- [Changelog](https://github.com/SupremeTechnopriest/react-idle-timer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/supremetechnopriest/react-idle-timer/compare/4.5.0...4.5.1)
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 10.2.0 to 10.2.1.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/10.2.0...10.2.1)
* Bumps [@testing-library/react](https://github.com/testing-library/react-testing-library) from 11.2.2 to 11.2.3.
- [Release notes](https://github.com/testing-library/react-testing-library/releases)
- [Changelog](https://github.com/testing-library/react-testing-library/blob/master/CHANGELOG.md)
- [Commits](https://github.com/testing-library/react-testing-library/compare/v11.2.2...v11.2.3)
* Bump @testing-library/react from 11.2.2 to 11.2.3
* Bump autoprefixer from 10.2.0 to 10.2.1
* Bump react-idle-timer from 4.5.0 to 4.5.1
* Bump webpack from 5.11.1 to 5.12.1
* Bumps [webpack](https://github.com/webpack/webpack) from 5.12.1 to 5.12.3.
- [Release notes](https://github.com/webpack/webpack/releases)
- [Commits](https://github.com/webpack/webpack/compare/v5.12.1...v5.12.3)
* Bumps [postcss](https://github.com/postcss/postcss) from 8.2.3 to 8.2.4.
- [Release notes](https://github.com/postcss/postcss/releases)
- [Changelog](https://github.com/postcss/postcss/blob/main/CHANGELOG.md)
- [Commits](https://github.com/postcss/postcss/compare/8.2.3...8.2.4)
* Bumps [less](https://github.com/less/less.js) from 4.0.0 to 4.1.0.
- [Release notes](https://github.com/less/less.js/releases)
- [Changelog](https://github.com/less/less.js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/less/less.js/compare/v4.0.0...v4.1.0)
* Bumps node from 15.5.0-alpine to 15.5.1-alpine.
* Bump node from 15.5.0-alpine to 15.5.1-alpine
* Bump less from 4.0.0 to 4.1.0
* Bump postcss from 8.2.3 to 8.2.4
* Bump webpack from 5.12.1 to 5.12.3

#### integration (2.6.0)

New changes in integration since 2.5.0:

* New compose file to optionally add deviceconnect service to the backend
* New compose file to optionally add deviceconnect service to the backend
* demo script, include docker-compose.connect.yml by default
([MEN-4357](https://tracker.mender.io/browse/MEN-4357))
* Add auditlogs and deviceconnect to production templates
* Add auditlogs 1.0.0.
* Upgrade deployments to 2.2.0.
* Upgrade deployments-enterprise to 2.2.0.
* Upgrade deviceauth to 2.5.0.
* Add deviceconnect 1.0.0.
* Upgrade gui to 2.6.0.
* Upgrade inventory to 2.2.0.
* Upgrade inventory-enterprise to 2.2.0.
* Upgrade mender to 2.5.0.
* Upgrade mender-api-gateway-docker to 2.4.0.
* Upgrade mender-artifact to 3.5.0.
* Upgrade mender-cli to 1.6.0.
* Add mender-connect 1.0.0.
* Upgrade tenantadm to 3.0.0.
* Upgrade useradm to 1.13.0.
* Upgrade useradm-enterprise to 1.13.0.
* Upgrade workflows to 1.3.0.
* Upgrade workflows-enterprise to 1.3.0.
* Aggregated Dependabot Changelogs:
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.50.0 to 2.51.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.50.0...v2.51.0)
* Bump stripe from 2.50.0 to 2.51.0 in /backend-tests
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.0.1 to 6.0.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.0.1...6.0.2)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.26.2 to 1.27.2.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/master/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.26.2...1.27.2)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.0.1 to 6.0.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.0.1...6.0.2)
* Bump pytest from 6.0.1 to 6.0.2 in /tests/requirements
* Bump docker-compose from 1.26.2 to 1.27.2 in /tests/requirements
* Bump pytest from 6.0.1 to 6.0.2 in /backend-tests
* Bumps [docker-compose](https://github.com/docker/compose) from 1.27.2 to 1.27.3.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.27.3/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.27.2...1.27.3)
* Bump docker-compose from 1.27.2 to 1.27.3 in /tests/requirements
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.0.2 to 6.1.0.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.0.2...6.1.0)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.27.3 to 1.27.4.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.27.4/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.27.3...1.27.4)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.1 to 3.1.1.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.1...3.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.0.2 to 6.1.0.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.0.2...6.1.0)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.51.0 to 2.53.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.51.0...v2.53.0)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.0 to 6.1.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.0...6.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.0 to 6.1.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.0...6.1.1)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.53.0 to 2.54.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.53.0...v2.54.0)
* Bumps python from 3.8 to 3.9.0.
* Bump python from 3.8 to 3.9.0 in /backend-tests/docker
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.54.0 to 2.55.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.54.0...v2.55.0)
* Bumps [pillow](https://github.com/python-pillow/Pillow) from 7.2.0 to 8.0.0.
- [Release notes](https://github.com/python-pillow/Pillow/releases)
- [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
- [Commits](https://github.com/python-pillow/Pillow/compare/7.2.0...8.0.0)
* Bumps [pyotp](https://github.com/pyotp/pyotp) from 2.4.0 to 2.4.1.
- [Release notes](https://github.com/pyotp/pyotp/releases)
- [Changelog](https://github.com/pyauth/pyotp/blob/develop/Changes.rst)
- [Commits](https://github.com/pyotp/pyotp/compare/v2.4.0...v2.4.1)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.1.1 to 3.2.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.1.1...3.2)
* Bumps [pillow](https://github.com/python-pillow/Pillow) from 8.0.0 to 8.0.1.
- [Release notes](https://github.com/python-pillow/Pillow/releases)
- [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
- [Commits](https://github.com/python-pillow/Pillow/compare/8.0.0...8.0.1)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.2 to 3.2.1.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.2...3.2.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.1 to 6.1.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.1...6.1.2)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.1 to 6.1.2.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.1...6.1.2)
* Bumps [requests](https://github.com/psf/requests) from 2.24.0 to 2.25.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.24.0...v2.25.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.1.1 to 3.0.0.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.1.1...v3.0.0)
* Bump pytest-html from 2.1.1 to 3.0.0 in /tests/requirements
* Bump requests from 2.24.0 to 2.25.0 in /tests/requirements
* Bumps [requests](https://github.com/psf/requests) from 2.24.0 to 2.25.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.24.0...v2.25.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.1.1 to 3.0.0.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.1.1...v3.0.0)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.0 to 3.11.1.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.0...3.11.1)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.0 to 3.11.1.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.0...3.11.1)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 3.0.0 to 3.1.0.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v3.0.0...v3.1.0)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.1 to 3.11.2.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/3.11.2/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.1...3.11.2)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 3.0.0 to 3.1.0.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v3.0.0...v3.1.0)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.11.1 to 3.11.2.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/3.11.2/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.11.1...3.11.2)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.55.0 to 2.55.1.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.55.0...v2.55.1)
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.2.1 to 3.3.1.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.2.1...3.3.1)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 3.1.0 to 3.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v3.1.0...v3.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.2 to 6.2.0.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.2...6.2.0)
* Bumps python from 3.9.0 to 3.9.1.
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.1.2 to 6.2.0.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.1.2...6.2.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 3.1.0 to 3.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v3.1.0...v3.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.0 to 6.2.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.2.0...6.2.1)
* Bumps [requests](https://github.com/psf/requests) from 2.25.0 to 2.25.1.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.25.0...v2.25.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 6.2.0 to 6.2.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/6.2.0...6.2.1)
* Bumps [requests](https://github.com/psf/requests) from 2.25.0 to 2.25.1.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.25.0...v2.25.1)
* Bumps [pillow](https://github.com/python-pillow/Pillow) from 8.0.1 to 8.1.0.
- [Release notes](https://github.com/python-pillow/Pillow/releases)
- [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
- [Commits](https://github.com/python-pillow/Pillow/compare/8.0.1...8.1.0)
* Bump pillow from 8.0.1 to 8.1.0 in /backend-tests

#### inventory (2.2.0)

New changes in inventory since 2.1.0:

* new device API end-point to replace inventory attributes
([MEN-4001](https://tracker.mender.io/browse/MEN-4001))
* new API end-point to return the list of filterable attributes
([MEN-3510](https://tracker.mender.io/browse/MEN-3510))
* Aggregated Dependabot Changelogs:
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4

#### inventory-enterprise (2.2.0)

New changes in inventory-enterprise since 2.1.0:

* new device API end-point to replace inventory attributes
([MEN-4001](https://tracker.mender.io/browse/MEN-4001))
* new API end-point to return the list of filterable attributes
([MEN-3510](https://tracker.mender.io/browse/MEN-3510))
* optional redis cache to get filterable attributes
([MEN-3510](https://tracker.mender.io/browse/MEN-3510))
* Aggregated Dependabot Changelogs:
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.3.2 to 8.3.3.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.3.2...v8.3.3)
* Bump github.com/go-redis/redis/v8 from 8.3.2 to 8.3.3
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.3.3 to 8.4.0.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.3.3...v8.4.0)
* Bump github.com/go-redis/redis/v8 from 8.3.3 to 8.4.0
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.0 to 8.4.2.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.0...v8.4.2)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.4)
* Bump github.com/go-redis/redis/v8 from 8.4.0 to 8.4.2
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.4
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.2 to 8.4.4.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.2...v8.4.4)
* Bump github.com/go-redis/redis/v8 from 8.4.2 to 8.4.4
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.4 to 8.4.8.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.4...v8.4.8)
* Bump github.com/go-redis/redis/v8 from 8.4.4 to 8.4.8

#### mender-api-gateway-docker (2.4.0)

New changes in mender-api-gateway-docker since 2.3.0:

* expose the management end-point to verify the user's plan
([MEN-3953](https://tracker.mender.io/browse/MEN-3953))
* restore ALLOWED_ORIGIN_HOSTS regex match when checking Origin
([MEN-4118](https://tracker.mender.io/browse/MEN-4118))

#### tenantadm (3.0.0)

New changes in tenantadm since 2.1.0:

* credit card update endpoints
* enhance /billing end-point to retrieve current subscription
([MEN-3821](https://tracker.mender.io/browse/MEN-3821))
* Aggregated Dependabot Changelogs:
* Bumps [github.com/sirupsen/logrus](https://github.com/sirupsen/logrus) from 1.6.0 to 1.7.0.
- [Release notes](https://github.com/sirupsen/logrus/releases)
- [Changelog](https://github.com/sirupsen/logrus/blob/master/CHANGELOG.md)
- [Commits](https://github.com/sirupsen/logrus/compare/v1.6.0...v1.7.0)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.0 to 1.4.2.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.0...v1.4.2)
* Bump github.com/sirupsen/logrus from 1.6.0 to 1.7.0
* Bump go.mongodb.org/mongo-driver from 1.4.0 to 1.4.2
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.3.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.3)
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.3
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4

#### useradm (1.13.0)

New changes in useradm since 1.12.0:

* GET /users accepts query parameters for filtering users
* new API end-point logout
([MEN-3943](https://tracker.mender.io/browse/MEN-3943))
* remove JWT all user tokens but the current one on password change
([MEN-3950](https://tracker.mender.io/browse/MEN-3950))
* Allow JWT to be passed as a cookie
([MEN-4042](https://tracker.mender.io/browse/MEN-4042))
* Add last login timestamp to user object
* Aggregated Dependabot Changelogs:
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.3.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.3)
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.3
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4

#### useradm-enterprise (1.13.0)

New changes in useradm-enterprise since 1.12.0:

* GET /users accepts query parameters for filtering users
* new API end-point logout
([MEN-3943](https://tracker.mender.io/browse/MEN-3943))
* remove JWT all user tokens but the current one on password change
([MEN-3950](https://tracker.mender.io/browse/MEN-3950))
* Useradm reports audit logs on create/delete user and updating
roles
* , new management end-point to verify user's plan
([MEN-3275](https://tracker.mender.io/browse/MEN-3275), [MEN-3953](https://tracker.mender.io/browse/MEN-3953))
* Allow JWT to be passed as a cookie
([MEN-4042](https://tracker.mender.io/browse/MEN-4042))
* Add last login timestamp to user object
* introduce "REMOTE_TERMINAL" permission
* Add the Remote Terminal RBAC role
* Aggregated Dependabot Changelogs:
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bumps [github.com/urfave/cli](https://github.com/urfave/cli) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/urfave/cli/releases)
- [Changelog](https://github.com/urfave/cli/blob/master/docs/CHANGELOG.md)
- [Commits](https://github.com/urfave/cli/compare/v1.22.4...v1.22.5)
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bump github.com/urfave/cli from 1.22.4 to 1.22.5
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.3.2 to 8.4.0.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.3.2...v8.4.0)
* Bump github.com/go-redis/redis/v8 from 8.3.2 to 8.4.0
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.2 to 1.4.3.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.2...v1.4.3)
* Bump go.mongodb.org/mongo-driver from 1.4.2 to 1.4.3
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.0 to 8.4.2.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.0...v8.4.2)
* Bump github.com/go-redis/redis/v8 from 8.4.0 to 8.4.2
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.2 to 8.4.4.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.2...v8.4.4)
* Bump github.com/go-redis/redis/v8 from 8.4.2 to 8.4.4
* Bumps [github.com/go-redis/redis/v8](https://github.com/go-redis/redis) from 8.4.4 to 8.4.8.
- [Release notes](https://github.com/go-redis/redis/releases)
- [Changelog](https://github.com/go-redis/redis/blob/master/CHANGELOG.md)
- [Commits](https://github.com/go-redis/redis/compare/v8.4.4...v8.4.8)
* Bump github.com/go-redis/redis/v8 from 8.4.4 to 8.4.8

#### workflows (1.3.0)

New changes in workflows since 1.2.0:

* add support for JSON body in HTTP tasks
([MEN-4110](https://tracker.mender.io/browse/MEN-4110))
* New properties: `requires` for Tasks, `skippped` for TaskResult
* Add support for default values in expressions
* Update workflow definitions to allow services' addresses override
* Add retryDelaySeconds property to speficy retry delays in tasks
* Aggregated Dependabot Changelogs:
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.0 to 1.4.3.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.0...v1.4.3)
* Bump golang from 1.14-alpine3.12 to 1.15.4-alpine3.12
* Bump go.mongodb.org/mongo-driver from 1.4.0 to 1.4.3
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4

#### workflows-enterprise (1.3.0)

New changes in workflows-enterprise since 1.2.0:

* Change welcome email to contain self-service password reset link.
* add support for JSON body in HTTP tasks
([MEN-4110](https://tracker.mender.io/browse/MEN-4110))
* New properties: `requires` for Tasks, `skippped` for TaskResult
* Add support for default values in expressions
* Update workflow definitions to allow services' addresses override
* Add retryDelaySeconds property to speficy retry delays in tasks
* Aggregated Dependabot Changelogs:
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.0 to 1.4.3.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.0...v1.4.3)
* Bump golang from 1.14-alpine3.12 to 1.15.4-alpine3.12
* Bump go.mongodb.org/mongo-driver from 1.4.0 to 1.4.3
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bumps [go.mongodb.org/mongo-driver](https://github.com/mongodb/mongo-go-driver) from 1.4.3 to 1.4.4.
- [Release notes](https://github.com/mongodb/mongo-go-driver/releases)
- [Commits](https://github.com/mongodb/mongo-go-driver/compare/v1.4.3...v1.4.4)
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4
* Bump go.mongodb.org/mongo-driver from 1.4.3 to 1.4.4

## Mender 2.5.1

_Released 01.21.2021_

### Changelogs

#### deployments (2.1.1)

New changes in deployments since 2.1.0:

* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* api: Generate artifact doesn't load entire request upon parsing
* api: Generate artifact endpoint accepts form values with whitespaces
* Deploy to group for os onprem fix.
([MEN-4029](https://tracker.mender.io/browse/MEN-4029))

#### deployments-enterprise (2.1.1)

New changes in deployments-enterprise since 2.1.0:

* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* api: Generate artifact doesn't load entire request upon parsing
* api: Generate artifact endpoint accepts form values with whitespaces
* Deploy to group for os onprem fix.
([MEN-4029](https://tracker.mender.io/browse/MEN-4029))

#### deviceauth (2.4.1)

New changes in deviceauth since 2.4.0:

* New query parameter id for GET /api/management/v1/devices
* ignore tenant claim in single tenant setup
([MEN-3972](https://tracker.mender.io/browse/MEN-3972))

#### gui (2.5.1)

New changes in gui since 2.5.0:

* fixed an issue that prevented admin access to user management settings

#### integration (2.5.1)

New changes in integration since 2.5.0:

* Upgrade deployments to 2.1.1.
* Upgrade deployments-enterprise to 2.1.1.
* Upgrade deviceauth to 2.4.1.
* Upgrade gui to 2.5.1.
* Upgrade inventory to 2.1.1.
* Upgrade inventory-enterprise to 2.1.1.
* Upgrade mender to 2.4.2.
* Upgrade mender-api-gateway-docker to 2.3.1.
* Upgrade mender-artifact to 3.4.1.
* Upgrade mender-cli to 1.5.1.

#### inventory (2.1.1)

New changes in inventory since 2.1.0:

* Deploy to group for os onprem fix.
([MEN-4029](https://tracker.mender.io/browse/MEN-4029))

#### inventory-enterprise (2.1.1)

New changes in inventory-enterprise since 2.1.0:

* Deploy to group for os onprem fix.
([MEN-4029](https://tracker.mender.io/browse/MEN-4029))

#### mender-api-gateway-docker (2.3.1)

New changes in mender-api-gateway-docker since 2.3.0:

* restore ALLOWED_ORIGIN_HOSTS regex match when checking Origin
([MEN-4118](https://tracker.mender.io/browse/MEN-4118))
## Mender 2.5.0

_Released 09.11.2020_

### Changelogs

#### deployments (2.1.0)

New changes in deployments since 2.0.0:

* Remove mongodb write/read concerns, let the connection string set them
* override file name in artifact download links
([MEN-3417](https://tracker.mender.io/browse/MEN-3417))
* New endpoint to deploy to group of devices
`POST /deployments/group/:name`
([MEN-3411](https://tracker.mender.io/browse/MEN-3411))
* New internal health check and liveliness endpoints
`GET /api/internal/v1/deployments/health`
`GET /api/internal/v1/deployments/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### deployments-enterprise (2.1.0)

New changes in deployments-enterprise since 2.0.0:

* Remove mongodb write/read concerns, let the connection string set them
* override file name in artifact download links
([MEN-3417](https://tracker.mender.io/browse/MEN-3417))
* New endpoint to deploy to group of devices
`POST /deployments/group/:name`
([MEN-3411](https://tracker.mender.io/browse/MEN-3411))
* New internal health check and liveliness endpoints
`GET /api/internal/v1/deployments/health`
`GET /api/internal/v1/deployments/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### deviceauth (2.4.0)

New changes in deviceauth since 2.3.0:

* internal API end-point to delete tenant limits
([MC-4040](https://tracker.mender.io/browse/MC-4040))
* Add support for ED25519 and ECDSA public keys in auth requests
([MEN-3728](https://tracker.mender.io/browse/MEN-3728))
* New internal health check and liveliness endpoints
`GET /api/internal/v1/deviceauth/health`
`GET /api/internal/v1/deviceauth/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))
* device preauthorization: in case of conflict return conflicting device
([MEN-3813](https://tracker.mender.io/browse/MEN-3813))

#### gui (2.5.0)

New changes in gui since 2.4.0:

* added roles management to settings to allow adding group based roles
* fixed identity attribute filtering on authorized devices
([MEN-3517](https://tracker.mender.io/browse/MEN-3517))
* enabled automatic selection on filter autocomplete
([MEN-3518](https://tracker.mender.io/browse/MEN-3518))
* ensured onboarding tooltip shows up after custom artifact is uploaded
* add cancel subscription form in organization page
([MEN-3306](https://tracker.mender.io/browse/MEN-3306))
* fixed an issue that caused unexpected deployment device states to crash the deployment report
* fixed an issue that prevented exists filter from working
* combined bulk device actions in speed dial on device selection
this allows easier device accepting, rejecting or group membership changes
* fixed settings availability in OS & onprem-enterprise deployments
* reintroduced ungrouped group
* switched group based deployment to use corresponding api endpoint
this reduced the need to retrieve all group devices in the UI
* adjusted group creation dialog to focus on device selection outside of dialog
* Add upgrade page for trial users
* added sorting capabilities to device lists
* enabled dual rbac roles for groups to align with new rbac role in backend
* added cancellation option for artifact upload & generation
* fixed authorization header in userapi calls
* Add livechat widget component
* Aggregated Dependabot Changelogs:
* Bumps node from 12.14.0-alpine to 14.4.0-alpine.
* Bumps nginx from 1.17-alpine to 1.19.0-alpine.
* Bumps [eslint](https://github.com/eslint/eslint) from 7.1.0 to 7.2.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.1.0...v7.2.0)
* Bumps [victory](https://github.com/formidablelabs/victory) from 34.3.10 to 34.3.11.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/master/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v34.3.10...v34.3.11)
* Bumps [css-loader](https://github.com/webpack-contrib/css-loader) from 3.5.3 to 3.6.0.
- [Release notes](https://github.com/webpack-contrib/css-loader/releases)
- [Changelog](https://github.com/webpack-contrib/css-loader/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/css-loader/compare/v3.5.3...v3.6.0)
* Bump node from 12.14.0-alpine to 14.4.0-alpine
* Bump victory from 34.3.10 to 34.3.11
* Bump nginx from 1.17-alpine to 1.19.0-alpine
* Bump eslint from 7.1.0 to 7.2.0
* Bump css-loader from 3.5.3 to 3.6.0
* Bumps [moment](https://github.com/moment/moment) from 2.26.0 to 2.27.0.
- [Release notes](https://github.com/moment/moment/releases)
- [Changelog](https://github.com/moment/moment/blob/develop/CHANGELOG.md)
- [Commits](https://github.com/moment/moment/compare/2.26.0...2.27.0)
* Bumps [validator](https://github.com/chriso/validator.js) from 13.0.0 to 13.1.1.
- [Release notes](https://github.com/chriso/validator.js/releases)
- [Changelog](https://github.com/validatorjs/validator.js/blob/master/CHANGELOG.md)
- [Commits](https://github.com/chriso/validator.js/compare/13.0.0...13.1.1)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.2.0 to 7.3.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.2.0...v7.3.0)
* Bump eslint from 7.2.0 to 7.3.0
* Bump validator from 13.0.0 to 13.1.1
* Bump moment from 2.26.0 to 2.27.0
* Bumps [eslint-plugin-import](https://github.com/benmosher/eslint-plugin-import) from 2.21.2 to 2.22.0.
- [Release notes](https://github.com/benmosher/eslint-plugin-import/releases)
- [Changelog](https://github.com/benmosher/eslint-plugin-import/blob/master/CHANGELOG.md)
- [Commits](https://github.com/benmosher/eslint-plugin-import/compare/v2.21.2...v2.22.0)
* Bumps [webpack-cli](https://github.com/webpack/webpack-cli) from 3.3.11 to 3.3.12.
- [Release notes](https://github.com/webpack/webpack-cli/releases)
- [Changelog](https://github.com/webpack/webpack-cli/blob/v3.3.12/CHANGELOG.md)
- [Commits](https://github.com/webpack/webpack-cli/compare/v3.3.11...v3.3.12)
* Bumps [eslint](https://github.com/eslint/eslint) from 7.3.0 to 7.3.1.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.3.0...v7.3.1)
* Bumps [eslint-plugin-react](https://github.com/yannickcr/eslint-plugin-react) from 7.20.0 to 7.20.1.
- [Release notes](https://github.com/yannickcr/eslint-plugin-react/releases)
- [Changelog](https://github.com/yannickcr/eslint-plugin-react/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yannickcr/eslint-plugin-react/compare/v7.20.0...v7.20.1)
* Bump eslint-plugin-import from 2.21.2 to 2.22.0
* Bump eslint from 7.3.0 to 7.3.1
* Bump eslint-plugin-react from 7.20.0 to 7.20.1
* Bump webpack-cli from 3.3.11 to 3.3.12
* Bumps [copy-webpack-plugin](https://github.com/webpack-contrib/copy-webpack-plugin) from 6.0.2 to 6.0.3.
- [Release notes](https://github.com/webpack-contrib/copy-webpack-plugin/releases)
- [Changelog](https://github.com/webpack-contrib/copy-webpack-plugin/blob/master/CHANGELOG.md)
- [Commits](https://github.com/webpack-contrib/copy-webpack-plugin/compare/v6.0.2...v6.0.3)
* Bumps [lint-staged](https://github.com/okonet/lint-staged) from 10.2.10 to 10.2.11.
- [Release notes](https://github.com/okonet/lint-staged/releases)
- [Commits](https://github.com/okonet/lint-staged/compare/v10.2.10...v10.2.11)
* Bumps [autoprefixer](https://github.com/postcss/autoprefixer) from 9.8.0 to 9.8.4.
- [Release notes](https://github.com/postcss/autoprefixer/releases)
- [Changelog](https://github.com/postcss/autoprefixer/blob/master/CHANGELOG.md)
- [Commits](https://github.com/postcss/autoprefixer/compare/9.8.0...9.8.4)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.10.2 to 7.10.4.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.10.4/packages/babel-preset-env)
* Bump autoprefixer from 9.8.0 to 9.8.4
* Bump @babel/preset-env from 7.10.2 to 7.10.4
* Bump copy-webpack-plugin from 6.0.2 to 6.0.3
* Bump lint-staged from 10.2.10 to 10.2.11
* Bumps [react-big-calendar](https://github.com/intljusticemission/react-big-calendar) from 0.25.0 to 0.26.0.
- [Release notes](https://github.com/intljusticemission/react-big-calendar/releases)
- [Changelog](https://github.com/jquense/react-big-calendar/blob/master/CHANGELOG.md)
- [Commits](https://github.com/intljusticemission/react-big-calendar/compare/v0.25.0...v0.26.0)
* Bumps [superagent](https://github.com/visionmedia/superagent) from 5.2.2 to 5.3.1.
- [Release notes](https://github.com/visionmedia/superagent/releases)
- [Changelog](https://github.com/visionmedia/superagent/blob/master/HISTORY.md)
- [Commits](https://github.com/visionmedia/superagent/compare/v5.2.2...v5.3.1)
* Bumps node from 14.4.0-alpine to 14.5.0-alpine.
* Bumps [@babel/plugin-proposal-class-properties](https://github.com/babel/babel/tree/HEAD/packages/babel-plugin-proposal-class-properties) from 7.10.1 to 7.10.4.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.10.4/packages/babel-plugin-proposal-class-properties)
* Bumps [lodash](https://github.com/lodash/lodash) from 4.17.15 to 4.17.19.
- [Release notes](https://github.com/lodash/lodash/releases)
- [Commits](https://github.com/lodash/lodash/compare/4.17.15...4.17.19)
* Bumps nginx from 1.19.0-alpine to 1.19.1-alpine.
* Bumps [victory](https://github.com/formidablelabs/victory) from 34.3.11 to 35.0.5.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v34.3.11...v35.0.5)
* Bumps [elliptic](https://github.com/indutny/elliptic) from 6.5.2 to 6.5.3.
- [Release notes](https://github.com/indutny/elliptic/releases)
- [Commits](https://github.com/indutny/elliptic/compare/v6.5.2...v6.5.3)
* Bump react-big-calendar from 0.25.0 to 0.26.0
* Bump superagent from 5.2.2 to 5.3.1
* Bump node from 14.4.0-alpine to 14.5.0-alpine
* Bump @babel/plugin-proposal-class-properties from 7.10.1 to 7.10.4
* Bump lodash from 4.17.15 to 4.17.19
* Bump nginx from 1.19.0-alpine to 1.19.1-alpine
* Bump victory from 34.3.11 to 35.0.5
* Bump elliptic from 6.5.2 to 6.5.3
* Bumps node from 14.5.0-alpine to 14.7.0-alpine.
* Bumps [react-dropzone](https://github.com/react-dropzone/react-dropzone) from 11.0.1 to 11.0.2.
- [Release notes](https://github.com/react-dropzone/react-dropzone/releases)
- [Commits](https://github.com/react-dropzone/react-dropzone/compare/v11.0.1...v11.0.2)
* Bump react-dropzone from 11.0.1 to 11.0.2
* Bump node from 14.5.0-alpine to 14.7.0-alpine
* Bumps [react-ga](https://github.com/react-ga/react-ga) from 3.0.0 to 3.1.2.
- [Release notes](https://github.com/react-ga/react-ga/releases)
- [Commits](https://github.com/react-ga/react-ga/compare/v3.0.0...v3.1.2)
* Bumps [victory](https://github.com/formidablelabs/victory) from 34.3.11 to 35.0.8.
- [Release notes](https://github.com/formidablelabs/victory/releases)
- [Changelog](https://github.com/FormidableLabs/victory/blob/main/CHANGELOG.md)
- [Commits](https://github.com/formidablelabs/victory/compare/v34.3.11...v35.0.8)
* Bumps [@mdi/js](https://github.com/Templarian/MaterialDesign-JS) from 5.3.45 to 5.4.55.
- [Release notes](https://github.com/Templarian/MaterialDesign-JS/releases)
- [Commits](https://github.com/Templarian/MaterialDesign-JS/compare/v5.3.45...v5.4.55)
* Bumps [@stripe/stripe-js](https://github.com/stripe/stripe-js) from 1.7.0 to 1.8.0.
- [Release notes](https://github.com/stripe/stripe-js/releases)
- [Commits](https://github.com/stripe/stripe-js/compare/v1.7.0...v1.8.0)
* Bumps node from 14.7.0-alpine to 14.8.0-alpine.
* Bumps nginx from 1.19.1-alpine to 1.19.2-alpine.
* Bump nginx from 1.19.1-alpine to 1.19.2-alpine
* Bump node from 14.7.0-alpine to 14.8.0-alpine
* Bump victory from 34.3.11 to 35.0.8
* Bump react-ga from 3.0.0 to 3.1.2
* Bump @stripe/stripe-js from 1.7.0 to 1.8.0
* Bump @mdi/js from 5.3.45 to 5.4.55
* Bumps [@mdi/js](https://github.com/Templarian/MaterialDesign-JS) from 5.4.55 to 5.5.55.
- [Release notes](https://github.com/Templarian/MaterialDesign-JS/releases)
- [Commits](https://github.com/Templarian/MaterialDesign-JS/compare/v5.4.55...v5.5.55)
* Bump @mdi/js from 5.4.55 to 5.5.55
* Bumps [axios](https://github.com/axios/axios) from 0.19.2 to 0.20.0.
- [Release notes](https://github.com/axios/axios/releases)
- [Changelog](https://github.com/axios/axios/blob/master/CHANGELOG.md)
- [Commits](https://github.com/axios/axios/compare/v0.19.2...v0.20.0)
* Bumps [react-dropzone](https://github.com/react-dropzone/react-dropzone) from 11.0.2 to 11.0.3.
- [Release notes](https://github.com/react-dropzone/react-dropzone/releases)
- [Commits](https://github.com/react-dropzone/react-dropzone/compare/v11.0.2...v11.0.3)
* Bumps [@babel/preset-env](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-env) from 7.10.4 to 7.11.0.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.11.0/packages/babel-preset-env)
* Bumps [jest-resolve](https://github.com/facebook/jest/tree/HEAD/packages/jest-resolve) from 26.0.1 to 26.4.0.
- [Release notes](https://github.com/facebook/jest/releases)
- [Changelog](https://github.com/facebook/jest/blob/master/CHANGELOG.md)
- [Commits](https://github.com/facebook/jest/commits/v26.4.0/packages/jest-resolve)
* Bump jest-resolve from 26.0.1 to 26.4.0
* Bump @babel/preset-env from 7.10.4 to 7.11.0
* Bump react-dropzone from 11.0.2 to 11.0.3
* Bump axios from 0.19.2 to 0.20.0
* Bumps node from 14.8.0-alpine to 14.9.0-alpine.
* Bumps [eslint](https://github.com/eslint/eslint) from 7.3.1 to 7.7.0.
- [Release notes](https://github.com/eslint/eslint/releases)
- [Changelog](https://github.com/eslint/eslint/blob/master/CHANGELOG.md)
- [Commits](https://github.com/eslint/eslint/compare/v7.3.1...v7.7.0)
* Bumps [@babel/preset-react](https://github.com/babel/babel/tree/HEAD/packages/babel-preset-react) from 7.10.1 to 7.10.4.
- [Release notes](https://github.com/babel/babel/releases)
- [Changelog](https://github.com/babel/babel/blob/main/CHANGELOG.md)
- [Commits](https://github.com/babel/babel/commits/v7.10.4/packages/babel-preset-react)
* Bumps [yarn](https://github.com/yarnpkg/yarn) from 1.22.4 to 1.22.5.
- [Release notes](https://github.com/yarnpkg/yarn/releases)
- [Changelog](https://github.com/yarnpkg/yarn/blob/master/CHANGELOG.md)
- [Commits](https://github.com/yarnpkg/yarn/compare/v1.22.4...v1.22.5)
* Bump @babel/preset-react from 7.10.1 to 7.10.4
* Bump yarn from 1.22.4 to 1.22.5
* Bump eslint from 7.3.1 to 7.7.0
* Bump node from 14.8.0-alpine to 14.9.0-alpine
* Bumps [enzyme-adapter-react-16](https://github.com/enzymejs/enzyme/tree/HEAD/packages/enzyme-adapter-react-16) from 1.15.2 to 1.15.4.
- [Release notes](https://github.com/enzymejs/enzyme/releases)
- [Changelog](https://github.com/enzymejs/enzyme/blob/master/CHANGELOG.md)
- [Commits](https://github.com/enzymejs/enzyme/commits/enzyme-adapter-react-16@1.15.4/packages/enzyme-adapter-react-16)
* Bump enzyme-adapter-react-16 from 1.15.2 to 1.15.4

#### integration (2.5.0)

New changes in integration since 2.4.0:

* docker compose: minio now restart on-failure
* Restore docker-compose.storage.s3.yml
* upgrade MongoDB from version 3.6 to version 4.4 (latest stable)
* Upgrade deployments to 2.1.0.
* Upgrade deployments-enterprise to 2.1.0.
* Upgrade deviceauth to 2.4.0.
* Upgrade gui to 2.5.0.
* Upgrade inventory to 2.1.0.
* Upgrade inventory-enterprise to 2.1.0.
* Upgrade mender to 2.4.0.
* Upgrade mender-api-gateway-docker to 2.3.0.
* Upgrade mender-cli to 1.5.0.
* Add mtls-ambassador 1.0.0.
* Upgrade tenantadm to 2.1.0.
* Upgrade useradm to 1.12.0.
* Upgrade useradm-enterprise to 1.12.0.
* Upgrade workflows to 1.2.0.
* Upgrade workflows-enterprise to 1.2.0.
* Aggregated Dependabot Changelogs:
* Bumps [requests](https://github.com/psf/requests) from 2.22.0 to 2.23.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.22.0...v2.23.0)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.42.0 to 2.48.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.42.0...v2.48.0)
* Bumps [pillow](https://github.com/python-pillow/Pillow) from 7.0.0 to 7.1.2.
- [Release notes](https://github.com/python-pillow/Pillow/releases)
- [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
- [Commits](https://github.com/python-pillow/Pillow/compare/7.0.0...7.1.2)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.0.1 to 2.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.0.1...v2.1.1)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.25.4 to 1.26.0.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/master/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.25.4...1.26.0)
* Bumps [requests](https://github.com/psf/requests) from 2.22.0 to 2.23.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.22.0...v2.23.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.0.1 to 2.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.0.1...v2.1.1)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.3.4 to 5.4.3.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.3.4...5.4.3)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.3.4 to 5.4.3.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.3.4...5.4.3)
* : Bump pytest from 5.3.4 to 5.4.3 in /backend-tests
* Bump pytest from 5.3.4 to 5.4.3 in /tests/requirements
* Bumps [cryptography](https://github.com/pyca/cryptography) from 2.8 to 2.9.2.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/2.8...2.9.2)
* Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.6.0 to 2.7.1.
- [Release notes](https://github.com/paramiko/paramiko/releases)
- [Changelog](https://github.com/paramiko/paramiko/blob/master/NEWS)
- [Commits](https://github.com/paramiko/paramiko/compare/2.6.0...2.7.1)
* Bump cryptography from 2.8 to 2.9.2 in /backend-tests
* Bump paramiko from 2.6.0 to 2.7.1 in /tests/requirements
* Bumps [pillow](https://github.com/python-pillow/Pillow) from 7.1.2 to 7.2.0.
- [Release notes](https://github.com/python-pillow/Pillow/releases)
- [Changelog](https://github.com/python-pillow/Pillow/blob/master/CHANGES.rst)
- [Commits](https://github.com/python-pillow/Pillow/compare/7.1.2...7.2.0)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.26.0 to 1.26.2.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.26.2/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.26.0...1.26.2)
* Bump docker-compose from 1.26.0 to 1.26.2 in /tests/requirements
* Bump pillow from 7.1.2 to 7.2.0 in /backend-tests
* Bumps [requests](https://github.com/psf/requests) from 2.23.0 to 2.24.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.23.0...v2.24.0)
* Bumps [requests](https://github.com/psf/requests) from 2.23.0 to 2.24.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.23.0...v2.24.0)
* Bump requests from 2.23.0 to 2.24.0 in /tests/requirements
* Bump requests from 2.23.0 to 2.24.0 in /backend-tests
* Bumps [cryptography](https://github.com/pyca/cryptography) from 2.9.2 to 3.0.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/2.9.2...3.0)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.48.0 to 2.49.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.48.0...v2.49.0)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.10.1 to 3.11.0.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.10.1...3.11.0)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.4.3 to 6.0.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.4.3...6.0.1)
* Bumps [pyotp](https://github.com/pyotp/pyotp) from 2.3.0 to 2.4.0.
- [Release notes](https://github.com/pyotp/pyotp/releases)
- [Changelog](https://github.com/pyauth/pyotp/blob/master/Changes.rst)
- [Commits](https://github.com/pyotp/pyotp/compare/v2.3.0...v2.4.0)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.10.1 to 3.11.0.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.10.1...3.11.0)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.4.3 to 6.0.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.4.3...6.0.1)
* Bumps [stripe](https://github.com/stripe/stripe-python) from 2.49.0 to 2.50.0.
- [Release notes](https://github.com/stripe/stripe-python/releases)
- [Changelog](https://github.com/stripe/stripe-python/blob/master/CHANGELOG.md)
- [Commits](https://github.com/stripe/stripe-python/compare/v2.49.0...v2.50.0)
* Bump stripe from 2.49.0 to 2.50.0 in /backend-tests
* Bumps [cryptography](https://github.com/pyca/cryptography) from 3.0 to 3.1.
- [Release notes](https://github.com/pyca/cryptography/releases)
- [Changelog](https://github.com/pyca/cryptography/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pyca/cryptography/compare/3.0...3.1)
* Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.7.1 to 2.7.2.
- [Release notes](https://github.com/paramiko/paramiko/releases)
- [Changelog](https://github.com/paramiko/paramiko/blob/master/NEWS)
- [Commits](https://github.com/paramiko/paramiko/compare/2.7.1...2.7.2)
* Bump paramiko from 2.7.1 to 2.7.2 in /tests/requirements
* Bump cryptography from 3.0 to 3.1 in /backend-tests

#### inventory (2.1.0)

New changes in inventory since 2.0.0:

* New endpoints for managing devices' group in bulk.
* Add $nin ("not in") operator for searching devices
* Add status query parameter to GET /groups
* New internal health check and liveliness endpoints
`GET /api/internal/v1/inventory/health`
`GET /api/internal/v1/inventory/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### inventory-enterprise (2.1.0)

New changes in inventory-enterprise since 2.0.0:

* New endpoints for managing devices' group in bulk.
* RBAC dynamic groups
([MEN-3626](https://tracker.mender.io/browse/MEN-3626))
* Introduce the $regex filter operator
* Add $nin ("not in") operator for searching devices
* Add status query parameter to GET /groups
* New internal health check and liveliness endpoints
`GET /api/internal/v1/inventory/health`
`GET /api/internal/v1/inventory/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### mender-api-gateway-docker (2.3.0)

New changes in mender-api-gateway-docker since 2.2.0:

* Return valid JSON documents as error pages' payloads
* , expose password-reset end-points without auth
([MEN-3544](https://tracker.mender.io/browse/MEN-3544), [MEN-3546](https://tracker.mender.io/browse/MEN-3546))

#### mtls-ambassador (1.0.0)

* support ecdsa and ed25519
* management token refresh

#### tenantadm (2.1.0)

New changes in tenantadm since 2.0.0:

* new management end-point to request tenant's cancellation
([MEN-3305](https://tracker.mender.io/browse/MEN-3305))
* Remove mongodb write/read concerns, let the connection string set them
* introduce a new end-point to create trial tenants
([MEN-3613](https://tracker.mender.io/browse/MEN-3613))
* new end-points to upgrade a trial tenant to a paid plan
([MEN-3615](https://tracker.mender.io/browse/MEN-3615))
* internal API end-point to update tenants
([MC-4040](https://tracker.mender.io/browse/MC-4040))
* Store marketing consent from the sign up form in stripe
* OAuth2 signup support for GitHub and Google
* add support for the + character in the email address
([MEN-1969](https://tracker.mender.io/browse/MEN-1969))
* New internal health check and liveliness endpoints
`GET /api/internal/v1/tenantadm/health`
`GET /api/internal/v1/tenantadm/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### useradm (1.12.0)

New changes in useradm since 1.11.0:

* Remove mongodb write concern, let the connection string set them
* add support for the + character in the email address
([MEN-1969](https://tracker.mender.io/browse/MEN-1969))
* New internal health check and liveliness endpoints
`GET /api/internal/v1/useradm/health`
`GET /api/internal/v1/useradm/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### useradm-enterprise (1.12.0)

New changes in useradm-enterprise since 1.11.0:

* Remove mongodb write concern, let the connection string set them
* Remove mongodb write concern, let the connection string set them
* Separate RBAC of visibility and deployments.
([MEN-3629](https://tracker.mender.io/browse/MEN-3629))
* OAuth2: Login using GitHub and Google account
* add support for the + character in the email address
([MEN-1969](https://tracker.mender.io/browse/MEN-1969))
* add support for the + character in the email address
([MEN-1969](https://tracker.mender.io/browse/MEN-1969))
* New internal health check and liveliness endpoints
`GET /api/internal/v1/useradm/health`
`GET /api/internal/v1/useradm/alive`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### workflows (1.2.0)

New changes in workflows since 1.1.0:

* add support for sending html (mime/alternative) messages
([MEN-3509](https://tracker.mender.io/browse/MEN-3509))
* Add Go Template processing of http task's request body
* Add support for yaml workflow definitions
* New internal health check endpoint
`GET /api/internal/v1/workflows/health`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

#### workflows-enterprise (1.2.0)

New changes in workflows-enterprise since 1.1.0:

* Add new workflow cancel_tenant to send cancellation request email
([MEN-3305](https://tracker.mender.io/browse/MEN-3305))
* add support for sending html (mime/alternative) messages
([MEN-3509](https://tracker.mender.io/browse/MEN-3509))
* Add Go Template processing of http task's request body
* Add support for yaml workflow definitions
* new workflow send_password_reset_email for password resets
([MEN-3545](https://tracker.mender.io/browse/MEN-3545))
* New internal health check endpoint
`GET /api/internal/v1/workflows/health`
([MEN-3024](https://tracker.mender.io/browse/MEN-3024))

## Mender 2.4.3

_Released 16.04.2021_

### Changelogs

#### create-artifact-worker (1.0.2)

New changes in create-artifact-worker since 1.0.1:

* bugfix to allow spaces in artifact names
([MEN-4179](https://tracker.mender.io/browse/MEN-4179))
* upgrade mender-artifact to version 3.5.0.
This enables the create-artifact-worker to generate artifacts that
implement the provides and clear provides fields.
([MEN-4409](https://tracker.mender.io/browse/MEN-4409))

#### integration (2.4.3)

New changes in integration since 2.4.2:

* Upgrade create-artifact-worker to 1.0.2.
* Upgrade mender to 2.3.3.
* Upgrade mender-artifact to 3.4.2.
* Upgrade mender-cli to 1.4.1.
## Mender 2.4.2

_Released 01.21.2021_

### Changelogs

#### deployments (2.0.1)

New changes in deployments since 2.0.0:

* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* api: Generate artifact doesn't load entire request upon parsing
* api: Generate artifact endpoint accepts form values with whitespaces

#### deployments-enterprise (2.0.1)

New changes in deployments-enterprise since 2.0.0:

* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* document artifact_provides and artifact_depends in API docs
([MEN-4051](https://tracker.mender.io/browse/MEN-4051))
* api: Generate artifact doesn't load entire request upon parsing
* api: Generate artifact endpoint accepts form values with whitespaces

#### deviceauth (2.3.1)

New changes in deviceauth since 2.3.0:

* ignore tenant claim in single tenant setup
([MEN-3972](https://tracker.mender.io/browse/MEN-3972))

#### integration (2.4.2)

New changes in integration since 2.4.1:

* Upgrade deployments to 2.0.1.
* Upgrade deployments-enterprise to 2.0.1.
* Upgrade deviceauth to 2.3.1.
* Upgrade mender to 2.3.2.
* Upgrade mender-api-gateway-docker to 2.2.1.
* Upgrade mender-artifact to 3.4.1.
* Upgrade useradm to 1.11.1.
* Upgrade useradm-enterprise to 1.11.1.

#### mender-api-gateway-docker (2.2.1)

New changes in mender-api-gateway-docker since 2.2.0:

* restore ALLOWED_ORIGIN_HOSTS regex match when checking Origin
([MEN-4118](https://tracker.mender.io/browse/MEN-4118))

#### useradm (1.11.1)

New changes in useradm since 1.11.0:

* No changes (re-release to follow Enterprise version).

#### useradm-enterprise (1.11.1)

New changes in useradm-enterprise since 1.11.0:

* FIX: Restrict observer role from posting to arbitrary endpoints
* FIX: Protect default roles from fake queries

## Mender 2.4.1

_Released 09.01.2020_

### Changelogs

#### integration (2.4.1)

New changes in integration since 2.4.0:

* Upgrade inventory to 2.0.1.
* Upgrade inventory-enterprise to 2.0.1.
* Aggregated Dependabot Changelogs:
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.3.4 to 5.4.3.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.3.4...5.4.3)
* Bumps [paramiko](https://github.com/paramiko/paramiko) from 2.6.0 to 2.7.1.
- [Release notes](https://github.com/paramiko/paramiko/releases)
- [Changelog](https://github.com/paramiko/paramiko/blob/master/NEWS)
- [Commits](https://github.com/paramiko/paramiko/compare/2.6.0...2.7.1)
* Bumps [pymongo](https://github.com/mongodb/mongo-python-driver) from 3.10.1 to 3.11.0.
- [Release notes](https://github.com/mongodb/mongo-python-driver/releases)
- [Changelog](https://github.com/mongodb/mongo-python-driver/blob/master/doc/changelog.rst)
- [Commits](https://github.com/mongodb/mongo-python-driver/compare/3.10.1...3.11.0)
* Bumps [pytest](https://github.com/pytest-dev/pytest) from 5.4.3 to 6.0.1.
- [Release notes](https://github.com/pytest-dev/pytest/releases)
- [Changelog](https://github.com/pytest-dev/pytest/blob/master/CHANGELOG.rst)
- [Commits](https://github.com/pytest-dev/pytest/compare/5.4.3...6.0.1)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.25.4 to 1.26.0.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/master/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.25.4...1.26.0)
* Bumps [requests](https://github.com/psf/requests) from 2.22.0 to 2.23.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.22.0...v2.23.0)
* Bumps [pytest-html](https://github.com/pytest-dev/pytest-html) from 2.0.1 to 2.1.1.
- [Release notes](https://github.com/pytest-dev/pytest-html/releases)
- [Changelog](https://github.com/pytest-dev/pytest-html/blob/master/CHANGES.rst)
- [Commits](https://github.com/pytest-dev/pytest-html/compare/v2.0.1...v2.1.1)
* Bumps [docker-compose](https://github.com/docker/compose) from 1.26.0 to 1.26.2.
- [Release notes](https://github.com/docker/compose/releases)
- [Changelog](https://github.com/docker/compose/blob/1.26.2/CHANGELOG.md)
- [Commits](https://github.com/docker/compose/compare/1.26.0...1.26.2)
* Bumps [requests](https://github.com/psf/requests) from 2.23.0 to 2.24.0.
- [Release notes](https://github.com/psf/requests/releases)
- [Changelog](https://github.com/psf/requests/blob/master/HISTORY.md)
- [Commits](https://github.com/psf/requests/compare/v2.23.0...v2.24.0)

#### inventory-enterprise (2.0.1)

New changes in inventory-enterprise since 2.0.0:

* Bugfix: Rejected devices remain listed in static
groups, even after rejection.
([MEN-3793](https://tracker.mender.io/browse/MEN-3793))

## Mender 2.4.0

_Released 07.15.2020_

### Changelogs

#### create-artifact-worker (1.0.1)

New changes in create-artifact-worker since 1.0.1b1:

* increase download and upload time-outs to 15 minutes
([MEN-3539](https://tracker.mender.io/browse/MEN-3539))
* handle multiple device types as comma-separated values
([MEN-3771](https://tracker.mender.io/browse/MEN-3771))

New changes in create-artifact-worker since 1.0.0:

* Limit the workflows create-artifact-worker can process

#### deployments (2.0.0)

New changes in deployments since 2.0.0b1:

* Remove mongodb write/read concerns, let the connection string set them

New changes in deployments since 1.9.0:

* New devices API endpoint POST /deployments/next
* Introduce new flow for creating deployments and selecting
deployments for the devices. Device deployments are no longer created
on deployment creation. Device deployments are being created when the
devices are asking for the deployment.
* New method for listing IDs of devices being part of particular deployment.
* GET /deployments returns total count in the header
* add configuration option to enable/disable path-style AWS S3 URIs
([MEN-2499](https://tracker.mender.io/browse/MEN-2499))

#### deployments-enterprise (2.0.0)

New changes in deployments-enterprise since 2.0.0b1:

* Remove mongodb write/read concerns, let the connection string set them

New changes in deployments-enterprise since 1.9.0:

* api: New method for endpoint POST /device/deployments/next
* Support for artifacts provides/depends attributes
* New devices API endpoint POST /deployments/next
* api/http: introduce endpoint for creating dynamic deplyment
* Introduce new flow for creating deployments and selecting
deployments for the devices. Device deployments are no longer created
on deployment creation. Device deployments are being created when the
devices are asking for the deployment.
* New method for listing IDs of devices being part of particular deployment.
* introduce new deployment status - scheduled
Deployment status is "scheduled" when the deployment
contains at least one phase, the first phase contains
start_ts field and the deployment didn't start yet.
Changes:
- introduce new deployment status scheduled;
- adjust status calculation;
* GET /deployments returns total count in the header
* add configuration option to enable/disable path-style AWS S3 URIs
([MEN-2499](https://tracker.mender.io/browse/MEN-2499))

#### deviceauth (2.3.0)

New changes in deviceauth since 2.2.0:

* Remove DEVICEAUTH_MAX_DEVICES_LIMIT_DEFAULT configuration option
* propagate-inventory-statuses command added

#### gui (2.4.0)

New changes in gui since 2.4.0b1:

* fixed an issue that caused unexpected deployment device states to crash the deployment report
* fixed settings availability in OS & onprem-enterprise deployments
* fixed check for group creation on mixed filter scopes & added short explanation

New changes in gui since 2.3.0:

* added artifact metadata to payload view if present
* made recent update times easier to read for devices & deployments
* prevented a redirect after deployment creation
* fixed an issue that would let the user list crash after user removal
* let mender plan be reflected in settings & billing page
* made scheduling deployments an enterprise plan only feature
* made phased deployments an enterprise plan only feature
* ensured deployment report is closed on abort to prevent UI crash
* made artifact dependencies available in expanded artifact details component
* fixed an issue that kept the header information from updating after login
* fixed an issue that prevented deployments from being possible
* reverted limit to 10 most popular device inventory attributes
* Docker HEALTHCHECK added
([MEN-2855](https://tracker.mender.io/browse/MEN-2855))
* refactored group creation dialog to support device additions
* added support for non-expandable device lists
+ improved rendering speed for device lists
* fixed an issue the broke the device auth state refresh on auth update
* added possibility to enable retries for deployments on deployment creation
* added filtering as you type based on client side store data
* added filtering possibility to pending & rejected device lists
* fixed a bug that prevented pagination in non-accepted device lists
* fixed page setting through custom entry in device lists
* allowed filters to be stored & using v2 inventory API
* allowed filtered to also use pagination
* improved device retrieval performance on group & filter changes
* prevented an error that could crash the ui when a device hasn't received status information
* added recently used device filters functionality
* fixed an issue that prevented device identity attributes from being populated
* fixed an error that prevented device lists from updating after authset dismissal
* fixed deb package installation instructions not containing package version
* improved deployments view to show scheduled deployments as well
* fixed an issue that could have prevented the deployment report from opening
* fixed a bug that prevented a group from being added after deletion
* fixed an issue that prevented group creation in short succession
* reduced device calls made in deployment report
by reusing existing device information if possible
* Make GUI aware that we have a pre-converted image for Raspberry Pi 4.
* refactored deployment counting to use count header, reducing request load
* fixed an issue that might prevent OS users from changing their settings
* fixed identity attribute filtering on authorized devices
([MEN-3517](https://tracker.mender.io/browse/MEN-3517))
* enabled automatic selection on filter autocomplete
([MEN-3518](https://tracker.mender.io/browse/MEN-3518))
* ensured onboarding tooltip shows up after custom artifact is uploaded

#### integration (2.4.0)

New changes in integration since 2.4.0b1:

* Restore docker-compose.storage.s3.yml
* Upgrade create-artifact-worker to 1.0.1.
* Upgrade deployments to 2.0.0.
* Upgrade deployments-enterprise to 2.0.0.
* Upgrade deviceauth to 2.3.0.
* Upgrade gui to 2.4.0.
* Upgrade inventory to 2.0.0.
* Upgrade inventory-enterprise to 2.0.0.
* Upgrade mender to 2.3.0.
* Upgrade mender-api-gateway-docker to 2.2.0.
* Upgrade mender-artifact to 3.4.0.
* Upgrade mender-cli to 1.4.0.
* Upgrade tenantadm to 2.0.0.
* Upgrade useradm to 1.11.0.
* Upgrade useradm-enterprise to 1.11.0.
* Upgrade workflows to 1.1.0.
* Upgrade workflows-enterprise to 1.1.0.

New changes in integration since 2.3.0:

* Fix broken artifact creation in the UI.
([MEN-3166](https://tracker.mender.io/browse/MEN-3166))
* device-auth: call mender-workflows-server
([MEN-2963](https://tracker.mender.io/browse/MEN-2963))
* use workflows-server in tenantadm
([MEN-2965](https://tracker.mender.io/browse/MEN-2965))
* Update backend images to use version mender-master
Introducing a new versioning schema, from this release on the Docker
images for the backend repositories will be published in their
corresponding registries following the Mender product version.
This means tags `<service>:mender-<mender-version>` instead of the old
tags `<service>:<service-version>`, which will eventually be deprecated.
([MEN-3466](https://tracker.mender.io/browse/MEN-3466))
* Upgrade create-artifact-worker to 1.0.1b1.
* Upgrade deployments to 2.0.0b1.
* Upgrade deployments-enterprise to 2.0.0b1.
* Upgrade deviceauth to 2.3.0b1.
* Upgrade gui to 2.4.0b1.
* Upgrade inventory to 2.0.0b1.
* Add inventory-enterprise 2.0.0b1.
* Upgrade mender to 2.3.0b1.
* Upgrade mender-api-gateway-docker to 2.2.0b1.
* Upgrade mender-artifact to 3.4.0b1.
* Upgrade mender-cli to 1.4.0b1.
* Upgrade tenantadm to 2.0.0b1.
* Upgrade useradm to 1.11.0b1.
* Upgrade useradm-enterprise to 1.11.0b1.
* Upgrade workflows to 1.1.0b1.
* Add workflows-enterprise 1.1.0b1.

#### inventory (2.0.0)

New changes in inventory since 1.7.0:

* New v2/filters/search endpoint.

#### inventory-enterprise (2.0.0)

* Introduced inventory-enterprise.

#### mender-api-gateway-docker (2.2.0)

New changes in mender-api-gateway-docker since 2.2.0b1:

* Return valid JSON documents as error pages' payloads
* Fix Artifact upload timeout bug

New changes in mender-api-gateway-docker since 2.1.0:

* RBAC: per device group restrictions support
([MEN-3240](https://tracker.mender.io/browse/MEN-3240))
* Increased timeouts to handle longer requests processing.

#### tenantadm (2.0.0)

New changes in tenantadm since 2.0.0b1:

* Remove mongodb write/read concerns, let the connection string set them

New changes in tenantadm since 1.1.0:

* docs/internal: extend tenant object with "plan" field
* Use workflows instead of conductor for API orchestration
* New database schema (1.4.0), avoid the creation of multiple (inactive) organization with the same username
* Make create-org plan default to enterprise
* Make device limits configurable and set enterprise default: no limit
* Fix: Delete all tenants' users on tenant deletion

#### useradm (1.11.0)

New changes in useradm since 1.11.0b1:

* Remove mongodb write concern, let the connection string set them

New changes in useradm since 1.10.0:

* Routine version update to stay in sync with Enterprise.

#### useradm-enterprise (1.11.0)

New changes in useradm-enterprise since 1.11.0b1:

* Remove mongodb write concern, let the connection string set them

New changes in useradm-enterprise since 1.10.0:

* extend UserUpdate endpoint with array of roles
([MEN-3451](https://tracker.mender.io/browse/MEN-3451))
* Allow updating of roles via UpdateUser
([MEN-3452](https://tracker.mender.io/browse/MEN-3452))
* RBAC: per device group restrictions support
([MEN-3240](https://tracker.mender.io/browse/MEN-3240))
* set-roles command creates default roles
* Roles management API calls
([MEN-3447](https://tracker.mender.io/browse/MEN-3447))

#### workflows (1.1.0)

New changes in workflows since 1.0.0:

* decommision and provision device workflows
([MEN-2963](https://tracker.mender.io/browse/MEN-2963))
* replace all values in processJobString
([MEN-2965](https://tracker.mender.io/browse/MEN-2965))
* list-jobs comand, extra logging and go fmt

#### workflows-enterprise (1.1.0)

* Introduced workflows-enterprise.

## Mender 2.3.1

_Released 07.15.2020_

### Changelogs

#### create-artifact-worker (1.0.1)

New changes in create-artifact-worker since 1.0.0:

* Limit the workflows create-artifact-worker can process
* increase download and upload time-outs to 15 minutes
([MEN-3539](https://tracker.mender.io/browse/MEN-3539))
* handle multiple device types as comma-separated values
([MEN-3771](https://tracker.mender.io/browse/MEN-3771))

#### gui (2.3.1)

New changes in gui since 2.3.0:

* fixed deb package installation instructions not containing package version

#### integration (2.3.1)

New changes in integration since 2.3.0:

* Update the data migration scripts
* Restore docker-compose.storage.s3.yml
* Upgrade create-artifact-worker to 1.0.1.
* Upgrade gui to 2.3.1.
* Upgrade mender to 2.2.1.
* Upgrade mender-artifact to 3.3.1.
## Mender 2.3.0

_Released 03.05.2020_

### Changelogs

#### deployments (1.9.0)

New changes in deployments since 1.8.1:

* run migrations on startup like other services do
([MC-1144](https://tracker.mender.io/browse/MC-1144))
* fix device count for get deployment id
* Set a timeout (5 seconds) for CreateBucket at start up
* index deployments database
([MEN-2019](https://tracker.mender.io/browse/MEN-2019))
* store: Migrate to official MongoDB driver

#### deployments-enterprise (1.9.0)

New changes in deployments-enterprise since 1.8.1:

* Disallow empty batches in phased rollouts
Previously there was a possibility to end up with an empty batch, due
to the formula used in the calculation for the number of devices which
is based on extracting a percentage number of devices from the total. Thus
if the total is so small, that a percentage below some number rounds to zero,
the batch would be empty. Now that same input will return an error.
([MEN-2810](https://tracker.mender.io/browse/MEN-2810))
* FIX: Concurrent updates to phase device counter are made atomic
* run migrations on startup like other services do
([MC-1144](https://tracker.mender.io/browse/MC-1144))
* fix device count for get deployment id
* Migration to official mongodb driver
* Set a timeout (5 seconds) for CreateBucket at start up
* index deployments database
([MEN-2019](https://tracker.mender.io/browse/MEN-2019))

#### deviceauth (2.2.0)

New changes in deviceauth since 2.1.0:

* Return device id to a POST /devauth/devices call
([MEN-2605](https://tracker.mender.io/browse/MEN-2605))
* additional mongodb index added
* store/mongo: migrate to official mongodb driver

#### gui (2.3.0)

New changes in gui since 2.3.0b1:

* ensured deployment report is closed on abort to prevent UI crash

New changes in gui since 2.2.1:

* fixed empty userData on edit, causing blank ui fields in settings & header
* fixed persistence of helptip dismissal during onboarding
* fixed regression: filtered on device-type before deployment
* ensured device groups are sorted when retrieved from backend
* added device status inidicator in devicelist
* added billing information page to display current & past billing status
* included inprogress deployments in progress visualisation
* fixed device filtering by url parameter
* fixed deployment device list pagination & device id display
* made deployments refresh more frequently if appropriate
* made selected device id show up when settings dialog is opened
* fixed an issue that caused the proper error to be hidden when an artifact could not be changed
* adjusted deployment report to improve release name readability
* fixed an issue that broke the deployments list alignment
* made releaseslist sortable
* enabled release filtering by name, description & device types
* added additional onboarding steps to ease update artifact generation
* fixed an issue that prevented the staying logged in functionality from working
* prevented a redirect after deployment creation

#### integration (2.3.0)

New changes in integration since 2.3.0b1:

* Fix broken artifact creation in the UI.
([MEN-3166](https://tracker.mender.io/browse/MEN-3166))
* Upgrade create-artifact-worker to 1.0.0.
* Upgrade deployments to 1.9.0.
* Upgrade deployments-enterprise to 1.9.0.
* Upgrade deviceauth to 2.2.0.
* Upgrade gui to 2.3.0.
* Upgrade inventory to 1.7.0.
* Upgrade mender to 2.2.0.
* Upgrade mender-api-gateway-docker to 2.1.0.
* Upgrade mender-artifact to 3.3.0.
* Upgrade mender-cli to 1.3.0.
* Upgrade mender-conductor to 1.6.0.
* Upgrade mender-conductor-enterprise to 1.6.0.
* Upgrade tenantadm to 1.1.0.
* Upgrade useradm to 1.10.0.
* Upgrade useradm-enterprise to 1.10.0.
* Upgrade workflows to 1.0.0.

New changes in integration since 2.2.1:

* Fix issue when demo script exists abruptly on user request
for logs. The issue only showed up when the folder name contained "-"
or "." characters.
* Add enterprise enabling flag to enterprise composition GUI
container, so that the enterprise features are shown in the Frontend.
* Fix - Make sure the demo-script subprocess has a stdin fd
([MEN-2836](https://tracker.mender.io/browse/MEN-2836))
* Fix - Create explicit exitcond for the demo setup fixture
([MEN-2836](https://tracker.mender.io/browse/MEN-2836))
* Change Enterprise Docker links to registry.mender.io.
This will be our gateway to serve the Enterprise images, not Docker
Hub. Those who are using Enterprise will need to log into this
gateway:
```
docker login -u $USERNAME registry.mender.io
```
where `$USERNAME` is the username given to you from Northern.tech. You
will be prompted for the password.
* Verify that empty batches returns a 400 error
Added a test for verifying that deployments-enterprise returns a 400 error
in case of the number of devices in a batch being empty due to rounding
errors in relation to the formula used for determining the number of devices
in a batch. ([MEN-2838](https://tracker.mender.io/browse/MEN-2838))
* Backend Integration tests always print "tests failed"; fix.
* Remove the Python dependency in the demo script
Remove the Python dependency in the demo script, to decrease the dependency
surface of the demo script.
Now the Mender-Artifact and Mender versions are parsed from the
docker-compose.client.yml and other-components.yml files through a simple AWK
script instead.
([MEN-2817](https://tracker.mender.io/browse/MEN-2817))
* Unskip the Pre-Auth tests
([MEN-1797](https://tracker.mender.io/browse/MEN-1797))
* Enable logging for minio
([MEN-2922](https://tracker.mender.io/browse/MEN-2922))
* [tests/run.sh] Enable passing on quoted arguments to pytest
* Run workflows with automigrate in production
([QA-139](https://tracker.mender.io/browse/QA-139))
* workflows server fixing demo command
([QA-139](https://tracker.mender.io/browse/QA-139))
* Upgrade elasticsearch to version 6
([MEN-2985](https://tracker.mender.io/browse/MEN-2985))
* Fix setup for running without SSL termination
* Add create-artifact-worker 1.0.0b1.
* Upgrade deployments to 1.9.0b1.
* Upgrade deployments-enterprise to 1.9.0b1.
* Upgrade deviceauth to 2.2.0b1.
* Upgrade gui to 2.3.0b1.
* Upgrade inventory to 1.7.0b1.
* Upgrade mender to 2.2.0b1.
* Upgrade mender-api-gateway-docker to 2.1.0b1.
* Upgrade mender-artifact to 3.3.0b1.
* Upgrade mender-cli to 1.3.0b1.
* Upgrade mender-conductor to 1.6.0b1.
* Upgrade mender-conductor-enterprise to 1.6.0b1.
* Upgrade tenantadm to 1.1.0b1.
* Upgrade useradm to 1.10.0b1.
* Upgrade useradm-enterprise to 1.10.0b1.
* Add workflows 1.0.0b1.

#### inventory (1.7.0)

New changes in inventory since 1.6.0:

* support for new mongo-driver
([MEN-2454](https://tracker.mender.io/browse/MEN-2454), [MEN-2801](https://tracker.mender.io/browse/MEN-2801))

#### mender-api-gateway-docker (2.1.0)

New changes in mender-api-gateway-docker since 2.0.0:

* ssl_trusted_certificate added
* SSL termination can be turned off via environment variable

#### mender-conductor (1.6.0)

New changes in mender-conductor since 1.5.0:

* Bugfixes for send_email conductor worker
* Prepare ES6 enabled conductor image
([MC-1296](https://tracker.mender.io/browse/MC-1296), [MEN-2987](https://tracker.mender.io/browse/MEN-2987))

#### mender-conductor-enterprise (1.6.0)

New changes in mender-conductor-enterprise since 1.5.0:

* Bugfixes for prepare_org_welcome_email conductor worker

#### tenantadm (1.1.0)

New changes in tenantadm since 1.0.0:

* stripe-go library updated
* api/http: New endpoint for creating inactive organization.
* Endpoint for removing inactive organization
* api/http: management endpoint for activating organization and updating org CC info
* store: Update to official mongodb driver

#### useradm (1.10.0)

New changes in useradm since 1.9.1:

* store/mongo: handle mongodb client creation error

#### useradm-enterprise (1.10.0)

New changes in useradm-enterprise since 1.9.1:

* Support for older Google authenticators on iOS, trimming secret length
* FIX: Create user panics when tenant-id is not specified
* store/mongo: handle mongodb client creation error

#### workflows (1.0.0)

* Refactor repo and added metadata endpoints
* docker: Initialized docker files workflows
* fixing entrypoint to match other services
([QA-139](https://tracker.mender.io/browse/QA-139))
* default mongo url fix
([MEN-3060](https://tracker.mender.io/browse/MEN-3060))

## Mender 2.2.2

_Released 03.05.2020_

### Changelogs

#### gui (2.2.2)

New changes in gui since 2.2.1:

* fix: removed superfluous " around tenant token in device config code
* Fix for changing page length for pagination of rejected and preauth devices
* fixed deploymentdevicelist lacking device identity information
* fixed device list refresh after page length change in deployment devicelist
* fixed an issue that prevented the staying logged in functionality from working

#### integration (2.2.2)

New changes in integration since 2.2.1:

* Upgrade gui to 2.2.2.
* Upgrade mender to 2.1.3.
## Mender 2.2.1

_Released 12.05.2019_

### Changelogs

#### deployments (1.8.1)

New changes in deployments since 1.8.0:

* run migrations on startup like other services do
([MC-1144](https://tracker.mender.io/browse/MC-1144))
* index deployments database
([MEN-2019](https://tracker.mender.io/browse/MEN-2019))
* added unit tests: indices created.
([MEN-2019](https://tracker.mender.io/browse/MEN-2019))

#### deployments-enterprise (1.8.1)

New changes in deployments-enterprise since 1.8.0:

* run migrations on startup like other services do
([MC-1144](https://tracker.mender.io/browse/MC-1144))
* index deployments database
([MEN-2019](https://tracker.mender.io/browse/MEN-2019))
* added unit tests: indices created.
([MEN-2019](https://tracker.mender.io/browse/MEN-2019))

#### gui (2.2.1)

New changes in gui since 2.2.0:

* fixed empty userData on edit, causing blank ui fields in settings & header
* fixed persistence of helptip dismissal during onboarding
* fixed regression: filtered on device-type before deployment
* ensured device groups are sorted when retrieved from backend

#### integration (2.2.1)

New changes in integration since 2.2.0:

* Upgrade deployments to 1.8.1.
* Upgrade deployments-enterprise to 1.8.1.
* Upgrade gui to 2.2.1.
* Upgrade mender to 2.1.2.
* Upgrade mender-artifact to 3.2.1.
* Upgrade useradm to 1.9.1.
* Upgrade useradm-enterprise to 1.9.1.

#### useradm-enterprise (1.9.1)

New changes in useradm-enterprise since 1.9.0:

* Support for older Google authenticators on iOS, trimming secret length
* Two factor authentication API docs
([MEN-2884](https://tracker.mender.io/browse/MEN-2884))

## Mender 2.2.0

_Released 10.23.2019_

### Changelogs

#### deployments (1.8.0)

New changes in deployments since 1.7.1:

* Fix "unexpected EOF" errors when the source of the artifact
is a slow network stream.
* Fix spurious upload errors due to wrong EOF handling.
* Fix inability to resume partial migration.

#### deployments-enterprise (1.8.0)

New changes in deployments-enterprise since 1.8.0b1:

* Disallow empty batches in phased rollouts
Previously there was a possibility to end up with an empty batch, due
to the formula used in the calculation for the number of devices which
is based on extracting a percentage number of devices from the total. Thus
if the total is so small, that a percentage below some number rounds to zero,
the batch would be empty. Now that same input will return an error.
([MEN-2810](https://tracker.mender.io/browse/MEN-2810))

#### deviceauth (2.1.0)

New changes in deviceauth since 2.1.0b1:

* additional mongodb index added

New changes in deviceauth since 2.0.0:

* Add support for default tenant token.
It can be used to allow devices that don't have a tenant token to be
allowed into a specific tenant's list of devices. Enable it either
using the `DEVICEAUTH_DEFAULT_TENANT_TOKEN` environment variable, or
the `default_tenant_token` setting in `config.yaml`.
([MEN-2705](https://tracker.mender.io/browse/MEN-2705), [MEN-2706](https://tracker.mender.io/browse/MEN-2706))

#### gui (2.2.0)

New changes in gui since 2.2.0b1:

* disabled onboarding steps in enterprise environments
* added frontend validation to disable empty batches in phased deployments
([MEN-2820](https://tracker.mender.io/browse/MEN-2820))
* prevented an error in finished deployments view
* fixed phased deployment progress calculation
* added support for raspberrypi4 during onboarding
* moved retry deployment to use createdeployment dialog for review
* Fixed a bug that broke the pagination in the finished deployments list
* added 2fa setup validation step
* added possibility to select previous deployment patterns
* disabled browser suggestions on autoselects
* added starttime column to deployments list in enterprise

New changes in gui since 2.1.0:

* limited height of large select lists to prevent them from hiding input
* ensured artifact & group sort order during deployment scheduling
* added closed feature notifications to show in open source UI
* Updated deployment creation UI to wizard for phased deployments

#### integration (2.2.0)

New changes in integration since 2.2.0b1:

* Fix - Create explicit exitcond for the demo setup fixture
([MEN-2836](https://tracker.mender.io/browse/MEN-2836))
* Change Enterprise Docker links to registry.mender.io.
This will be our gateway to serve the Enterprise images, not Docker
Hub. Those who are using Enterprise will need to log into this
gateway:
```
docker login -u $USERNAME registry.mender.io
```
where `$USERNAME` is the username given to you from Northern.tech. You
will be prompted for the password.
* Add enterprise enabling flag to enterprise composition GUI
container, so that the enterprise features are shown in the Frontend.
* Upgrade deployments to 1.8.0.
* Upgrade deployments-enterprise to 1.8.0.
* Upgrade deviceauth to 2.1.0.
* Upgrade gui to 2.2.0.
* Upgrade mender-artifact to 3.2.0.
* Upgrade mender-conductor to 1.5.0.
* Upgrade mender-conductor-enterprise to 1.5.0.
* Upgrade tenantadm to 1.0.0.
* Upgrade useradm to 1.9.0.
* Upgrade useradm-enterprise to 1.9.0.
* Fix - Make sure the demo-script subprocess has a stdin fd
([MEN-2836](https://tracker.mender.io/browse/MEN-2836))

New changes in integration since 2.1.0:

* remove default conductor config file
* Fix error: `No such container: integration-2.1.0b1_mender-useradm_1`
* Introduced `enterprise.yml` template in production
directory to install an Enterprise backend server.
* The old `template` directory has been replaced with a
dedicated `production` directory, and templates are now provided as
single files with the `.template` suffix instead. These should be
copied to their non-`.template` location before being used. The `run`
script should no longer be copied, and if it already exists in the
`production` directory before merging this change, it should be
removed before attempting to merge or rebase.
* The `prod.yml` file has been moved into a `config`
subfolder. Users with downstream repositories need to move their
`prod.yml` as well.
* Enable tenantadm as an Enterprise release component.
* Enable tenantadm as an Enterprise release component.
* Fix issue when demo script exists abruptly on user request
for logs. The issue only showed up when the folder name contained "-"
or "." characters.
* Upgrade deployments to 1.8.0b1.
* Upgrade deployments-enterprise to 1.8.0b1.
* Upgrade deviceauth to 2.1.0b1.
* Upgrade gui to 2.2.0b1.
* Upgrade mender to 2.1.1.
* Upgrade mender-artifact to 3.2.0b1.
* Upgrade mender-conductor to 1.5.0b1.
* Upgrade mender-conductor-enterprise to 1.5.0b1.
* Upgrade tenantadm to 1.0.0b1.
* Upgrade useradm to 1.9.0b1.
* Upgrade useradm-enterprise to 1.9.0b1.

#### mender-conductor (1.5.0)

New changes in mender-conductor since 1.4.0:

* update conductor from 2.2.0 to 2.11.0; fix configuration
* startup script modified
* copy default configuration into the image

#### mender-conductor-enterprise (1.5.0)

New changes in mender-conductor-enterprise since 1.4.0:

* update task configs to work with conductor 2.11.0
* fixing U+2014 'EM DASH' character
([MC-1016](https://tracker.mender.io/browse/MC-1016))

## Mender 2.1.1

_Released 12.05.2019_

### Changelogs

#### deviceauth (2.0.1)

New changes in deviceauth since 2.0.0:

* additional mongodb index added

#### gui (2.1.1)

New changes in gui since 2.1.0:

* Fixed faulty fallback file definition in nginx config

#### integration (2.1.1)

New changes in integration since 2.1.0:

* Fix issue when demo script exists abruptly on user request
for logs. The issue only showed up when the folder name contained "-"
or "." characters.
* Fix - Make sure the demo-script subprocess has a stdin fd
([MEN-2836](https://tracker.mender.io/browse/MEN-2836))
* Fix - Create explicit exitcond for the demo setup fixture
([MEN-2836](https://tracker.mender.io/browse/MEN-2836))
* Upgrade deviceauth to 2.0.1.
* Upgrade gui to 2.1.1.
* Upgrade mender to 2.1.2.
* Upgrade mender-artifact to 3.1.1.
## Mender 2.1.0

_Released 09.16.2019_

### Changelogs

#### deployments (1.7.1)

New changes in deployments since 1.7.0:

* Fix "unexpected EOF" errors when the source of the artifact
is a slow network stream.
* Fix spurious upload errors due to wrong EOF handling.
* Fix inability to resume partial migration.

#### gui (2.1.0)

New changes in gui since 2.1.0b1:

* added 2fa login functionality
* onboarding: Don't require Enter after copy/paste operation.
* added copyable version information tooltip in left navbar
* fixed an issue that could lead to help tooltips sometimes not showing
* fixed a problem that could cause a crash of the device lists
* onboarding: Don't require Enter after copy/paste operation.
* Fix installation of mender-artifact missing sudo in onboarding.
* Fix sudo password messing up commands in onboarding.
([MEN-2700](https://tracker.mender.io/browse/MEN-2700))

New changes in gui since 2.0.1:

* Device list times no longer change on expansion
([MEN-2366](https://tracker.mender.io/browse/MEN-2366))
* Fix onboarding install instructions for HM and demo server
([MEN-2571](https://tracker.mender.io/browse/MEN-2571))
* newly uploaded releases are now autoselected to ease deployment
* total artifact size in a release is now shown instead of signing state
* Updated Help pages with new structure and content for Update Modules
* show total artifact size in ui + clarify uncompressed size
* long device inventory texts are no longer cut off + visible on hover

#### integration (2.1.0)

New changes in integration since 2.1.0b1:

* Fix error: `No such container: integration-2.1.0b1_mender-useradm_1`
* Upgrade deployments to 1.7.1.
* Upgrade gui to 2.1.0.
* Upgrade mender to 2.1.0.
* Upgrade mender-artifact to 3.1.0.
* Upgrade mender-cli to 1.2.0.
* Upgrade mender-conductor to 1.4.0.
* Upgrade mender-conductor-enterprise to 1.4.0.
* Upgrade useradm to 1.8.0.

New changes in integration since 2.0.1:

* Disable virtual QEMU client by default.
A client can be launched by giving the `--client` argument to the
`demo` script, either at the same time as launching the servers, or
later after the servers have already been launched.
([MEN-2363](https://tracker.mender.io/browse/MEN-2363))
* Automate upload of demo application artifact in demo server
([MEN-2433](https://tracker.mender.io/browse/MEN-2433))
* Fix Mender version not showing up in production.
([MEN-2690](https://tracker.mender.io/browse/MEN-2690))
* Allow demo script to run with existing demo user
([MEN-2682](https://tracker.mender.io/browse/MEN-2682))
* demo: Fix broken detection with no arguments and `--help` argument.
* Fixes for demo wget to work on Alpine Linux using latest download
([MEN-2654](https://tracker.mender.io/browse/MEN-2654))
* Adding deployments enterprise _REV
([MEN-2652](https://tracker.mender.io/browse/MEN-2652))
* Upgrade deployments to 1.7.1b1.
* Upgrade gui to 2.1.0b1.
* Upgrade mender to 2.1.0b1.
* Upgrade mender-artifact to 3.1.0b1.
* Upgrade mender-cli to 1.2.0b1.
* Upgrade mender-conductor to 1.4.0b1.
* Upgrade mender-conductor-enterprise to 1.4.0b1.
* Upgrade useradm to 1.8.0b1.
* Unify demo scripts by removing all except the one called 'demo'.
([MEN-2571](https://tracker.mender.io/browse/MEN-2571))

#### mender-conductor (1.4.0)

New changes in mender-conductor since 1.3.1:

* upgrading python client to the latest version (2.12.4)
* Timestamp added to send_email worker
* email-sender: fixed bug with wrong state reporting

#### mender-conductor-enterprise (1.4.0)

New changes in mender-conductor-enterprise since 1.3.1:

* MC-637 updating settings for prepare_org_welcome_email conductor task
* upgrading python client to the latest version (2.12.4)

#### useradm (1.8.0)

New changes in useradm since 1.7.0:

* unauthorized for empty username logins
([MEN-2375](https://tracker.mender.io/browse/MEN-2375))

## Mender 2.0.1

_Released 06.24.2019_

### Changelogs

#### gui (2.0.1)

New changes in gui since 2.0.0:

* long device inventory texts are no longer cut off + visible on hover
* updated dependencies
* Bugfix for innaccurate offline devices on dashboard
* Bugfix to ensure pending device checkboxes work as expected
* Prevented blank page on no result release search
([MEN-2572](https://tracker.mender.io/browse/MEN-2572))

#### integration (2.0.1)

New changes in integration since 2.0.0:

* Upgrade gui to 2.0.1.
* Upgrade mender to 2.0.1.
* Upgrade mender-artifact to 3.0.1.
* Upgrade mender-conductor to 1.3.1.
* Upgrade mender-conductor-enterprise to 1.3.1.

#### mender-conductor (1.3.1)

New changes in mender-conductor since 1.3.0:

* Timestamp added to send_email worker
* email-sender: fixed bug with wrong state reporting

## Mender 2.0.0

_Released 05.07.2019_

### Changelogs

#### deployments (1.7.0)

New changes in deployments since 1.7.0b1:

* artifact object extended with optional "size" field
* Update to latest mender-artifact dependency.

New changes in deployments since 1.6.0:

* Adjust go test files to reflect changes in API
([MEN-2309](https://tracker.mender.io/browse/MEN-2309))
* Updated the vendor dependency on mender-artifact
* Update deployments service with mender artifact v3 format changes
([MEN-2309](https://tracker.mender.io/browse/MEN-2309))
* The Dockerfile has been changed to build using the multi-stage container build
pattern, and now builds the deployments binary in one build step, and then
copies the binary over to the production environment based on alpine:3.6. This
change should help keep builds consistent across all services.

#### deviceauth (2.0.0)

New changes in deviceauth since 1.7.0:

* Devauth management API v1 and admission API removed.

#### gui (2.0.0)

New changes in gui since 2.0.0b1:

* Device list times no longer change on expansion
([MEN-2366](https://tracker.mender.io/browse/MEN-2366))
* show total artifact size in ui + clarify uncompressed size

New changes in gui since 1.7.0:

* Allow to accept multiple pending devices at one time
* schedule a new deployment to all devices within a group, except just the first 100
* Bugfix: Ensure "already installed" displays correctly in deployment report
* Update to deviceauth API v2 and use device authsets for admit-on-request flow
* Fixed single device selection in the device list UI, which could remove device selection otherwise
* show ungrouped devices in a visibly separated list entry
* more device identity attributes are now able to select, depending on their popularity
* fix an issue that prevented deployments to filtered devices
* more device identity attributes are now able to select, depending on their popularity
* multiple payloads in an artifact are now shown in the artifact list
* schedule a new deployment to all devices within a group, except just the first 100
* Fixed bug where finished deployments continue to display "in progress" when report is kept open
* multiple payloads in an artifact are now shown in the artifact list
* Allow click-to-retry for deployments with failures
* Allow to accept multiple pending devices at one time
* introduced devices information on the dashboard
* Fixed bug where finished deployments continue to display "in progress" when report is kept open
* Make Artifact selector more scalable with autocomplete
* introduced devices information on the dashboard

#### integration (2.0.0)

New changes in integration since 2.0.0b1:

* Upgrade deployments to 1.7.0.
* Upgrade deviceauth to 2.0.0.
* Upgrade gui to 2.0.0.
* Upgrade inventory to 1.6.0.
* Upgrade mender to 2.0.0.
* Upgrade mender-api-gateway-docker to 2.0.0.
* Upgrade mender-artifact to 3.0.0.
* Upgrade mender-conductor to 1.3.0.
* Upgrade mender-conductor-enterprise to 1.3.0.
* Resolve docker credentials problems in integration
([MEN-2408](https://tracker.mender.io/browse/MEN-2408))

New changes in integration since 1.7.0:

* Add statistics generator script, and start doing statistics
on code development for each release.
([MEN-2206](https://tracker.mender.io/browse/MEN-2206))
* logo pushed as in the case of mendersoftware/mender repo
* Upgrade deployments to 1.7.0b1.
* Upgrade deviceauth to 2.0.0b1.
* Upgrade gui to 2.0.0b1.
* Upgrade inventory to 1.6.0b1.
* Upgrade mender to 2.0.0b1.
* Upgrade mender-artifact to 3.0.0b1.
* Upgrade mender-conductor to 1.3.0b1.
* Upgrade mender-conductor-enterprise to 1.3.0b1.
* Ignore author's own signoff when generating release statistics.
* Integration tests for client DB migration.
([MEN-2311](https://tracker.mender.io/browse/MEN-2311))
* update conductor dependencies - elasticsearch and redis
* Fix docker version detection
* Added integration test for an Artifact without any compression.
([MEN-2224](https://tracker.mender.io/browse/MEN-2224))
* docker-compose: add mender-conductor to mender-device-auth dependencies

#### inventory (1.6.0)

New changes in inventory since 1.5.0:

* Allow filter with ":"

#### mender-conductor (1.3.0)

New changes in mender-conductor since 1.2.0:

* upgrade conductor to the latest version (2.2.0)
* Timestamp changed to ISO8601

#### mender-conductor-enterprise (1.3.0)

New changes in mender-conductor-enterprise since 1.2.0:

* Debug logging added to email preparer
* Version update from 1.8.1 to 1.8.9 for python conductor client
* Complete time format added in entrypoint script
* Bugfix for email preparer

## Mender 1.7.1

_Released 05.07.2019_

### Changelogs

#### integration (1.7.1)

New changes in integration since 1.7.0:

* Ignore author's own signoff when generating release statistics.
* Upgrade mender to 1.7.1.
* Upgrade mender-artifact to 2.4.1.
## Mender 1.7.0

_Released 12.13.2018_

### Release statistics
A total of 25446 lines added, 6653 removed (delta 18793)

| Developers with the most changesets |             |
|-------------------------------------|-------------|
| Marcin Chalczynski                  | 104 (34.0%) |
| Krzysztof Jaskiewicz                | 71 (23.2%)  |
| Kristian Amlie                      | 47 (15.4%)  |
| Michael Clelland                    | 36 (11.8%)  |
| Maciej Mrowiec                      | 14 (4.6%)   |
| Ole Petter Orhagen                  | 7 (2.3%)    |
| Alf-Rune Siqveland                  | 6 (2.0%)    |
| Don Cross                           | 5 (1.6%)    |
| Eystein Måløy Stenberg              | 4 (1.3%)    |
| Marcin Pasinski                     | 3 (1.0%)    |

| Developers with the most changed lines |              |
|----------------------------------------|--------------|
| Michael Clelland                       | 9832 (35.8%) |
| Kristian Amlie                         | 6660 (24.3%) |
| Marcin Chalczynski                     | 5180 (18.9%) |
| Krzysztof Jaskiewicz                   | 3594 (13.1%) |
| Alf-Rune Siqveland                     | 1184 (4.3%)  |
| Maciej Mrowiec                         | 367 (1.3%)   |
| Ole Petter Orhagen                     | 207 (0.8%)   |
| Don Cross                              | 186 (0.7%)   |
| Tobias Klauser                         | 56 (0.2%)    |
| Mirza Krak                             | 55 (0.2%)    |

| Developers with the most lines removed |           |
|----------------------------------------|-----------|
| Tobias Klauser                         | 51 (0.8%) |
| Eystein Måløy Stenberg                 | 28 (0.4%) |

| Developers with the most signoffs (total 310) |             |
|-----------------------------------------------|-------------|
| Marcin Chalczynski                            | 104 (33.5%) |
| Krzysztof Jaskiewicz                          | 71 (22.9%)  |
| Kristian Amlie                                | 48 (15.5%)  |
| Michael Clelland                              | 36 (11.6%)  |
| Maciej Mrowiec                                | 14 (4.5%)   |
| Ole Petter Orhagen                            | 8 (2.6%)    |
| Alf-Rune Siqveland                            | 6 (1.9%)    |
| Don Cross                                     | 5 (1.6%)    |
| Eystein Måløy Stenberg                        | 4 (1.3%)    |
| Marcin Pasinski                               | 3 (1.0%)    |

| Top changeset contributors by employer |             |
|----------------------------------------|-------------|
| RnDity                                 | 175 (57.2%) |
| Northern.tech                          | 122 (39.9%) |
| cosinekitty@gmail.com                  | 5 (1.6%)    |
| Amarula Solutions                      | 1 (0.3%)    |
| jgitlin@goboomtown.com                 | 1 (0.3%)    |
| tklauser@distanz.ch                    | 1 (0.3%)    |
| Election Systems & Software            | 1 (0.3%)    |

| Top lines changed by employer |               |
|-------------------------------|---------------|
| Northern.tech                 | 18415 (67.1%) |
| RnDity                        | 8774 (32.0%)  |
| cosinekitty@gmail.com         | 186 (0.7%)    |
| tklauser@distanz.ch           | 56 (0.2%)     |
| Election Systems & Software   | 16 (0.1%)     |
| Amarula Solutions             | 2 (0.0%)      |
| jgitlin@goboomtown.com        | 1 (0.0%)      |

| Employers with the most signoffs (total 310) |             |
|----------------------------------------------|-------------|
| RnDity                                       | 175 (56.5%) |
| Northern.tech                                | 126 (40.6%) |
| cosinekitty@gmail.com                        | 5 (1.6%)    |
| tklauser@distanz.ch                          | 1 (0.3%)    |
| Election Systems & Software                  | 1 (0.3%)    |
| Amarula Solutions                            | 1 (0.3%)    |
| jgitlin@goboomtown.com                       | 1 (0.3%)    |

| Employers with the most hackers (total 17) |            |
|--------------------------------------------|------------|
| Northern.tech                              | 10 (58.8%) |
| RnDity                                     | 2 (11.8%)  |
| cosinekitty@gmail.com                      | 1 (5.9%)   |
| tklauser@distanz.ch                        | 1 (5.9%)   |
| Election Systems & Software                | 1 (5.9%)   |
| Amarula Solutions                          | 1 (5.9%)   |
| jgitlin@goboomtown.com                     | 1 (5.9%)   |


### Changelogs

#### deployments (1.6.0)

New changes in deployments since 1.5.0:

* Change image download link validity to 24h from 1h.
* Change image download link validity to 24h from 1h.
([MEN-2054](https://tracker.mender.io/browse/MEN-2054))

#### deviceauth (1.7.0)

New changes in deviceauth since 1.7.0b1:

* document management API v2

New changes in deviceauth since 1.6.0:

* do not synchronize data with device admission service
* docs: introduce version 2 of the management API
* fix database migration
* fix database migration
* management API v2 endpoint for getting devices
* v2 of GET /devices/<id>
* actually run migration 1.5.0
* actually run migration 1.5.0
* API v2 POST /devices endpoint (for preauthorizing devices)
* v2 of GET /devices/<id>

#### gui (1.7.0)

New changes in gui since 1.7.0b1:

* Fixed bug where finished deployments continue to display "in progress" when report is kept open

New changes in gui since 1.6.0:

* Update node modules
* Introduce new tabbed deployment layout
* Added 'Copy to clipboard' function to error messages throughout UI
* Add a date range filter to past deployments tab
* Add "copy link to device" button on expanded device view
* Add group filter to past devices tab
* Make Artifact selector more scalable with auto-complete
* Bugfix: Ensure "already installed" displays correctly in deployment report
* Allow click-to-retry for deployments with failures
* Update to deviceauth API v2 and use device authsets for admit-on-request flow

#### integration (1.7.0)

New changes in integration since 1.7.0b1:

* Upgrade deployments to 1.6.0.
* Upgrade deviceauth to 1.7.0.
* Upgrade gui to 1.7.0.
* Upgrade inventory to 1.5.0.
* Upgrade mender to 1.7.0.
* Upgrade mender-api-gateway-docker to 1.6.0.
* Upgrade mender-artifact to 2.4.0.
* Upgrade mender-cli to 1.1.0.
* Upgrade mender-conductor to 1.2.0.
* Upgrade mender-conductor-enterprise to 1.2.0.
* Upgrade useradm to 1.7.0.
* Add statistics generator script, and start doing statistics
on code development for each release.
([MEN-2206](https://tracker.mender.io/browse/MEN-2206))

New changes in integration since 1.6.0:

* Increase bandwidth limit to 3 MB/s per device for demo setup.
* remove admission service from the setup
* remove admission service from the setup
* client: Use KVM automatically if available. Remove "./demo --kvm" option.
* Fix docker version detection
* Upgrade deployments to 1.6.0b1.
* Upgrade deviceauth to 1.7.0b1.
* Upgrade gui to 1.7.0b1.
* Upgrade inventory to 1.5.0b1.
* Upgrade mender to 1.7.0b1.
* Upgrade mender-api-gateway-docker to 1.6.0b1.
* Upgrade mender-artifact to 2.4.0b1.
* Upgrade mender-cli to 1.1.0b1.
* Upgrade mender-conductor to 1.2.0b1.
* Upgrade mender-conductor-enterprise to 1.2.0b1.
* Upgrade useradm to 1.7.0b1.

#### mender-api-gateway-docker (1.6.0)

New changes in mender-api-gateway-docker since 1.5.0:

* nginx conf: redirect /api/management/v1/admission calls to devicauth service
* redirection to /ui/ fixed
* use exact openresty version (1.13.6.2-0-alpine) instead of floating tag (alpine)
* json access logs format option is added

#### mender-conductor-enterprise (1.2.0)

New changes in mender-conductor-enterprise since 1.1.0:

* Latest template from Ralph.

#### useradm (1.7.0)

New changes in useradm since 1.6.0:

* Recover from unsuccessful attempt to create user.
* Enable common logging stack adding request access log and response timings.

## Mender 1.6.1

_Released 12.13.2018_

### Changelogs

#### integration (1.6.1)

New changes in integration since 1.6.0:

* Upgrade deviceadm to 1.4.1.
* Upgrade mender to 1.6.1.
* Upgrade mender-artifact to 2.3.1.
* Add statistics generator script, and start doing statistics
on code development for each release.
([MEN-2206](https://tracker.mender.io/browse/MEN-2206))
* Fix docker version detection
## Mender 1.6.0

_Released 09.18.2018_

#### deviceauth (1.6.0)

New changes in deviceauth since 1.5.0:

* Device object returned by API exposes new boolean attribute: "decommissioning" signifying devices that are currently going through removal process.

#### gui (1.6.0)

New changes in gui since 1.6.0b1:

* Added 'Copy to clipboard' function to error messages throughout UI
* Introduce new tabbed deployment layout
* Update node modules
* Bugfix: Ensure "already installed" displays correctly in deployment report

New changes in gui since 1.5.0:

* Add preauthorize devices section
* Cleaned up URL for filtering device list by ID or group:
([MEN-1875](https://tracker.mender.io/browse/MEN-1875))
* Add a global setting to store and use user-selected device identity attribute throughout UI
* Fixup: Add a link to mender docs for enabling wifi in hosted image

#### integration (1.6.0)

New changes in integration since 1.6.0b1:

* Upgrade deviceauth to 1.6.0.
* Upgrade gui to 1.6.0.
* Upgrade inventory to 1.4.1.
* Upgrade mender to 1.6.0.
* Upgrade mender-artifact to 2.3.0.
* Upgrade mender-cli to 1.0.1.
* Upgrade mender-conductor to 1.1.0.
* Upgrade mender-conductor-enterprise to 1.1.0.
* Upgrade useradm to 1.6.0.

New changes in integration since 1.5.0:

* Add mender-cli as a versioned repository under the Mender umbrella.
* Upgrade deviceauth to 1.6.0b1.
* Upgrade gui to 1.6.0b1.
* Upgrade inventory to 1.4.1b1.
* Upgrade mender to 1.6.0b1.
* Upgrade mender-artifact to 2.3.0b1.
* Upgrade mender-cli to 1.0.1b1.
* Upgrade mender-conductor to 1.1.0b1.
* Upgrade mender-conductor-enterprise to 1.1.0b1.
* Upgrade useradm to 1.6.0b1.
* demo: suppress warning on newer docker-compose versions
* consolidate to single mongodb server instance
* Change mongo definitions to map the correct path. /data is being mapped, but /data/db needs to.
* test_security.py: Ignore return code of grep.
* use common mongodb server instance with tenantadm

#### mender-conductor (1.1.0)

New changes in mender-conductor since 1.0.0:

* Extend logging with messages from conductor client library to stdout.
* Update conductor client library to 1.8.9

## Mender 1.5.1

_Released 09.18.2018_

#### gui (1.5.1)

New changes in gui since 1.5.0:

* Bugfix - show decommissioned devices in deployment reports
* Bugfix - show decommissioned devices in deployment reports

#### integration (1.5.1)

New changes in integration since 1.5.0:

* test_security.py: Ignore return code of grep.
* Upgrade gui to 1.5.1.
* Upgrade inventory to 1.4.1.
* Upgrade mender to 1.5.1.
* Upgrade mender-cli to 1.0.1.
## Mender v1.5.0b1

_Released 05.15.2018_

#### deployments (1.5.0b1)
* display number of devices targeted when listing deployments
* possible to upload artifacts to specific tenant via internal API
([MEN-1775](https://tracker.mender.io/browse/MEN-1775))
* add ability to filter on deployment creation timestamps

#### deviceauth (1.5.0b1)
* trigger device provisioning workflow only if the device is not currently accepted
* device count endpoint handles preauthorized devices
* moved to globalsign/mgo

#### gui (1.5.0b1)
* Fix bug where recent deployment stats were being called repeatedly on dashboard
* Display version in UI
* Redesign Devices sections, added Rejected devices tab
* Display a dialog after first deployment as part of onboarding
* Move main navigation to be left aligned

#### integration (1.5.0b1)
* Switched to using Intel x86_64 hardware accelerated client
instead of ARM emulator.
* Make the integration version available to the UI
([MEN-1767](https://tracker.mender.io/browse/MEN-1767))
* mender-conductor container is now based on
github.com/mendersoftware/mender-conductor repository.
* Add --kvm option to demo scripts to run client VM hardware accelerated.
* Introduce optional mender-conductor container based on
github.com/mendersoftware/mender-conductor-enterprise, for Enterprise
installations.
* migrate to setup with mender-conductor-enterprise image
* Switch default client container type to qemux86-64.
* Upgrade deployments to 1.5.0b1.
* Upgrade deviceadm to 1.4.0b1.
* Upgrade deviceauth to 1.5.0b1.
* Upgrade gui to 1.5.0b1.
* Upgrade inventory to 1.4.0b1.
* Upgrade mender to 1.5.0b1.
* Upgrade mender-api-gateway-docker to 1.5.0b1.
* Add mender-conductor 1.0.0b1.
* Add mender-conductor-enterprise 1.0.0b1.
* Upgrade useradm to 1.5.0b1.
* migrate to setup with mender-conductor image

#### mender-api-gateway-docker (1.5.0b1)
* Allow cross-origin requests from hostnames listed in ALLOWED_HOSTS
* When a client exceeds its rate limit gateway returns 429 (Too
Many Requests) instead of 503 (Service Temporarily Unavailable)

#### useradm (1.5.0b1)
* New internal endpoint for deleting authentication tokens.

## Mender v1.5.0

_Released 06.07.2018_

#### integration (1.5.0)
* Add mender-cli as a versioned repository under the Mender umbrella.
* Upgrade deployments to 1.5.0.
* Upgrade deviceadm to 1.4.0.
* Upgrade deviceauth to 1.5.0.
* Upgrade gui to 1.5.0.
* Upgrade inventory to 1.4.0.
* Upgrade mender to 1.5.0.
* Upgrade mender-api-gateway-docker to 1.5.0.
* Add mender-cli 1.0.0.
* Add mender-conductor 1.0.0.
* Add mender-conductor-enterprise 1.0.0.
* Upgrade useradm to 1.5.0.
## Mender v1.4.2

_Released 06.07.2018_

#### gui (1.4.1)
* Fix elusive bug which sometimes caused GUI to restart over
and over due to not finding uglifyjs.

#### integration (1.4.2)
* Upgrade gui to 1.4.1.

## Mender v1.4.1

_Released 06.04.2018_

#### integration (1.4.1)
* Switched to using Intel x86_64 hardware accelerated client
instead of ARM emulator.
* Add --kvm option to demo scripts to run client VM hardware accelerated.
* Switch default client container type to qemux86-64.
* Upgrade mender to 1.4.1.
## Mender v1.4.0b1

_Released 02.09.2018_

#### deployments (1.4.0b1)
* updated aws-go-sdk to v1.12.27
* delete artifact from storage if parsing failed

#### deviceadm (1.3.0b1)
* PUT /devices/{id}/status (internal)

#### gui (1.4.0b1)
* Add checkbox option to remain logged in
* add progress bar for individual devices updates
([MEN-1558](https://tracker.mender.io/browse/MEN-1558))
* make it possible to decommission a device that has never sent inventory
* add request ID to snackbar
* Added deployments in progress to header bar
* Add Device notifications to top bar
* Fix for showing incorrect device IDs
([MEN-1536](https://tracker.mender.io/browse/MEN-1536))

#### integration (1.4.0b1)
* Upgrade Conductor to 1.8.1
* replace dynomite with redis
* fix http 404 on decommissioning
* Update integration version references to 1.4.x.
* Upgrade deployments to 1.4.0b1.
* Upgrade deviceadm to 1.3.0b1.
* Upgrade deviceauth to 1.4.0b1.
* Upgrade gui to 1.4.0b1.
* Upgrade inventory to 1.3.0b1.
* Upgrade mender to 1.4.0b1.
* Upgrade mender-api-gateway-docker to 1.4.0b1.
* Upgrade mender-artifact to 2.2.0b1.
* Upgrade useradm to 1.4.0b1.
* replace dynomite with redis

#### inventory (1.3.0b1)
* Get all devices in a group with a single api-call.
([MEN-811](https://tracker.mender.io/browse/MEN-811))

#### mender-api-gateway-docker (1.4.0b1)
* reload-when-hosts-changed: silence cmp output
* From now on it is possible to set rate limit per IP address
for the API using environment variables.
There are two variables:
RATE_LIMIT_GLOBAL_RATE=limit - number of request per second
RATE_LIMIT_GLOBAL_BURST=burst - burst parameter defines
how many requests a client can make in excess
of the rate specified by the limit.
Both parameters, limit and burst, should be numbers.
* entrypoint: include mender-gui in monitored DNS names

## Mender v1.4.0

_Released 03.20.2018_

#### integration (1.4.0)
* Upgrade deployments to 1.4.0.
* Upgrade deviceadm to 1.3.0.
* Upgrade deviceauth to 1.4.0.
* Upgrade gui to 1.4.0.
* Upgrade inventory to 1.3.0.
* Upgrade mender to 1.4.0.
* Upgrade mender-api-gateway-docker to 1.4.0.
* Upgrade mender-artifact to 2.2.0.
* Upgrade useradm to 1.4.0.
## Mender v1.3.1

_Released 02.09.2018_

#### integration (1.3.1)
* Upgrade gui to 1.3.1.
* Upgrade mender to 1.3.1.
* Upgrade mender-artifact to 2.1.2.
## Mender v1.3.0b1

_Released 11.14.2017_

#### deployments (1.3.0b1)
* docs: dump expire parameter from artifact download endpoint
* deployments/controller: handle substate field in device status updates
* images: make artifact download links valid for 15 minutes only
* deployments: descending sort by created time when listing deployments
* deployments/controller: status report substate field length limited to 200 characters
* Additional MongoDB configuration options: mongo_ssl, mongo_ssl_skipverify, mongo_username, mongo_password
* docs/management: return device state and substate in device deployment info
* limits: add GET /limits/storage management endpoint
* deployments: make artifact download links valid for 1 hour only
* Prevent artifacts with invalid checksums from
being uploaded to the server.
([MEN-1412](https://tracker.mender.io/browse/MEN-1412))
* docs/internal: spec for GET /tenants/:id/limits/storage
* Additional MongoDB configuration options: mongo_ssl, mongo…
* docs: document that expire on /artifacts/{id}/download is silently ignored
* POST /api/v1/internal/tenants ep
* docs/devices: add optional substate field in status ported

#### deviceadm (1.2.0b1)
* middleware: accommodate changes in request{id,log} middleware and enable request logger update
* Additional MongoDB configuration options: mongo_ssl, mongo_ssl_skipverify, mongo_username, mongo_password
* Additional MongoDB configuration options: mongo_ssl, mongo…
* store/mongo: move single tenant migration to separate func
* main: add 'migrate [--tenant=<tenant ID>]' command

#### deviceauth (1.3.0b1)
* GET /devices/count?status endpoint
* devauth: only one accepted authset
When accepting an auth set, reject all other accepted auth sets of a particular
device. This way we make sure that only one auth set is accepted at a time. In
case when key rotation is used, old key cannot be used to obtain the token.
([MEN-1417](https://tracker.mender.io/browse/MEN-1417))
* store/mongo: properly setup context for migrations in multi tenant
* api/http: support for internal endpoint for setting per-tenant limits
Add support for PUT operation on a new internal endpoint
`/api/internal/v1/devauth/tenant/:id/limits/:name`. The endpoint is used for
setting per tenant limits.
* store/mongo: make UpdateAuthSet() operate on multiple auth sets
* store, store/mongo: add collection for keeping 'Limits'
* devauth: ignore store.ErrAuthSetNotFound when rejecting auth sets during accept
* devauth: set Authorization field in  device decommissioning requests
* devauth: support for saving per-tenant limits
* devauth: log a message when the token is does not have a mender.device claim
* docs: include Authorization header in spec of authset status PUT endpoint
* Additional MongoDB configuration options: mongo_ssl, mongo_ssl_skipverify, mongo_username, mongo_password
* migrate --tenant=... cli
* store/mongo: raise store.ErrAuthSetNotFound when no auth sets were updated
* model: add Limit wrapper, add predefined limit name - max_device_count
* jwt: add mender.device claim, type bool, defaults to false
* docs/internal: remove 404 status on PUT /tenant/:id/limits/max-device-count
* middleware: repacking of logger and request ID to context is no longer needed
* docs: add spec for GET /limits/max_devices
* devauth: set and verify mender.device claim
Device tokens given out by deviceauth service will now have 'mender.device'
claim set to true. Tokens without the claim will fail verification and will be
rejected. Device is expected to request a new token.
* client/orchestrator: pass 'authorization' parameter in device decommission request

#### gui (1.3.0b1)
* Fix logout issues, only timeout user when inactive
* Fix for showing incorrect device IDs
([MEN-1536](https://tracker.mender.io/browse/MEN-1536))
* Added onboarding helptips that toggle on/off per user
* Added API connection error messaging and timeouts to Deployments tab
* Added API timeouts and disconnection error retry messages to devices and artifacts tabs
* disable decommissioning button while request is in progress
* API connection error and retry for deployments on dashboard

#### integration (1.3.0b1)
* compose, template: set mender-inventory command to `server --automigrate`
Ensure that inventory service starts in daemon mode and automatically applies DB
migrations.
* Fix Missing restart policy for some containers in
docker-compose setup.
([MEN-1556](https://tracker.mender.io/browse/MEN-1556))
* Update conductor to 1.7.7
* allow access to https://localhost in test environment
* Update conductor to 1.7.7
* Upgrade deployments to 1.3.0b1.
* Upgrade deviceadm to 1.2.0b1.
* Upgrade deviceauth to 1.3.0b1.
* Upgrade gui to 1.3.0b1.
* Upgrade inventory to 1.2.0b1.
* Upgrade mender to 1.3.0b1.
* Upgrade mender-api-gateway-docker to 1.3.0b1.
* Upgrade useradm to 1.3.0b1.
* conductor: include Authorization header in decommissioning workflow

#### inventory (1.2.0b1)
* main: add server [--automigrate] command, drop previous command line flags
Command line invocation and parameters are changed. See --help output for
details.
`server` subcommand will start the services in 'daemon' mode (sans the forking
part). Optional `--automigrate` argument enables automatic DB migration,
otherwise then a migration is needed the service will exit logging an error.
* Additional MongoDB configuration options: mongo_ssl, mongo_ssl_skipverify, mongo_username, mongo_password
* main: add 'migrate [--tenant=<tenant ID>]' command
* middleware: accommodate changes in request{id,log} middleware and enable request logger update
* dockerfile: update entrypoint to match currently supported command line arguments
* Additional MongoDB configuration options: mongo_ssl, mongo…

#### mender-api-gateway-docker (1.3.0b1)
* Introduce static content caching for /ui routing.
* Make browser side UI caching configurable though CACHE_UI env. Disabled by default.
* Include request time in gateway access logs.
* nginx: separate HTTP and HTTPS server scopes, redirect all HTTP requests to HTTPS
* nginx: align gateway URLs with useradm API
* Introduce static content caching for /ui routing.
* deployments service routing
* gateway dns cache reloading for improved recovery from service restarts
([MEN-1227](https://tracker.mender.io/browse/MEN-1227))
* Include request time in gateway access logs.

#### useradm (1.3.0b1)
* docs: add undocumented X-Original-URI, X-Original-Method on internal /auth/verify
* store/mongo: TenantDataStore uses a store with automigrations enabled
* commands: add 'migrate [--tenant=<id>]' command
* middleware: accommodate changes in request{id,log} middleware and enable request logger update
* jwt: add mender.user claim, bool
Add 'mender.user' claim to tokens given out bu useradm. The claim indicates that
the token is assigned to a user and a 'sub' claim corresponds to user ID.
* store/mongo: With*() helpers return a new instance of store with correct property modified
* docs: spec for an endpoint for setting up tenants
* commands: propagate new user to tenantadm
([MEN-1311](https://tracker.mender.io/browse/MEN-1311))
* store/mongo: move migration of single tenant to separate func
* api/http: update internal URLs, align them with API URL schema
Internal URLs are now available with /api/internal/v1/useradm/ prefix
* store: introduce tenant keeper
* docs: align internal URLs with API URL scheme
* useradm: add mender.user claim to given out tokens
Append 'mender.user' claim to all given out tokens. All tokens that do not have
this claim will fail verification and be rejected forcing the user to log in again.
* set correct header when sending token
* useradm: add CreateTenant operation
* api/http: add endpoint for creating tenants

## Mender v1.3.0

_Released 12.21.2017_

#### integration (1.3.0)
* Upgrade deployments to 1.3.0.
* Upgrade deviceadm to 1.2.0.
* Upgrade deviceauth to 1.3.0.
* Upgrade gui to 1.3.0.
* Upgrade inventory to 1.2.0.
* Upgrade mender to 1.3.0.
* Upgrade mender-api-gateway-docker to 1.3.0.
* Upgrade useradm to 1.3.0.
## Mender v1.2.2

_Released 11.14.2017_

#### deployments (1.2.2)
* deployments: descending sort by created time when listing deployments

#### integration (1.2.2)
* Upgrade deployments to 1.2.2.
* Upgrade gui to 1.2.1.
* Upgrade mender-api-gateway-docker to 1.2.1.
* Fix Missing restart policy for some containers in
docker-compose setup.
([MEN-1556](https://tracker.mender.io/browse/MEN-1556))

#### mender-api-gateway-docker (1.2.1)
* nginx: separate HTTP and HTTPS server scopes, redirect all HTTP requests to HTTPS

## Mender v1.2.1

_Released 10.02.2017_

#### deployments (1.2.1)
* Prevent artifacts with invalid checksums from
being uploaded to the server.
([MEN-1412](https://tracker.mender.io/browse/MEN-1412))

#### integration (1.2.1)
* Upgrade deployments to 1.2.1.
* Upgrade mender to 1.2.1.
* Upgrade mender-artifact to 2.1.1.
## Mender v1.2.0

_Released 09.05.2017_

#### deployments (1.2.0)
* Deployment creation process changed. From now on artifacts are
assigned to device deployments on update request handling.
* Return 422 - Unprocessable Entity on attempt of creating deployment without artifacts
* Deployments no longer require inventory to create deployments.
* New optional array field: 'artifacts' in deployment object returned by API containing list of artifact ids used by deployment.

#### deviceauth (1.2.0)
* Introduce 'server' subcommand that is also default command. Supports '--automigrate' parameter to enable automatic database version migration on startup.
* Increase orchestrater request timeout to 30s

#### gui (1.2.0)
* Bugfix for multiplying GET devices requests
* Add ‘create user’ functionality
* Change root API url to docker.mender.io
* Removed user creation UI incl password strength check (#231)
* Added user management edit functionality
* Updated node modules
* Remove shortened device IDs, now useless due to incremental SHAs
* create deployment from single device ([MEN-1233](https://tracker.mender.io/browse/MEN-1233))
* Allow user to remove artifacts via the GUI
* Added self user management

#### integration (1.2.0)
* Move interactive flags for client container to main docker file.
Makes it available for debugging on all client containers, not just
dev containers.
* allow access to https://localhost in test environment

#### mender-api-gateway-docker (1.2.0)
* Return additional headers for improved security: X-XSS-Protection, Cache-Control, Pragma. ([MEN-1316](https://tracker.mender.io/browse/MEN-1316))
* Validate Origin header if present. ([MEN-1287](https://tracker.mender.io/browse/MEN-1287))
* Add a configurable Host whitelist to gateway configuration, denying requests with unknown Hosts. Configured through ALLOWED_HOSTS env var on gateway startup. ([MEN-1262](https://tracker.mender.io/browse/MEN-1262))

#### useradm (1.2.0)
* Improve log messages when opening connection to MongoDB.
* Additional MongoDB configuration options: mongo_ssl, mongo_ssl_skipverify, mongo_username, mongo_password
* Remove 'initial user' login logic, including 'POST /users/initial' API. Now initial user need to be created by administrator using cli ([MEN-1034](https://tracker.mender.io/browse/MEN-1034))
* New cli subcommand for creating users: 'useradm create-user. ([MEN-1034](https://tracker.mender.io/browse/MEN-1034))
* New API for listing users: 'GET https://localhost/api/management/v1/useradm/users' and 'GET https://localhost/api/management/v1/useradm/users/:userid'
* New API for creating additional users: 'POST https://localhost/api/management/v1/useradm/users'
* New API for editing user email and password: 'PUT https://localhost/api/management/v1/useradm/users/:userid'
* New API for removing user: 'DELETE https://localhost/api/management/v1/useradm/users/:userid'

## Mender v1.1.3

_Released 10.02.2017_

#### integration (1.1.3)
* Fix incorrectly set service version references.

## Mender v1.1.2

_(Never released publicly)_

#### deployments (1.1.1)
* Prevent artifacts with invalid checksums from
being uploaded to the server.
([MEN-1412](https://tracker.mender.io/browse/MEN-1412))

#### integration (1.1.2)
* Upgrade deployments to 1.1.1.
* Upgrade mender to 1.1.2.
* Upgrade mender-artifact to 2.0.2.
## Mender v1.1.1

_Released 09.05.2017_

#### mender
* Fix - Now throws an error when committing nothing.
([MEN-505](https://tracker.mender.io/browse/MEN-505))
* Changed the errormessage to more closely reflect the issue.
([MEN-1215](https://tracker.mender.io/browse/MEN-1215))
* Improve error message when manifest field/file cannot be read.
* Logs an error when device_type file not found.
([MEN-505](https://tracker.mender.io/browse/MEN-505))
* Fixed behaviour when no sys-cert is available on the system.
([MEN-1151](https://tracker.mender.io/browse/MEN-1151))
* installer: improve incompatible image error message

#### mender-artifact
* Sign existing artifacts using mender-artifact CLI
([MEN-1220](https://tracker.mender.io/browse/MEN-1220))
* mender-artifact now fails with whitespace in the artifact-name
([MEN-1355](https://tracker.mender.io/browse/MEN-1355))
* Mender-Artifact now returns an error code to the os on cli errors
([MEN-1328](https://tracker.mender.io/browse/MEN-1328))

## Mender v1.1.0

_Released 06.16.2017_

#### gui

* Remove shortened device IDs, now useless due to incremental SHAs
* Fix for [MEN-1233](https://tracker.mender.io/browse/MEN-1233) - create deployment from single device

#### mender

* Fix misleading version being displayed for non-tagged builds. ([MEN-1178](https://tracker.mender.io/browse/MEN-1178))

## Mender v1.1.0 Beta 1

_Released 05.24.2017_

#### deployments
* Increase file upload request validity when pushing artifact to remote file storage.
* Update artifact handling reflecting changes in mender-artifact.
* Support for signed images introduced, but with no signature
verification yet. ([MEN-1022](https://tracker.mender.io/browse/MEN-1022))
* Add device decommissioning support in the deployments service.
* Update artifact description when updating artifact data.
* images/s3: unmarshal S3 errors when uploading image
* Artifact upload error handling fixed.
* Update artifact description when updating artifact data. ([MEN-1093](https://tracker.mender.io/browse/MEN-1093))
* travis: bump required Go version to 1.8

#### deviceadm
* Support for listing device authentication data sets with device ID
filter using GET /devices?device_id=<devid>

#### deviceauth
* New feature: decommissioning device
* devauth: improve logging when rejecting or giving out tokens
* Decommission device endpoint implemented (without
decommission job submit).
* api/management: management API is publicly available, update misleading description
* api: add tenant_token as an optional attribute in authentication request

#### gui
* Artifact signed field and improvements ([MEN-230](https://tracker.mender.io/browse/MEN-230))
* Bugfix: hide placeholder when past deployments is not empty ([MEN-229](https://tracker.mender.io/browse/MEN-229))
* Device blocking & decommissioning ([MEN-226](https://tracker.mender.io/browse/MEN-226))
* Implement pagination UI on pending & in progress deployment lists ([MEN-222](https://tracker.mender.io/browse/MEN-222))

#### integration
* Upgrade all server components to 1.1 series
* Upgrade client to 1.1
* Upgrade mender-artifact to 2.0

#### inventory
* No changes

#### mender-api-gateway-docker
* nginx: log and pass X-MEN-RequestID

#### mender-artifact
* Switch default artifact format version to 2. ([MEN-1183](https://tracker.mender.io/browse/MEN-1183))
* Add CLI support for signing and verifying images.
* Add implementation of RSA and ECDSA signatures.
* Fix returning and printing errors form artifact library.
* Fix overwriting artifact if new one is invalid.
* Add basic signing functionality and rewrite the library.

#### mender
* Add support for using signed mender-artifact library.
* Add support for verifying artifact signature. ([MEN-1020](https://tracker.mender.io/browse/MEN-1020))

#### useradm
* Added `create-user` and `server` commands to useradm. Running
`useradm server` will start useradm service (just like running `useradm` did),
also if no command is passed `server` is used a default. `create-user` will add
given user to DB. Examples: `useradm create-user --username foo@bar.com
--password foobarbarbar` (creates a user with username foo@bar.com and password
foobar...), `useradm create-user --username foo@bar.com` (same as before, but
password is read from terminal). See `--help` for details.

## Mender v1.0.1
_Released 04.05.2017_

### Notable changes

#### deployments

* Update artifact description when updating artifact data. (MEN-1093)
* Fix log flag not being set for device deployment after log been uploaded.
(MEN-1078)

#### gui

* Bugfix: open correct deployment report dialog from dashboard
* Update node modules, add drag+drop artifact, allow edit
artifact description
* Move user token from local storage to cookie, add react-cookie module (#217)
* Update node modules, add drag+drop & cookie functionality (#219)
* Replace artifact upload dialog with drag-and-drop
* Remove cookie when receiving unauthorized response
* Edit artifact description in UI

#### mender

* Fix bug that caused the update not to be retried after failing during
previous attempt (#193)

---
## Mender v1.0.0
_Released 02.20.2017_

---
