---
title: Mender client
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---


## mender 3.4.0

_Released 09.25.2022_

### Statistics

A total of 1308 lines added, 668 removed (delta 640)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 7 (22.6%) |
| Mikael Torp-Holte | 4 (12.9%) |
| Alf-Rune Siqveland | 3 (9.7%) |
| Lluis Campos | 2 (6.5%) |
| Ole Petter Orhagen | 2 (6.5%) |
| Fabio Tranchitella | 2 (6.5%) |
| Maciej Tomczuk | 2 (6.5%) |
| Domenic Rodriguez | 2 (6.5%) |
| Peter Grzybowski | 2 (6.5%) |
| Drew Moseley | 2 (6.5%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 721 (51.8%) |
| Kristian Amlie | 362 (26.0%) |
| Alf-Rune Siqveland | 128 (9.2%) |
| Ole Petter Orhagen | 57 (4.1%) |
| Maciej Tomczuk | 43 (3.1%) |
| Mikael Torp-Holte | 24 (1.7%) |
| Domenic Rodriguez | 20 (1.4%) |
| Peter Grzybowski | 11 (0.8%) |
| Drew Moseley | 8 (0.6%) |
| Michael Ho | 8 (0.6%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 24 (3.6%) |
| Jonas Vautherin | 3 (0.4%) |
| Kristian Amlie | 2 (0.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 25 (80.6%) |
| Gecko Robotics | 2 (6.5%) |
| drew@moseleynet.net | 2 (6.5%) |
| callmemikeh@gmail.com | 1 (3.2%) |
| jonas.vautherin@protonmail.ch | 1 (3.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1350 (97.1%) |
| Gecko Robotics | 20 (1.4%) |
| drew@moseleynet.net | 8 (0.6%) |
| callmemikeh@gmail.com | 8 (0.6%) |
| jonas.vautherin@protonmail.ch | 5 (0.4%) |

| Employers with the most hackers (total 13) | |
|---|---|
| Northern.tech | 9 (69.2%) |
| Gecko Robotics | 1 (7.7%) |
| drew@moseleynet.net | 1 (7.7%) |
| callmemikeh@gmail.com | 1 (7.7%) |
| jonas.vautherin@protonmail.ch | 1 (7.7%) |

### Changelogs

#### mender (3.4.0)

New changes in mender since 3.3.0:

##### Bug Fixes

* setenv: Fix script input syntax.
* rootfs-image-v2: Make sure to set mender_boot_part_hex
* By default we bind to 127.0.0.1:0 instead of localhost.
* Over D-Bus we return the ProxyHost equal to 127.0.0.1
* Upgrade openssl dependency to fix cast error in recent Go.
* If paused before ArtifactReboot, and then manually
  rebooting the device outside of Mender, the client will properly
  resume the update now, instead of failing and rolling back.
  ([MEN-5709](https://tracker.mender.io/browse/MEN-5709))
* Append log entries to syslog at the correct level
* The client update and inventory checks are now unaffected by the use
  of the `check-update` and `send-inventory` commands. While previously, this
  would both move the intervals at which checks we're done, and also extend them
  beyond the expected polling intervals configured.
  ([MEN-5547](https://tracker.mender.io/browse/MEN-5547))
* Resolve symlinks for /dev/disk/by-partlabel

##### Features

* Add DaemonLogLevel parameter in configuration file
  ([MEN-5583](https://tracker.mender.io/browse/MEN-5583))

##### Other

* Upgrade mender-artifact library to v0.0.0-20220913084855-9ed8ad0d53d0


## mender 3.3.1

_Released 10.19.2022_

### Statistics

A total of 628 lines added, 238 removed (delta 390)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 5 (31.2%) |
| Kristian Amlie | 5 (31.2%) |
| Peter Grzybowski | 2 (12.5%) |
| Michael Ho | 1 (6.2%) |
| Mikael Torp-Holte | 1 (6.2%) |
| Lluis Campos | 1 (6.2%) |
| Maciej Tomczuk | 1 (6.2%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 418 (64.0%) |
| Ole Petter Orhagen | 92 (14.1%) |
| Kristian Amlie | 82 (12.6%) |
| Maciej Tomczuk | 40 (6.1%) |
| Peter Grzybowski | 11 (1.7%) |
| Michael Ho | 8 (1.2%) |
| Mikael Torp-Holte | 2 (0.3%) |

| Developers with the most lines removed | |
|---|---|
| Ole Petter Orhagen | 2 (0.8%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 15 (93.8%) |
| callmemikeh@gmail.com | 1 (6.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 645 (98.8%) |
| callmemikeh@gmail.com | 8 (1.2%) |

| Employers with the most hackers (total 7) | |
|---|---|
| Northern.tech | 6 (85.7%) |
| callmemikeh@gmail.com | 1 (14.3%) |

### Changelogs

#### mender (3.3.1)

New changes in mender since 3.3.0:

##### Bug Fixes

* Upgrade openssl dependency to fix cast error in recent Go.
* If paused before ArtifactReboot, and then manually
  rebooting the device outside of Mender, the client will properly
  resume the update now, instead of failing and rolling back.
  ([MEN-5709](https://tracker.mender.io/browse/MEN-5709))
* The client update and inventory checks are now unaffected by the use
  of the `check-update` and `send-inventory` commands. While previously, this
  would both move the intervals at which checks we're done, and also extend them
  beyond the expected polling intervals configured.
  ([MEN-5547](https://tracker.mender.io/browse/MEN-5547))
* Append log entries to syslog at the correct level
* By default we bind to 127.0.0.1:0 instead of localhost.
* Over D-Bus we return the ProxyHost equal to 127.0.0.1
* Resolve symlinks for /dev/disk/by-partlabel
* The daemon no longer exits in the edge case where it cannot bring
  down the proxy server due to timeouts.
* The websockets are no longer left trying to open a connection to the
  server, when the proxy server is shut down.


## mender 3.3.0

_Released 06.14.2022_

### Statistics

A total of 928 lines added, 608 removed (delta 320)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 13 (43.3%) |
| Peter Grzybowski | 6 (20.0%) |
| Kristian Amlie | 4 (13.3%) |
| Domenic Rodriguez | 2 (6.7%) |
| Fabio Tranchitella | 1 (3.3%) |
| Mikael Torp-Holte | 1 (3.3%) |
| Sven Schermer | 1 (3.3%) |
| Lluis Campos | 1 (3.3%) |
| Adam Duskett | 1 (3.3%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 507 (46.6%) |
| Kristian Amlie | 284 (26.1%) |
| Peter Grzybowski | 249 (22.9%) |
| Domenic Rodriguez | 20 (1.8%) |
| Sven Schermer | 16 (1.5%) |
| Lluis Campos | 9 (0.8%) |
| Fabio Tranchitella | 2 (0.2%) |
| Mikael Torp-Holte | 1 (0.1%) |
| Adam Duskett | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 54 (8.9%) |
| Lluis Campos | 2 (0.3%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 26 (86.7%) |
| Gecko Robotics | 2 (6.7%) |
| Disruptive Technologies | 1 (3.3%) |
| aduskett@gmail.com | 1 (3.3%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 1052 (96.6%) |
| Gecko Robotics | 20 (1.8%) |
| Disruptive Technologies | 16 (1.5%) |
| aduskett@gmail.com | 1 (0.1%) |

| Employers with the most hackers (total 9) | |
|---|---|
| Northern.tech | 6 (66.7%) |
| Gecko Robotics | 1 (11.1%) |
| Disruptive Technologies | 1 (11.1%) |
| aduskett@gmail.com | 1 (11.1%) |

### Changelogs

#### mender (3.3.0)

New changes in mender since 3.2.1:

##### Bug Fixes

* Only fall back to older endpoints on HTTP 404's



  Make the client only fall back to older endpoints on HTTP 404 error codes when
  polling the `deployments/next` endpoint.

  Previous functionality fell back to older endpoints on all error codes. This in
  turn meant that when the client got rate-limited by the server on 429's, the
  client fell back to the older endpoints.

  The problem with this is that only the POSTv2 endpoint supports control maps, so
  when an update with control maps was in progress, the other endpoints would
  return 204, and the client would think the deployment was aborted from the server.
  ([MEN-5421](https://tracker.mender.io/browse/MEN-5421))
* Fixed an issue in which long-running systems, with a long time
  between reboots, and multiple updates encountered the `Tried maximum amount of
  times` error, due to an error in the retry logic.
* Log the fallback to the `artifact_info` file at log level Warn, when
  the Artifact name can not be retrieved from the database.
* add an After systemd dependency on mender-client-data-dir
* The `mender-client.service` file now has an explicit `After`
  dependency on the `data.mount` target, to make sure it is mounted, before the
  client commences operation.
* Fix Git error when installing after the fix for the
  [CVE-2022-24765 Git
  vulnerability](https://nvd.nist.gov/vuln/detail/CVE-2022-24765)
  ([Github's description of the
  issue](https://github.blog/2022-04-12-git-security-vulnerability-announced/)).
  This also fixes a subtle "pseudo abort" issue which can occur in the
  Yocto build environment.
* the HTTP proxy must bind on localhost, not on all the interfaces
  ([MEN-5642](https://tracker.mender.io/browse/MEN-5642))
* Don't accumulate zombies when command output parsing fails.
  ([MEN-5587](https://tracker.mender.io/browse/MEN-5587))
* Only capture module stdout when requested
  ([MEN-5098](https://tracker.mender.io/browse/MEN-5098))
* Fix printing of update module stdout in real-time

##### Features

* Allow to disable HTTP Keep-Alive from config, set idle timeout.
* Inventory push retries and backoff.

  We use RetryPollIntervalSeconds in inventory with the exponential
  backoff via GetExponentialBackoffTime together with a new setting:
  * RetryPollCount -- the max number of tries
  * inventory by default tries 3 times with one minute intervals
    (GetExponentialBackoffTime defaults)
* RetryPollCount applies to all places where backoff is present

##### Other

* Add alternate EFI path to mender-inventory-bootloader-integration
* Add alternate EFI path to mender-inventory-bootloader-inte…
* Add support for the `GET /v2/deployments/device/deployments/{id}/update_control_map` endpoint.
  ([MEN-5542](https://tracker.mender.io/browse/MEN-5542))

##### Dependabot bumps

* Aggregated Dependabot Changelogs:
  * Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.7.0 to 1.7.1.
      - [Release notes](https://github.com/stretchr/testify/releases)
      - [Commits](https://github.com/stretchr/testify/compare/v1.7.0...v1.7.1)

      ```
      updated-dependencies:
      - dependency-name: github.com/stretchr/testify
        dependency-type: direct:production
        update-type: version-update:semver-patch
      ```


## mender 3.2.1

_Released 02.02.2022_

### Statistics

A total of 113 lines added, 22 removed (delta 91)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 2 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 115 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 115 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender (3.2.1)

New changes in mender since 3.2.0:

* fix(client_update): Only fall back to older endpoints on HTTP 404's

  Make the client only fall back to older endpoints on HTTP 404 error codes when
  polling the `deployments/next` endpoint.

  Previous functionality fell back to older endpoints on all error codes. This in
  turn meant that when the client got rate-limited by the server on 429's, the
  client fell back to the older endpoints.

  The problem with this is that only the POSTv2 endpoint supports control maps, so
  when an update with control maps was in progress, the other endpoints would
  return 204, and the client would think the deployment was aborted from the server.
  ([MEN-5421](https://tracker.mender.io/browse/MEN-5421))


## mender 3.2.0

_Released 01.24.2022_

### Statistics

A total of 4572 lines added, 1819 removed (delta 2753)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 23 (39.0%) |
| Lluis Campos | 16 (27.1%) |
| Ole Petter Orhagen | 12 (20.3%) |
| Fabio Tranchitella | 4 (6.8%) |
| Zachary T Welch | 1 (1.7%) |
| Jesus | 1 (1.7%) |
| Maciej Tomczuk | 1 (1.7%) |
| Alf-Rune Siqveland | 1 (1.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 2786 (53.9%) |
| Kristian Amlie | 1295 (25.1%) |
| Ole Petter Orhagen | 1035 (20.0%) |
| Fabio Tranchitella | 32 (0.6%) |
| Alf-Rune Siqveland | 9 (0.2%) |
| Jesus | 6 (0.1%) |
| Zachary T Welch | 2 (0.0%) |
| Maciej Tomczuk | 1 (0.0%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 272 (15.0%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 57 (96.6%) |
| Timesys Corporation | 1 (1.7%) |
| wjaxxx@gmail.com | 1 (1.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 5158 (99.8%) |
| wjaxxx@gmail.com | 6 (0.1%) |
| Timesys Corporation | 2 (0.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 8) | |
|---|---|
| Northern.tech | 6 (75.0%) |
| wjaxxx@gmail.com | 1 (12.5%) |
| Timesys Corporation | 1 (12.5%) |

### Changelogs

#### mender (3.2.0)

New changes in mender since 3.1.0:

* [FIX] Fetch geo location data once per power cycle
* The client now shows output from scripts executed in the log as regular
  log messages, prefixed by the filedescriptor they are written to, and the script
  executed, like this: 'Output (stdout|stderr) from command \"/usr/bin/foo\": bar.'
  ([MEN-5098](https://tracker.mender.io/browse/MEN-5098))
* Bump github.com/mendersoftware/mender-artifact to 3.6.1
* Fix error not finding active partition for systems where /dev/root is a symlink
* installer/bootenv: support systemd-boot tools
* Upgrade golang.org/x/crypto to the latest version
* Title if the update module has not already requested a reboot. This
  is done, in the case that ArtifactInstall never finished, and hence the reboot
  information from the update module is never collected.
  ([MEN-4882](https://tracker.mender.io/browse/MEN-4882))
* Upgrade from deprecated `golang.org/x/crypto/ssh/terminal` to
  `golang.org/x/term`
  ([QA-235](https://tracker.mender.io/browse/QA-235))
* Mender starts a local HTTP server that will proxy incoming
  requests to `/api/devices` to the currently authenticated Mender server.
  The existing D-Bus API endpoints GetJwtToken and JwtTokenStateChange
  will now return the local address together with the JWT token. Supports
  also websocket upgrade when calling
  `/api/devices/v1/deviceconnect/connect` endpoint
  ([MEN-5216](https://tracker.mender.io/browse/MEN-5216))
* mender setup: Deprecate `--demo` flag and split its
  functionality across new flags `--demo-server` to configure the device
  for a Mender demo server and `--demo-polling` to use demo polling
  intervals. ([MEN-5138](https://tracker.mender.io/browse/MEN-5138))
* Client will no longer cache the Authorization token from
  the server across restarts, meaning that it is no longer possible to
  end up in the situation where a rootfs update with invalid
  authorization data succeeds, only to fail authorization later on when
  the token expires.
  ([MEN-5217](https://tracker.mender.io/browse/MEN-5217))
* It is no longer possible to change the identity of a device
  with a rootfs update. This was not supported before either, but worked
  in a hacky way by abusing the authorization token to get a rootfs
  update with new identity data to succeed. Afterwards the device would
  show up as a new device when the token expired.
  ([MEN-5217](https://tracker.mender.io/browse/MEN-5217))
* ubi: Get rid of useless warning: `Could not resolve path link: ubi..`
* Refresh update control maps before failing an update

  Fix the issue where if a state takes longer than the expiration time
  for the enabled update control map, then by the time the client checks its
  control maps, the map is expired, and the update fails.

  Now the client refreshes the update maps from the server before each pause, and
  hence, this issue will be avoided.
  ([MEN-5096](https://tracker.mender.io/browse/MEN-5096))
* Handle the possibility of losing network connectivity when refreshing
  the update control maps.
* Fix a race condition which can happen during a reboot if
  systemd kills the `reboot` command before it kills the Mender client.
  ([MEN-5340](https://tracker.mender.io/browse/MEN-5340))
* When an update is paused, the client now queries the server
  for updates using the `UpdatePollIntervalSeconds` interval if it is
  shorter than `UpdateControlMapExpirationTimeSeconds`, enabling quicker
  response when continuing an update.
* Fix a (possible) file descriptor leak.
* vendor: Bump mender-artifact to latest master version


## mender 3.1.1

_Released 02.09.2022_

### Statistics

A total of 430 lines added, 58 removed (delta 372)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 7 (41.2%) |
| Ole Petter | 6 (35.3%) |
| Lluis Campos | 3 (17.6%) |
| Jesus | 1 (5.9%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter | 259 (60.1%) |
| Kristian Amlie | 151 (35.0%) |
| Lluis Campos | 15 (3.5%) |
| Jesus | 6 (1.4%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Ole Petter | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 16 (94.1%) |
| wjaxxx@gmail.com | 1 (5.9%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 425 (98.6%) |
| wjaxxx@gmail.com | 6 (1.4%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| wjaxxx@gmail.com | 1 (25.0%) |

### Changelogs

#### mender (3.1.1)

New changes in mender since 3.1.0:

* Fix error not finding active partition for systems where /dev/root is a symlink
* Title if the update module has not already requested a reboot. This
  is done, in the case that ArtifactInstall never finished, and hence the reboot
  information from the update module is never collected.
  ([MEN-4882](https://tracker.mender.io/browse/MEN-4882))
* Refresh update control maps before failing an update
  Fix the issue where if a state takes longer than the expiration time
  for the enabled update control map, then by the time the client checks its
  control maps, the map is expired, and the update fails.
  Now the client refreshes the update maps from the server before each pause, and
  hence, this issue will be avoided.
  ([MEN-5096](https://tracker.mender.io/browse/MEN-5096))
* Handle the possibility of losing network connectivity when refreshing
  the update control maps.
* Fix a race condition which can happen during a reboot if
  systemd kills the `reboot` command before it kills the Mender client.
  ([MEN-5340](https://tracker.mender.io/browse/MEN-5340))
* Fix a (possible) file descriptor leak.
* Bump github.com/mendersoftware/mender-artifact to 3.6.x


## mender 3.1.0

_Released 09.28.2021_

### Statistics

A total of 588 lines added, 396 removed (delta 192)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 11 (36.7%) |
| Lluis Campos | 5 (16.7%) |
| Alf-Rune Siqveland | 3 (10.0%) |
| Ole Petter Orhagen | 3 (10.0%) |
| Fabio Tranchitella | 2 (6.7%) |
| Uri Ishon | 2 (6.7%) |
| Prashanth Joseph Babu | 2 (6.7%) |
| Alan Martinovic | 1 (3.3%) |
| Manuel Zedel | 1 (3.3%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 414 (58.5%) |
| Ole Petter Orhagen | 117 (16.5%) |
| Lluis Campos | 58 (8.2%) |
| Prashanth Joseph Babu | 46 (6.5%) |
| Uri Ishon | 31 (4.4%) |
| Alf-Rune Siqveland | 24 (3.4%) |
| Alan Martinovic | 13 (1.8%) |
| Fabio Tranchitella | 4 (0.6%) |
| Manuel Zedel | 1 (0.1%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 32 (8.1%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 26 (86.7%) |
| Complete Solution Robotics, LLC | 2 (6.7%) |
| prashanthjbabu@gmail.com | 2 (6.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 631 (89.1%) |
| prashanthjbabu@gmail.com | 46 (6.5%) |
| Complete Solution Robotics, LLC | 31 (4.4%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 9) | |
|---|---|
| Northern.tech | 7 (77.8%) |
| prashanthjbabu@gmail.com | 1 (11.1%) |
| Complete Solution Robotics, LLC | 1 (11.1%) |

### Changelogs

#### mender (3.1.0)

New changes in mender since 3.0.0:

* Fix a bug which could sometimes lead the client to do a
  rollback after it had already committed. This could happen if the
  client happened to spontaneously reboot or fail during the status
  update to the server. Doing this is not correct according to the state
  flow, and can have unexpected consequences depending on the
  combination of Update Modules and State Scripts.
  ([MEN-4830](https://tracker.mender.io/browse/MEN-4830))
* mender-inventory-network: Fix incompatibility with busybox,
  by using short command line options in grep command.
  ([MEN-4851](https://tracker.mender.io/browse/MEN-4851))
* Do not put useless and sometimes even incorrect zero values
  in the configuration file when running `mender setup`.
  ([MEN-4857](https://tracker.mender.io/browse/MEN-4857))
* Extend logs for docker module
* Add artifact_name to device provides if not found in store
* Support passing docker run CLI arguments when deploying
  an artifact using the `docker` _update module_.
* Implement support for non-U-Boot tool names.
  The tools still have to be command line compatible with the U-Boot
  tools (either u-boot-fw-utils or libubootenv), but the names can be
  different. This allows having U-Boot tools installed alongside
  grub-mender-grubenv tools, whose new names are
  `grub-mender-grubenv-set` and `grub-mender-grubenv-print`, instead of
  `fw_setenv` and `fw_printenv`.
  The two new configuration settings `BootUtilitiesSetActivePart` and
  `BootUtilitiesGetNextActivePart` have been introduced to configure the
  names. If no names are set, then the default is to try the
  grub-mender-grubenv tools first, followed by the "fw_" tools if the
  former are not found.
  ([MEN-3978](https://tracker.mender.io/browse/MEN-3978))
* Add missing filesystem sync which could produce an empty or
  corrupted Update Module file tree in
  `/var/lib/mender/modules/v3/payloads/0000/tree/files/` after an
  unexpected reboot.
* If the mender.conf file has a new server URL or tenant token, the
  client will now remove the cached authorization token upon the next restart of
  the dameon, and hence respect the new configuration, as opposed to letting it
  expire, which was the old functionality.
  ([MEN-3420](https://tracker.mender.io/browse/MEN-3420))
* [FIX] Fetch geo location data once per power cycle


## mender 3.0.2

_Released 02.09.2022_

### Statistics

A total of 430 lines added, 58 removed (delta 372)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 7 (41.2%) |
| Ole Petter | 6 (35.3%) |
| Lluis Campos | 3 (17.6%) |
| Jesus | 1 (5.9%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter | 259 (60.1%) |
| Kristian Amlie | 151 (35.0%) |
| Lluis Campos | 15 (3.5%) |
| Jesus | 6 (1.4%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Ole Petter | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 16 (94.1%) |
| wjaxxx@gmail.com | 1 (5.9%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 425 (98.6%) |
| wjaxxx@gmail.com | 6 (1.4%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| wjaxxx@gmail.com | 1 (25.0%) |

#### mender (3.0.2)

### Changelogs

New changes in mender since 3.0.1:

* Fix error not finding active partition for systems where /dev/root is a symlink
* Title if the update module has not already requested a reboot. This
  is done, in the case that ArtifactInstall never finished, and hence the reboot
  information from the update module is never collected.
  ([MEN-4882](https://tracker.mender.io/browse/MEN-4882))
* Refresh update control maps before failing an update
  Fix the issue where if a state takes longer than the expiration time
  for the enabled update control map, then by the time the client checks its
  control maps, the map is expired, and the update fails.
  Now the client refreshes the update maps from the server before each pause, and
  hence, this issue will be avoided.
  ([MEN-5096](https://tracker.mender.io/browse/MEN-5096))
* Handle the possibility of losing network connectivity when refreshing
  the update control maps.
* Fix a race condition which can happen during a reboot if
  systemd kills the `reboot` command before it kills the Mender client.
  ([MEN-5340](https://tracker.mender.io/browse/MEN-5340))
* Fix a (possible) file descriptor leak.
* Bump github.com/mendersoftware/mender-artifact to 3.6.x


## mender 3.0.1

_Released 09.29.2021_

### Statistics

A total of 94 lines added, 48 removed (delta 46)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 4 (50.0%) |
| Prashanth Joseph Babu | 2 (25.0%) |
| Alf-Rune Siqveland | 1 (12.5%) |
| Lluis Campos | 1 (12.5%) |

| Developers with the most changed lines | |
|---|---|
| Prashanth Joseph Babu | 46 (48.9%) |
| Kristian Amlie | 31 (33.0%) |
| Alf-Rune Siqveland | 9 (9.6%) |
| Lluis Campos | 8 (8.5%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 6 (75.0%) |
| prashanthjbabu@gmail.com | 2 (25.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 48 (51.1%) |
| prashanthjbabu@gmail.com | 46 (48.9%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| prashanthjbabu@gmail.com | 1 (25.0%) |


### Changelogs

#### mender (3.0.1)

New changes in mender since 3.0.0:

* Add artifact_name to device provides if not found in store
* Add missing filesystem sync which could produce an empty or
  corrupted Update Module file tree in
  `/var/lib/mender/modules/v3/payloads/0000/tree/files/` after an
  unexpected reboot.
* [FIX] Fetch geo location data once per power cycle


## mender 3.0.0

_Released 07.14.2021_

### Statistics

A total of 7715 lines added, 3584 removed (delta 4131)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 51 (48.6%) |
| Ole Petter Orhagen | 22 (21.0%) |
| Lluis Campos | 19 (18.1%) |
| Alf-Rune Siqveland | 3 (2.9%) |
| Fabio Tranchitella | 3 (2.9%) |
| Manuel Zedel | 2 (1.9%) |
| Nils Olav Kvelvane Johansen | 2 (1.9%) |
| Prashanth Joseph Babu | 2 (1.9%) |
| Grant Sloman | 1 (1.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 4160 (51.9%) |
| Kristian Amlie | 2479 (30.9%) |
| Lluis Campos | 1175 (14.7%) |
| Alf-Rune Siqveland | 80 (1.0%) |
| Nils Olav Kvelvane Johansen | 43 (0.5%) |
| Manuel Zedel | 35 (0.4%) |
| Prashanth Joseph Babu | 25 (0.3%) |
| Fabio Tranchitella | 22 (0.3%) |
| Grant Sloman | 1 (0.0%) |

| Developers with the most signoffs (total 4) | |
|---|---|
| Ole Petter Orhagen | 3 (75.0%) |
| Lluis Campos | 1 (25.0%) |

| Developers with the most report credits (total 1) | |
|---|---|
| Alex Stout | 1 (100.0%) |

| Developers who gave the most report credits (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 102 (97.1%) |
| prashanthjbabu@gmail.com | 2 (1.9%) |
| Violet Ultra Ltd | 1 (1.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 7994 (99.7%) |
| prashanthjbabu@gmail.com | 25 (0.3%) |
| Violet Ultra Ltd | 1 (0.0%) |

| Employers with the most signoffs (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Employers with the most hackers (total 9) | |
|---|---|
| Northern.tech | 7 (77.8%) |
| prashanthjbabu@gmail.com | 1 (11.1%) |
| Violet Ultra Ltd | 1 (11.1%) |

### Changelogs

#### mender (3.0.0)

New changes in mender since 2.6.0:

* mender setup: when configuring for demo using self-signed
  certificate, install the certificate in the local trust store so that
  all components in the system (namely, Mender addons) can trust the
  Mender server without extra configuration.
  ([MEN-4580](https://tracker.mender.io/browse/MEN-4580))
* Warn in the log when the system certificates contain the demo cert.
* Dont Verify SSL if skip verify is set
  If skip verify is set , then we shouldnt call VerifyResult
* Fix infinite carriage return output when running in ADB shell
* Add a DBus endpoint for the UpdateControlMap, which allows
  a user to set the `ID` and `Priority` of a given update process.
  ([MEN-4535](https://tracker.mender.io/browse/MEN-4535))
* The daemon will no longer crash if mender check-update or send-inventory is used before the daemon has finished its set up.
  ([MEN-4074](https://tracker.mender.io/browse/MEN-4074))
* Update Modules Artifact generators: correct --software-version flag
* single-file-artifact-gen: Support concurrent executions
* single-file Update Module: fix rollback functionality
* Add UpdateControlMapBootExpirationTimeSeconds to mender.conf.
* The location of the device type file is now determined by the mender.conf file. If the device type file is not used in mender.conf, the device type file is determined by the --data flag and if the flag is not used, the device type file is set to default. In addition, the scripts and modules directories location is consistent with the --data flag now.
  ([MEN-4669](https://tracker.mender.io/browse/MEN-4669))
* Implement the continue/pause/fail state machine logic
  This adds support for the explit control of the Mender state machine through the
  update control maps functionality.
  The state machine can be controlled through the verbs, puase/continue/fail in
  the states:
  * ArtifactInstall_Enter
  * ArtifactCommit_Enter
  * ArtifactReboot_Enter
  ([MEN-4549](https://tracker.mender.io/browse/MEN-4549))
* Fix D-Bus timeout on errors by finishing handling
  ([MEN-4703](https://tracker.mender.io/browse/MEN-4703))
* Report to deployments/status when pausing in any state
  ([MEN-4624](https://tracker.mender.io/browse/MEN-4624))
* Fix race condition in menderAuthManagerService due to
  concurrent map access. This could manifest either as a crash, or as a
  failure to deliver the JwtToken to dependent processes, such as
  mender-connect.
* Fix race condition in `dbus.RegisterMethodCallCallback` due
  to concurrent map access. This could manifest either as a crash, or as
  a failure to deliver the JwtToken to dependent processes, such as
  mender-connect.
* Fix: Correctly log the error response message from server errors
* Fix occasional crash when exiting using SIGTERM.
* Fix: `mender-client.service` and the old `mender.service`
  services can no longer run at the same time. If anyone has both, then
  `mender.service` should be removed from the system.
* Previously the Mender client would hide output from the
  child processes it ran, leading to errors from tools such as
  `fw_printenv`, not showing up in the logs.
  Now default to showing all output from the child processes called in
  the client logs.
* The client now supports the HTTP Device API v2.
  ([MEN-4785](https://tracker.mender.io/browse/MEN-4785))
* Mark deployment as failed on bad signature instead of retrying.
* CLI commands prefixed with hyphen are now deprecated, use
  instead directly the command name. For example `mender daemon`, `mender
  commit`, `mender show-artifact`, etc.
  ([MEN-4808](https://tracker.mender.io/browse/MEN-4808))
* Remove deprecated flag --log-modules
  ([MEN-4808](https://tracker.mender.io/browse/MEN-4808))
* Fix a bug which could sometimes lead the client to do a
  rollback after it had already committed. This could happen if the
  client happened to spontaneously reboot or fail during the status
  update to the server. Doing this is not correct according to the state
  flow, and can have unexpected consequences depending on the
  combination of Update Modules and State Scripts.
  ([MEN-4830](https://tracker.mender.io/browse/MEN-4830))
* mender-inventory-network: Fix incompatibility with busybox,
  by using short command line options in grep command.
  ([MEN-4851](https://tracker.mender.io/browse/MEN-4851))
* Do not put useless and sometimes even incorrect zero values
  in the configuration file when running `mender setup`.
  ([MEN-4857](https://tracker.mender.io/browse/MEN-4857))

## mender 2.6.1

_Released 07.14.2021_

### Statistics

A total of 506 lines added, 215 removed (delta 291)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 6 (37.5%) |
| Kristian Amlie | 5 (31.2%) |
| Ole Petter Orhagen | 2 (12.5%) |
| Nils Olav Kvelvane Johansen | 2 (12.5%) |
| Prashanth Joseph Babu | 1 (6.2%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 290 (49.9%) |
| Kristian Amlie | 186 (32.0%) |
| Ole Petter Orhagen | 58 (10.0%) |
| Nils Olav Kvelvane Johansen | 44 (7.6%) |
| Prashanth Joseph Babu | 3 (0.5%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 47 (21.9%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Ole Petter Orhagen | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 15 (93.8%) |
| prashanthjbabu@gmail.com | 1 (6.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 578 (99.5%) |
| prashanthjbabu@gmail.com | 3 (0.5%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| prashanthjbabu@gmail.com | 1 (20.0%) |

### Changelogs

#### mender (2.6.1)

New changes in mender since 2.6.0:

* Dont Verify SSL if skip verify is set
  If skip verify is set , then we shouldnt call VerifyResult
* Update Modules Artifact generators: correct --software-version flag
* single-file-artifact-gen: Support concurrent executions
* single-file Update Module: fix rollback functionality
* The daemon will no longer crash if mender check-update or send-inventory is used before the daemon has finished its set up.
  ([MEN-4074](https://tracker.mender.io/browse/MEN-4074))
* Fix D-Bus timeout on errors by finishing handling
  ([MEN-4703](https://tracker.mender.io/browse/MEN-4703))
* The location of the device type file is now determined by the mender.conf file. If the device type file is not used in mender.conf, the device type file is determined by the --data flag and if the flag is not used, the device type file is set to default. In addition, the scripts and modules directories location is consistent with the --data flag now.
  ([MEN-4669](https://tracker.mender.io/browse/MEN-4669))
* Fix race condition in menderAuthManagerService due to
  concurrent map access. This could manifest either as a crash, or as a
  failure to deliver the JwtToken to dependent processes, such as
  mender-connect.
* Fix race condition in `dbus.RegisterMethodCallCallback` due
  to concurrent map access. This could manifest either as a crash, or as
  a failure to deliver the JwtToken to dependent processes, such as
  mender-connect.
* Fix occasional crash when exiting using SIGTERM.
* Fix: Correctly log the error response message from server errors
* Fix a bug which could sometimes lead the client to do a
  rollback after it had already committed. This could happen if the
  client happened to spontaneously reboot or fail during the status
  update to the server. Doing this is not correct according to the state
  flow, and can have unexpected consequences depending on the
  combination of Update Modules and State Scripts.
  ([MEN-4830](https://tracker.mender.io/browse/MEN-4830))
* mender-inventory-network: Fix incompatibility with busybox,
  by using short command line options in grep command.
  ([MEN-4851](https://tracker.mender.io/browse/MEN-4851))

## mender 2.6.0

_Released 04.16.2021_

### Changelogs

#### mender (2.6.0)

New changes in mender since 2.5.0:

* fix, support white spaces in single-file artifacts' names
([MEN-4179](https://tracker.mender.io/browse/MEN-4179))
* Change provider in inventory-geo script to ipinfo.io
* Cache geo-location inventory data in volatile memory
* Log which scripts are run at the info level
* Filter out docker network interfaces in inventory
This adds functionality for filtering out interfaces matching
* br-.*
* veth.*
* docker.*
by default, so that docker network interfaces do not flood the inventory on
hosts running a lot of docker containers.
If re-adding this functionality is required, set the environment variable:
* INCLUDE_DOCKER_INTERFACES=true
([MEN-4487](https://tracker.mender.io/browse/MEN-4487))
* single-file: Use atomic file operations.
* single-file: Use stderr for all error messages.
* Remove deprecated field HttpsClient from config file (gets
the rid of bogus SSL warnings on `mender show-artifact` and any other
cli operation).
([MEN-4398](https://tracker.mender.io/browse/MEN-4398))
* Send the inventory after a successful deployment, even though the
device has not rebooted.
([MEN-4518](https://tracker.mender.io/browse/MEN-4518))
* mender setup: when configuring for demo using self-signed
certificate, install the certificate in the local trust store so that
all components in the system (namely, Mender addons) can trust the
Mender server without extra configuration.
([MEN-4580](https://tracker.mender.io/browse/MEN-4580))
* Warn in the log when the system certificates contain the demo cert.
* Aggregated Dependabot Changelogs:
* Bumps [github.com/stretchr/testify](https://github.com/stretchr/testify) from 1.6.1 to 1.7.0.
- [Release notes](https://github.com/stretchr/testify/releases)
- [Commits](https://github.com/stretchr/testify/compare/v1.6.1...v1.7.0)


## mender 2.5.4

_Released 02.09.2022_

### Statistics

A total of 297 lines added, 52 removed (delta 245)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 7 (53.8%) |
| Lluis Campos | 3 (23.1%) |
| Ole Petter | 2 (15.4%) |
| Jesus | 1 (7.7%) |

| Developers with the most changed lines | |
|---|---|
| Kristian Amlie | 152 (49.8%) |
| Ole Petter | 125 (41.0%) |
| Lluis Campos | 22 (7.2%) |
| Jesus | 6 (2.0%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Lluis Campos | 1 (50.0%) |
| Ole Petter | 1 (50.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 12 (92.3%) |
| wjaxxx@gmail.com | 1 (7.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 299 (98.0%) |
| wjaxxx@gmail.com | 6 (2.0%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| wjaxxx@gmail.com | 1 (25.0%) |

### Changelogs

#### mender (2.5.4)

New changes in mender since 2.5.3:

* Fix error not finding active partition for systems where /dev/root is a symlink
* Title if the update module has not already requested a reboot. This
  is done, in the case that ArtifactInstall never finished, and hence the reboot
  information from the update module is never collected.
  ([MEN-4882](https://tracker.mender.io/browse/MEN-4882))
* Fix a race condition which can happen during a reboot if
  systemd kills the `reboot` command before it kills the Mender client.
  ([MEN-5340](https://tracker.mender.io/browse/MEN-5340))
* Fix a (possible) file descriptor leak.
* Bump github.com/mendersoftware/mender-artifact to 3.5.x


## mender 2.5.3

_Release date 09.29.2021_

### Statistics

A total of 97 lines added, 51 removed (delta 46)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 5 (55.6%) |
| Prashanth Joseph Babu | 2 (22.2%) |
| Alf-Rune Siqveland | 1 (11.1%) |
| Lluis Campos | 1 (11.1%) |

| Developers with the most changed lines | |
|---|---|
| Prashanth Joseph Babu | 46 (47.4%) |
| Kristian Amlie | 34 (35.1%) |
| Alf-Rune Siqveland | 9 (9.3%) |
| Lluis Campos | 8 (8.2%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Kristian Amlie | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 7 (77.8%) |
| prashanthjbabu@gmail.com | 2 (22.2%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 51 (52.6%) |
| prashanthjbabu@gmail.com | 46 (47.4%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 3 (75.0%) |
| prashanthjbabu@gmail.com | 1 (25.0%) |

### Changelogs

#### mender (2.5.3)

New changes in mender since 2.5.2:

* Add artifact_name to device provides if not found in store
* Add missing filesystem sync which could produce an empty or
  corrupted Update Module file tree in
  `/var/lib/mender/modules/v3/payloads/0000/tree/files/` after an
  unexpected reboot.
* [FIX] Fetch geo location data once per power cycle


## mender 2.5.2

_Released 07.14.2021_

### Statistics

A total of 506 lines added, 215 removed (delta 291)

| Developers with the most changesets | |
|---|---|
| Kristian Amlie | 5 (33.3%) |
| Lluis Campos | 5 (33.3%) |
| Ole Petter Orhagen | 2 (13.3%) |
| Nils Olav Kvelvane Johansen | 2 (13.3%) |
| Prashanth Joseph Babu | 1 (6.7%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 289 (49.7%) |
| Kristian Amlie | 186 (32.0%) |
| Ole Petter Orhagen | 58 (10.0%) |
| Nils Olav Kvelvane Johansen | 45 (7.7%) |
| Prashanth Joseph Babu | 3 (0.5%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 47 (21.9%) |

| Developers with the most signoffs (total 2) | |
|---|---|
| Ole Petter Orhagen | 2 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 14 (93.3%) |
| prashanthjbabu@gmail.com | 1 (6.7%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 578 (99.5%) |
| prashanthjbabu@gmail.com | 3 (0.5%) |

| Employers with the most signoffs (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 4 (80.0%) |
| prashanthjbabu@gmail.com | 1 (20.0%) |

### Changelogs

#### mender (2.5.2)

New changes in mender since 2.5.1:

* Dont Verify SSL if skip verify is set
  If skip verify is set , then we shouldnt call VerifyResult
* Update Modules Artifact generators: correct --software-version flag
* single-file-artifact-gen: Support concurrent executions
* single-file Update Module: fix rollback functionality
* The daemon will no longer crash if mender check-update or send-inventory is used before the daemon has finished its set up.
  ([MEN-4074](https://tracker.mender.io/browse/MEN-4074))
* Fix D-Bus timeout on errors by finishing handling
  ([MEN-4703](https://tracker.mender.io/browse/MEN-4703))
* The location of the device type file is now determined by the mender.conf file. If the device type file is not used in mender.conf, the device type file is determined by the --data flag and if the flag is not used, the device type file is set to default. In addition, the scripts and modules directories location is consistent with the --data flag now.
  ([MEN-4669](https://tracker.mender.io/browse/MEN-4669))
* Fix race condition in menderAuthManagerService due to
  concurrent map access. This could manifest either as a crash, or as a
  failure to deliver the JwtToken to dependent processes, such as
  mender-connect.
* Fix race condition in `dbus.RegisterMethodCallCallback` due
  to concurrent map access. This could manifest either as a crash, or as
  a failure to deliver the JwtToken to dependent processes, such as
  mender-connect.
* Fix occasional crash when exiting using SIGTERM.
* Fix: Correctly log the error response message from server errors
* Fix a bug which could sometimes lead the client to do a
  rollback after it had already committed. This could happen if the
  client happened to spontaneously reboot or fail during the status
  update to the server. Doing this is not correct according to the state
  flow, and can have unexpected consequences depending on the
  combination of Update Modules and State Scripts.
  ([MEN-4830](https://tracker.mender.io/browse/MEN-4830))

## mender 2.5.1

_Released 16.04.2021_

### Changelogs

#### mender (2.5.1)

New changes in mender since 2.5.0:

* Change provider in inventory-geo script to ipinfo.io
* Cache geo-location inventory data in volatile memory
* Remove deprecated field HttpsClient from config file (gets
the rid of bogus SSL warnings on `mender show-artifact` and any other
cli operation).
([MEN-4398](https://tracker.mender.io/browse/MEN-4398))
* single-file: Use atomic file operations.
* single-file: Use stderr for all error messages.
* Send the inventory after a successful deployment, even though the
device has not rebooted.
([MEN-4518](https://tracker.mender.io/browse/MEN-4518))

## mender 2.5.0

_Released 01.20.2021_

### Changelogs

#### mender (2.5.0)

New changes in mender since 2.4.0:

* Fix rootfs-image-v2 commit in standalone mode when upgrade fails
* Add --reboot-exit-code parameter to "install" command.
* Fixed wrong error produced by rootfs-image commit
* Gracefully shutdown on SIGTERM
* implement "show-provides" command on client
([MEN-3074](https://tracker.mender.io/browse/MEN-3074))
* add inventory script to list the artifact provides data
([MEN-3073](https://tracker.mender.io/browse/MEN-3073))
* add support for software version flags in artifact generators
([MEN-3481](https://tracker.mender.io/browse/MEN-3481))
* Support for `clears_artifact_provides` field in Artifacts.
([MEN-3075](https://tracker.mender.io/browse/MEN-3075))
* switch to the new PUT endpoint to update inventory attributes
([MEN-4001](https://tracker.mender.io/browse/MEN-4001))
* Add Glib's GIO dependency for D-Bus interface. It can be
opt-out using `nodbus` at compile time.
([MEN-4032](https://tracker.mender.io/browse/MEN-4032))
* Add support for probing the U-Boot environment separator
([MEN-3970](https://tracker.mender.io/browse/MEN-3970))
* Allow to load private key from the Security configuration section
([MEN-3924](https://tracker.mender.io/browse/MEN-3924))
* artifact-gen: Improve error message when mender-artifact is not found.
([MEN-4044](https://tracker.mender.io/browse/MEN-4044))
* Fix: Do not switch boot partitions on installation errors on the
active partition.
([MEN-3980](https://tracker.mender.io/browse/MEN-3980))
* Correctly log the error message from the server on failed update
download attempts.
* mender-inventory-geo: Set connection timeout to 10s.
* Decrease the verbosity of 'Authorization requests failed' errors in
the log output.
* service API to register object interfaces over System DBus
([MEN-4009](https://tracker.mender.io/browse/MEN-4009))
* Add DBus support to AuthManager implementing WithDBus
* implement DBus signal ValidJwtTokenAvailable
([MEN-4017](https://tracker.mender.io/browse/MEN-4017))
* Add an inventory script for reporting the update-modules currently
installed on a device.
* Add busconfig file for DBus API to install steps.
([MEN-4030](https://tracker.mender.io/browse/MEN-4030))
* Replace the current progressbar with a minimalistic and less verbose implementation.
* The 'inventory-geo-script' now has a separate install target:
'install-inventory-network-scripts'. Note however that it is still installed by
the default 'install-inventory-scripts' target.
* When available, enable D-Bus interface by default
* Exit with code 0 on a received SIGTERM signal.
([MEN-4170](https://tracker.mender.io/browse/MEN-4170))
* Add passphrase-file global option.
* Fix error parsing response for getting tenant token on setup
([MEN-4245](https://tracker.mender.io/browse/MEN-4245))
* Extend the D-Bus API to return the server URL
([MEN-4360](https://tracker.mender.io/browse/MEN-4360))
* Aggregated Dependabot Changelogs:
* Bumps [github.com/mendersoftware/openssl](https://github.com/mendersoftware/openssl) from 1.0.9 to 1.0.10.
- [Release notes](https://github.com/mendersoftware/openssl/releases)
- [Commits](https://github.com/mendersoftware/openssl/compare/v1.0.9...v1.0.10)
* Bump github.com/mendersoftware/openssl from 1.0.9 to 1.0.10
* Bumps [github.com/mendersoftware/openssl](https://github.com/mendersoftware/openssl) from 1.0.10 to 1.1.0.
- [Release notes](https://github.com/mendersoftware/openssl/releases)
- [Commits](https://github.com/mendersoftware/openssl/compare/v1.0.10...v1.1.0)
* Bump github.com/mendersoftware/openssl from 1.0.10 to 1.1.0

## mender 2.4.2

_Released 01.21.2021_

### Changelogs

#### mender (2.4.2)

New changes in mender since 2.4.0:

* Add support for probing the U-Boot environment separator
([MEN-3970](https://tracker.mender.io/browse/MEN-3970))
* Fix: Do not switch boot partitions on installation errors on the
active partition.
([MEN-3980](https://tracker.mender.io/browse/MEN-3980))
* Allow to load private key from the Security configuration section
([MEN-3924](https://tracker.mender.io/browse/MEN-3924))
* mender-inventory-geo: Set connection timeout to 10s.
* Fix error parsing response for getting tenant token on setup
([MEN-4245](https://tracker.mender.io/browse/MEN-4245))

## mender 2.4.1

_Released 11.03.2020_

### Statistics

A total of 397 lines added, 161 removed (delta 236)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 4 (36.4%) |
| Peter Grzybowski | 3 (27.3%) |
| Lluis Campos | 3 (27.3%) |
| Fabio Tranchitella | 1 (9.1%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 314 (77.0%) |
| Peter Grzybowski | 51 (12.5%) |
| Lluis Campos | 42 (10.3%) |
| Fabio Tranchitella | 1 (0.2%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 11 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 408 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### mender (2.4.1)

New changes in mender since 2.4.0:

* Add support for probing the U-Boot environment separator
([MEN-3970](https://tracker.mender.io/browse/MEN-3970))
* Fix: Do not switch boot partitions on installation errors on the
active partition.
([MEN-3980](https://tracker.mender.io/browse/MEN-3980))
* Allow to load private key from the Security configuration section
([MEN-3924](https://tracker.mender.io/browse/MEN-3924))

## mender 2.4.0

_Released 09.11.2020_

### Changelogs

#### mender (2.4.0)

New changes in mender since 2.3.0:

* keystore: use openssl bindings
Switch the code that signs the server's authentication request
to use openssl. This allows to use ssl_engines, which permit to
use PKCS#11 or TPMs as keystore.
* vendor: switch openssl bindings to github.com/Linutronix/golang-openssl
spacemonkeygo/openssl depends on spacelog, which increases binary
size by about 2MB due to using reflect.
Switch to a fork which has the logger removed.
This patch can hopefully be reverted someday, when the logger
removal has been mainlined.
* Log state-script stderr as info, not error
([MEN-3316](https://tracker.mender.io/browse/MEN-3316))
* mender-inventory-geo script to return geo localization data
* Add support for libubootenv as boot loader user space tools
provider. ([MEN-3684](https://tracker.mender.io/browse/MEN-3684))
* Remove Server config warn on mender setup command
([MEN-3652](https://tracker.mender.io/browse/MEN-3652))
* Fix broken logging to syslogger.
([MEN-3676](https://tracker.mender.io/browse/MEN-3676))
* chmod 600 on config file
([MEN-3762](https://tracker.mender.io/browse/MEN-3762))
* mender-device-identity: skip dummyX interfaces
* mender.service: update to run after network-online.target
* Switch to OpenSSL for all server communication.
([MEN-3730](https://tracker.mender.io/browse/MEN-3730))
* keystore: support ed25519 keys
* Add the ability to configure the client with a client certificate and
private key in order to enable mTLS in the client communication setup.
([MEN-3115](https://tracker.mender.io/browse/MEN-3115))

## mender 2.3.3

_Released 16.04.2021_

### Changelogs

#### mender (2.3.3)

New changes in mender since 2.3.2:

* single-file: Use atomic file operations.
* single-file: Use stderr for all error messages.
* Send the inventory after a successful deployment, even though the
device has not rebooted.
([MEN-4518](https://tracker.mender.io/browse/MEN-4518))
* fix, support white spaces in single-file artifacts' names
([MEN-4179](https://tracker.mender.io/browse/MEN-4179))

## mender 2.3.2

_Released 01.21.2021_

### Changelogs

#### mender (2.3.2)

New changes in mender since 2.3.0:

* Add support for probing the U-Boot environment separator
([MEN-3970](https://tracker.mender.io/browse/MEN-3970))
* Fix: Do not switch boot partitions on installation errors on the
active partition.
([MEN-3980](https://tracker.mender.io/browse/MEN-3980))
* Fix error parsing response for getting tenant token on setup
([MEN-4245](https://tracker.mender.io/browse/MEN-4245))

## mender 2.3.1

_Released 11.03.2020_

### Statistics

A total of 211 lines added, 26 removed (delta 185)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 5 (55.6%) |
| Lluis Campos | 3 (33.3%) |
| Fabio Tranchitella | 1 (11.1%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 179 (80.6%) |
| Lluis Campos | 42 (18.9%) |
| Fabio Tranchitella | 1 (0.5%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 9 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 222 (100.0%) |

| Employers with the most hackers (total 3) | |
|---|---|
| Northern.tech | 3 (100.0%) |

### Changelogs

#### mender (2.3.1)

New changes in mender since 2.3.0:

* Add support for probing the U-Boot environment separator
([MEN-3970](https://tracker.mender.io/browse/MEN-3970))
* Fix: Do not switch boot partitions on installation errors on the
active partition.
([MEN-3980](https://tracker.mender.io/browse/MEN-3980))

## mender 2.3.0

_Released 07.15.2020_

### Changelogs

#### mender (2.3.0)

New changes in mender since 2.2.0:

* Fix "State transition loop detected" when retrying status update.
* Remove text/template dependency from the cli library reducing
mender client binary size by approximately 20%
* Renamed systemd mender.service -> mender-client.service
([MEN-2948](https://tracker.mender.io/browse/MEN-2948))
* Fixes various logging nitpicks
* Deprecated the log-modules cli commandline flag
([MEN-3251](https://tracker.mender.io/browse/MEN-3251))
* Make the system logger respect the global log level
([MEN-3135](https://tracker.mender.io/browse/MEN-3135))
* Make the system logger write to the LOG_USER facility by default
* Fix Stat_t.Dev/Rdev type assumption
* Send Provides in the deployments API call
([MEN-2587](https://tracker.mender.io/browse/MEN-2587))
* Report function caller on all logs when loglevel=Debug

## mender 2.2.1

_Released 07.15.2020_

### Changelogs

#### mender (2.2.1)

New changes in mender since 2.2.0:

* Fix check-update and send-inventory options on deb install
([MEN-3277](https://tracker.mender.io/browse/MEN-3277))
* Fix Stat_t.Dev/Rdev type assumption
* Log state-script stderr as info, not error
([MEN-3316](https://tracker.mender.io/browse/MEN-3316))
* Fix broken logging to syslogger.
([MEN-3676](https://tracker.mender.io/browse/MEN-3676))
* Add support for libubootenv as boot loader user space tools
provider. ([MEN-3684](https://tracker.mender.io/browse/MEN-3684))
* Make interactive setup device type default to configured device type
([MEN-3777](https://tracker.mender.io/browse/MEN-3777))

## mender 2.2.0

_Released 03.05.2020_

### Changelogs

#### mender (2.2.0)

New changes in mender since 2.2.0b1:

* Remove text/template dependency from the cli library reducing
mender client binary size by approximately 20%
* Fix "State transition loop detected" when retrying status update.

New changes in mender since 2.1.2:

* mender setup cli command and new CLI package
([MEN-2418](https://tracker.mender.io/browse/MEN-2418), [MEN-2806](https://tracker.mender.io/browse/MEN-2806))
* Fix UBI device size calculation
* store: Save artifact provides for dependency verifications
* app: Verify artifact (version >= 3) dependencies with current artifact
* store/app{standalone}: Artifact dependency checking for artifact v3
* app/store{standalone}: Unit tests Artifact v3 depends and provides
* Enable the usage of the full Mender-Artifact version 3 format
([MEN-2642](https://tracker.mender.io/browse/MEN-2642))
* support: modules-artifact-gen: Fix typo in default name of output file
* Rename --mender-professional flag to --hosted-mender
* Add --quiet flag and remove --run-daemon option and confirm device
* Now the client stores Artifact provides parameters across reboots in
standalone mode. Previously this data was ignored, and hence upgrading with an
Artifact with provides parameters these were lost.
([MEN-2969](https://tracker.mender.io/browse/MEN-2969))
* Set default device type to hostname for interactive setup
* New command: `snapshot dump` to dump current rootfs
* Skip special device "rootfs" when determining rootfs type
* Report 'Unknown' rootfs type if we can't detect it
* Optimize rootfs-update image writes
([MEN-2939](https://tracker.mender.io/browse/MEN-2939))
* Make `single-file-artifact-gen` script POSIX compliant.
([MEN-3049](https://tracker.mender.io/browse/MEN-3049))
* Fix segfault when running `mender setup` on a read-only
filesystem.
* Fix crash when specified certificate can't be opened.
Both the `ServerCertificate` setting and the system certificates are
now optional, in the sense that the client will run without them.
However, the client will not be able to connect without the right
certificates, so the main usecase of this change is to have a workable
client that will roll back if connections can't be made, instead of
exiting. ([MEN-3047](https://tracker.mender.io/browse/MEN-3047))
* Add warning message when server certificate can't be parsed.
* snapshot: Added watchdog timer to keep system from freezing
* snapshot: Add compression options to speed up transfer
* Improved error message when an update-module is missing
([MEN-3007](https://tracker.mender.io/browse/MEN-3007))
* snapshot: New flag `--source` specifying the source
filesystem to snapshot

## mender 2.1.3

_Released 03.05.2020_

### Changelogs

#### mender (2.1.3)

New changes in mender since 2.1.2:

* Fix crash when specified certificate can't be opened.
Both the `ServerCertificate` setting and the system certificates are
now optional, in the sense that the client will run without them.
However, the client will not be able to connect without the right
certificates, so the main usecase of this change is to have a workable
client that will roll back if connections can't be made, instead of
exiting. ([MEN-3047](https://tracker.mender.io/browse/MEN-3047))
* Add warning message when server certificate can't be parsed.


## mender 2.1.2

_Released 12.05.2019_

### Changelogs

#### mender (2.1.2)

New changes in mender since 2.1.1:

* Fix UBI device size calculation

## mender 2.1.1

_Released 10.23.2019_

### Changelogs

#### mender (2.1.1)

New changes in mender since 2.1.0:

* module/single-file: fix rollback state by correctly defining filename
* Check for -f option in stat command
* Set hard limit(10) for client update status report retries
This fixes an issue where the maxSendingAttemps in
updateReportRetry state could be set real high, since it is calculated
as UpdatePollIntervalSeconds / RetryPollIntervalSeconds. This adds a
hard upper limit of 10 retries for the client in any case.
([MEN-2676](https://tracker.mender.io/browse/MEN-2676))

## mender 2.1.2

_Released 12.05.2019_

### Changelogs

#### mender (2.1.2)

New changes in mender since 2.1.0:

* module/single-file: fix rollback state by correctly defining filename
* Check for -f option in stat command
* Set hard limit(10) for client update status report retries
This fixes an issue where the maxSendingAttemps in
updateReportRetry state could be set real high, since it is calculated
as UpdatePollIntervalSeconds / RetryPollIntervalSeconds. This adds a
hard upper limit of 10 retries for the client in any case.
([MEN-2676](https://tracker.mender.io/browse/MEN-2676))
* Fix UBI device size calculation

## mender 2.1.0

_Released 09.16.2019_

### Changelogs

#### mender (2.1.0)

New changes in mender since 2.0.1:

* rootfs-image-v2: Make sure to follow the spec regarding `stream-next`.
We should to read the final empty entry to make sure the client does
not block.
* Restore error code 2 behavior when there is nothing to commit.
* Fix read error masking in installer.chunkedCopy(...) func
* Update vendored dependencies for client.
* When set, HTTP proxy settings in http_proxy/https_proxy environment variables are respected now.
* module-artifact-gen: Fix inability to specify more than one device_type.
* Make all errors checked or explicitly ignored
All possible errors must be checked across all code base.
If an error is intentionally ignored it should be done explicitly.
* add state-scripts example scripts to wait for network connectivity
before trying to connect to the Mender server.
([MEN-2457](https://tracker.mender.io/browse/MEN-2457))
* Artifact gen: Support argument passthrough to `mender-artifact`.
Use `--` to signal that remaining arguments should be passed directly
to `mender-artifact`.
* Make the device type file location configurable
* Make channel receiving user signals buffered
The commit fixes improper usage of signal.Notify(...) func from Go stdlib.
A channel must be buffered to properly receive signals:
https://golang.org/pkg/os/signal/#Notify
Also there is no need to reallocate channel and defer signal.Stop(...)
each time user signal is received. Thus less resources are used.
* standalone: Fix artifact committing not working after upgrading from 1.x.
([MEN-2465](https://tracker.mender.io/browse/MEN-2465))
* Print warning on an invalid server certificate.
([MEN-2378](https://tracker.mender.io/browse/MEN-2378))
* add state-script example to preserve ssh keys accross updates
([MEN-2457](https://tracker.mender.io/browse/MEN-2457))
* Fix `/bin/lsb_release` not being picked up by inventory script.
* Fix misspells in comments and error messages
* Make sure ARM64 is included in bootloader integration inventory.
* Added example to retain systemd network configuration.
* single-file module: Make sure permissions are preserved.
Also make sure that backup preserves permissions.
* add state-script example to utilize dbus to broadcast
Mender states ([MEN-2457](https://tracker.mender.io/browse/MEN-2457))
* Provide command line interface to force inventory update.
([MEN-2131](https://tracker.mender.io/browse/MEN-2131))

## mender 2.0.1

_Released 06.24.2019_

### Changelogs

#### mender (2.0.1)

New changes in mender since 2.0.0:

* module-artifact-gen: Fix inability to specify more than one device_type.
* single-file module: Make sure permissions are preserved.
Also make sure that backup preserves permissions.
* Artifact gen: Support argument passthrough to `mender-artifact`.
Use `--` to signal that remaining arguments should be passed directly
to `mender-artifact`.
* Restore error code 2 behavior when there is nothing to commit.

## mender 2.0.0

_Released 05.07.2019_

### Changelogs

#### mender (2.0.0)

New changes in mender since 2.0.0b1:

* Version files are now allowed to contain a newline character. Also
some minor changes, as readVersion now accepts an io.Reader, and files are
opened outside of the function. This means that the error message is now
consistent for all the uses of readVersion.
([MEN-2318](https://tracker.mender.io/browse/MEN-2318))
* file-install modules: Don't destroy original before we know we have a backup.
* Fix File Install UM to not wipe out dest_dir on single file installs
* standalone: Fix artifact committing not working after upgrading from 1.x.
([MEN-2465](https://tracker.mender.io/browse/MEN-2465))
* Deprecate old file-install Update Module and create instead
two new ones: single-file-install and file-tree-install. These have a
simpler logic and clearer scope. See for details.
([MEN-2442](https://tracker.mender.io/browse/MEN-2442))
* Don't push network interfaces without a mac address to inventory
* Disallow installing file trees on root destination dir for
File Install Update Module
* Make sure ARM64 is included in bootloader integration inventory.
* Mender no longer misidentifies LVM volumes.
([MEN-2302](https://tracker.mender.io/browse/MEN-2302))
* Update modules: Implement `NeedsArtifactReboot` -> `Automatic`.
([MEN-2011](https://tracker.mender.io/browse/MEN-2011))

New changes in mender since 1.7.0:

* Bugfix: State-script error code in Sync-Enter causes infinite loop
([MEN-2195](https://tracker.mender.io/browse/MEN-2195))
* Allow rootfsPartA and rootfsPartB to be symlinks
* Rewrite AuthorizeWaitState to fix an infinite loop bug
([MEN-2195](https://tracker.mender.io/browse/MEN-2195))
* Modify design for exec.Cmd stdout/stderr logging
* Place UM generator scripts in a dedicated folder
([MEN-2371](https://tracker.mender.io/browse/MEN-2371))
* Write Update Module to do file(s) install
([MEN-2371](https://tracker.mender.io/browse/MEN-2371))
* Set StateScriptTimeout default to 1h
([MEN-2409](https://tracker.mender.io/browse/MEN-2409))
* Add source-installation instructions to README.md.
* Add `rootfs-image-v2` as a demonstration of how to
reimplement Mender's `rootfs-image` update type as an update module.
It's also useful as inspiration if users want to make their own
slightly tweaked rootfs-image type.
([MEN-2392](https://tracker.mender.io/browse/MEN-2392))
* Swapped definition of StateScriptRetryTimeout and
StateScriptRetryInterval for the names to represent what they are
actually doing. This change breaks compatibility with current usage of
these configurable parameters. See documentation for correct usage.
([MEN-2409](https://tracker.mender.io/browse/MEN-2409))
* Updated the copyright year to 2019 in LICENSE.
* Write update module for doing container setup
([MEN-2232](https://tracker.mender.io/browse/MEN-2232))
* Add example update modules for shell commands and pkg installs.
* Remove misleading warning message when ServerCert is missing.
* Remove jq dependency for file-install Update Module
* Implement initial version of update modules.
([MEN-2000](https://tracker.mender.io/browse/MEN-2000))
* Add support for Mender Artifact format version 3.
([MEN-2000](https://tracker.mender.io/browse/MEN-2000))
* Artifact name is now stored in the local database, and
`/etc/mender/artifact_info` acts only as a fallback if no name has
been stored yet. This is typically the case for devices provisioned
directly from a disk image. Scripts should use the client
`-show-artifact` argument instead of parsing the file.
([MEN-2000](https://tracker.mender.io/browse/MEN-2000))
* `-rootfs` argument has been removed and replaced with the
`-install` argument, which works the same way.
([MEN-2000](https://tracker.mender.io/browse/MEN-2000))
* Mender now runs a stripped down set of state scripts when
installing artifacts in standalone mode, and the `-f` flag is no
longer required to install such artifacts, nor is it valid. The
scripts that run are:
* `Download` scripts
* `ArtifactInstall` scripts
* `ArtifactCommit` scripts
* `ArtifactRollback` scripts
* `ArtifactFailure` scripts
Reboot scripts do not run, so these must be handled manually in
standalone mode.
([MEN-2000](https://tracker.mender.io/browse/MEN-2000))
* Behavior change: `ArtifactCommit_Error` scripts now run
after an `ArtifactCommit_Leave` script has returned an error.
([MEN-2000](https://tracker.mender.io/browse/MEN-2000))
* Bugfix in killing mechanism for State Scripts
timing out ([MEN-2409](https://tracker.mender.io/browse/MEN-2409))
* Update vendored dependency net/http2 to latest version
* Support installing most files using Makefile `install` target.
The device_type file is not supported, since it is highly hardware
specific. Also the configuration will be very bare bones, and will
require changes unless Hosted Mender is being used.
([MEN-2383](https://tracker.mender.io/browse/MEN-2383))
* Make output from `-show-artifact` easier to consume by limiting logging.
* Fix state logic for the case of actual wait
([MEN-2195](https://tracker.mender.io/browse/MEN-2195))
* Properly fail the update when writes to the underlying storage fail.
([MEN-2285](https://tracker.mender.io/browse/MEN-2285))
* Work around occasional OOM bug in mmc driver.
([MEN-2285](https://tracker.mender.io/browse/MEN-2285))
* Make sure state directory is created if it doesn't exist.

## mender 1.7.1

_Released 05.07.2019_

### Changelogs

#### mender (1.7.1)

New changes in mender since 1.7.0:

* Remove misleading warning message when ServerCert is missing.
* Bugfix: State-script error code in Sync-Enter causes infinite loop
([MEN-2195](https://tracker.mender.io/browse/MEN-2195))
* Update vendored dependency net/http2 to latest version
* Rewrite AuthorizeWaitState to fix an infinite loop bug
([MEN-2195](https://tracker.mender.io/browse/MEN-2195))
* Fix state logic for the case of actual wait
([MEN-2195](https://tracker.mender.io/browse/MEN-2195))
* Make sure ARM64 is included in bootloader integration inventory.
* Mender no longer misidentifies LVM volumes.
([MEN-2302](https://tracker.mender.io/browse/MEN-2302))
* Updated the copyright year to 2019 in LICENSE.

## mender 1.7.0

_Released 12.13.2018_

### Changelogs

#### mender (1.7.0)

New changes in mender since 1.7.0b1:

* Allow rootfsPartA and rootfsPartB to be symlinks

New changes in mender since 1.6.0:

* FIX: Enabling compiling ppc64le
* Fix active partition detection when using non-native
filesystems.
* Add inventory scripts for rootfs type and bootloader integration.
([MEN-2059](https://tracker.mender.io/browse/MEN-2059))
* New feature: Fail-over Mender server(s)
([MEN-1972](https://tracker.mender.io/browse/MEN-1972))
* New inventory script for "os" attribute, installed by default.
([MEN-2060](https://tracker.mender.io/browse/MEN-2060))
* Mender client now loads configuration settings from
both /etc/mender/mender.conf and (if it exists)
/var/lib/mender/mender.conf. The second file is located
on the data partition, so it allows any subset of configuration
changes to survive upgrades.
([MEN-2073](https://tracker.mender.io/browse/MEN-2073))
* Print a message to the mender log when the
mender client has confirmed the authenticity of an
artifact's digital signature.
([MEN-2152](https://tracker.mender.io/browse/MEN-2152))
* Fix update check not working under BusyBox.
([MEN-2159](https://tracker.mender.io/browse/MEN-2159))
* Add Community Code of Conduct
* Detect if inactive part is mounted and unmount
([MEN-2084](https://tracker.mender.io/browse/MEN-2084))
* Improve error message when running mender as non-root user
([MEN-2083](https://tracker.mender.io/browse/MEN-2083))

## mender 1.6.1

_Released 12.13.2018_

### Changelogs

#### mender (1.6.1)

New changes in mender since 1.6.0:

* Fix update check not working under BusyBox.
([MEN-2159](https://tracker.mender.io/browse/MEN-2159))
* Print a message to the mender log when the
mender client has confirmed the authenticity of an
artifact's digital signature.
([MEN-2152](https://tracker.mender.io/browse/MEN-2152))

## mender 1.6.0

_Released 09.18.2018_

### Changelogs

#### mender (1.6.0)

New changes in mender since 1.6.0b1:

* Fix active partition detection when using non-native
filesystems.
* New inventory script for "os" attribute, installed by default.
([MEN-2060](https://tracker.mender.io/browse/MEN-2060))
* FIX: Enabling compiling ppc64le
* Add inventory scripts for rootfs type and bootloader integration.
([MEN-2059](https://tracker.mender.io/browse/MEN-2059))

New changes in mender since 1.5.0:

* FIXED: HTTP error 401 is not handled by all states
([MEN-1854](https://tracker.mender.io/browse/MEN-1854))
* ArtifactReboot_Enter scripts are no longer rerun
if interrupted by an unexpected reboot. It will be treated
as if Mender itself rebooted.
* Enable user to force an update-check locally
The user can now force an update check by either running mender with the
-check-update option, or send a signal [SIGUSR1] to the running mender process.
([MEN-1905](https://tracker.mender.io/browse/MEN-1905))
* Add automatic check for canary value in U-Boot environment
to try to detect if there is a problem in the environment setup of
U-Boot and/or the u-boot-fw-utils tools.
* Mender client key generator script
* log active partition before and after reboot.
([MEN-1880](https://tracker.mender.io/browse/MEN-1880))

## mender 1.5.1

_Released 09.18.2018_

### Changelogs

#### mender (1.5.1)

New changes in mender since 1.5.0:

* FIX: Enabling compiling ppc64le
* Fix active partition detection when using non-native
filesystems.


## mender 1.5.0b1

_Released 05.15.2018_

### Changelogs

#### mender (1.5.0b1)
* Regenerate keys on all key errors, not just when keys are missing.
([MEN-1823](https://tracker.mender.io/browse/MEN-1823))
* cli: New client option to show installed artifact name
([MEN-1806](https://tracker.mender.io/browse/MEN-1806))
* Spontaneous-reboot hardening of the client
([MEN-1187](https://tracker.mender.io/browse/MEN-1187))
* FIXED: Log writes not flushed from memory
([MEN-1726](https://tracker.mender.io/browse/MEN-1726))
* Allow multiple digit partition numbers.
* log request-id in case of bad API requests
([MEN-1738](https://tracker.mender.io/browse/MEN-1738))
* Abort upgrade if artifact name is not retrievable from artifact_info
([MEN-1824](https://tracker.mender.io/browse/MEN-1824))

## mender 1.5.0

_Released 06.07.2018_

### Changelogs

#### mender (1.5.0)
* FIXED: HTTP error 401 is not handled by all states
([MEN-1854](https://tracker.mender.io/browse/MEN-1854))
* Mender client key generator script


## mender 1.4.1

_Released 06.04.2018_

### Changelogs

#### mender (1.4.1)
* FIXED: Log writes not flushed from memory
([MEN-1726](https://tracker.mender.io/browse/MEN-1726))
* Regenerate keys on all key errors, not just when keys are missing.
([MEN-1823](https://tracker.mender.io/browse/MEN-1823))
* Mender client key generator script


## mender 1.4.0b1

_Released 02.09.2018_

### Changelogs

#### mender (1.4.0b1)
* Report update status for scripts and states
([MEN-1015](https://tracker.mender.io/browse/MEN-1015))
* Print detailed logs about authorization errors.
([MEN-1660](https://tracker.mender.io/browse/MEN-1660), [MEN-1661](https://tracker.mender.io/browse/MEN-1661))
* mender-device-identity: Check if file exists before reading
Mender on orangepi fails to run because identity script exit with error like:
/usr/share/mender/identity/mender-device-identity
cat: can't open '/sys/class/net/bonding_masters/type': Not a directory
Add check before reading type to avoid problems.
* Remove trailing slash from server URL configuration.
([MEN-1620](https://tracker.mender.io/browse/MEN-1620))

## mender 1.4.0

_Released 03.20.2018_

### Changelogs

#### mender (1.4.0)
* Allow multiple digit partition numbers.


## mender 1.3.1

_Released 02.09.2018_

### Changelogs

#### mender (1.3.1)
* Print detailed logs about authorization errors.
([MEN-1660](https://tracker.mender.io/browse/MEN-1660), [MEN-1661](https://tracker.mender.io/browse/MEN-1661))

## mender 1.3.0b1

_Released 11.14.2017_

### Changelogs

#### mender (1.3.0b1)
* Mender now logs whatever a state-script outputs to stderr
([MEN-1349](https://tracker.mender.io/browse/MEN-1349))
* mender-device-identity: only collect MAC from ARPHRD_ETHER types
* Fix 'unexpected EOF' error when downloading large updates.
([MEN-1511](https://tracker.mender.io/browse/MEN-1511))
* Implement ability for client to resume a download from
where it left off if the connection is broken.
([MEN-1511](https://tracker.mender.io/browse/MEN-1511))
* Improve error messages for state scripts errors.
Rely on the full error description instead of just the error code.
* Fix compile for ARM64.
* set return code = 2, when there is nothing to commit
* Added retry-later functionality on top of the state-script functionality
* Correctly fail state script execution if stderr can not be opened.
It would not be impossible to continue execution in this case, but it
is bad to lose log output, and not being able to open stderr is a
pretty uncommon case that might indicate a more serious issue like
resource starvation.

## mender 1.3.0

_Released 12.21.2017_

### Changelogs

#### mender (1.3.0)
* Remove trailing slash from server URL configuration.
([MEN-1620](https://tracker.mender.io/browse/MEN-1620))


## mender 1.2.1

_Released 10.02.2017_

### Changelogs

#### mender (1.2.1)
* Improve error messages for state scripts errors.
Rely on the full error description instead of just the error code.
* Fix checksum not being verified for headers, only
payload. ([MEN-1412](https://tracker.mender.io/browse/MEN-1412))

## mender 1.2.0

_Released 09.05.2017_

### Changelogs

#### mender (1.2.0)
* Refactored all store implementations into /store
* Improve error message when manifest field/file cannot be read.
* Fixed format check to conform to the expected artifact-file-format
([MEN-1289](https://tracker.mender.io/browse/MEN-1289))
* installer: improve incompatible image error message
* Client will not run state scripts from cmd-line except when forced.
([MEN-1235](https://tracker.mender.io/browse/MEN-1235))
* Fixed behaviour when no sys-cert is available on the system.
([MEN-1151](https://tracker.mender.io/browse/MEN-1151))
* Mender now logs whatever a state-script outputs to stderr
([MEN-1349](https://tracker.mender.io/browse/MEN-1349))
* Fix misleading version being displayed for non-tagged builds.
([MEN-1178](https://tracker.mender.io/browse/MEN-1178))
* Changed the errormessage to more closely reflect the issue.
([MEN-1215](https://tracker.mender.io/browse/MEN-1215))
* Removed the DeviceKey option in menderConfig.
* Fix - Now throws an error when committing nothing.
([MEN-505](https://tracker.mender.io/browse/MEN-505))
* Introduction of state script feature. State scripts can be
used to execute scripts at various stages of Mender's execution. See
documentation for more information.
* Introduce experimental support for writing to UBI volumes
* Logs an error when device_type file not found.
([MEN-505](https://tracker.mender.io/browse/MEN-505))
* remove no longer referenced client certificate code

## mender 1.1.2

_(Never released publicly)_

### Changelogs

#### mender (1.1.2)
* Fix checksum not being verified for headers, only
payload. ([MEN-1412](https://tracker.mender.io/browse/MEN-1412))

