---
title: monitor-client
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## monitor-client 1.1.0

_Released 01.24.2022_

### Statistics

A total of 738 lines added, 182 removed (delta 556)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 14 (56.0%) |
| Lluis Campos | 5 (20.0%) |
| Ole Petter Orhagen | 4 (16.0%) |
| Kristian Amlie | 2 (8.0%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 341 (40.3%) |
| Ole Petter Orhagen | 314 (37.1%) |
| Lluis Campos | 108 (12.8%) |
| Kristian Amlie | 84 (9.9%) |

| Developers with the most lines removed | |
|---|---|
| Kristian Amlie | 48 (26.4%) |
| Lluis Campos | 1 (0.5%) |

| Developers with the most signoffs (total 1) | |
|---|---|
| Lluis Campos | 1 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 25 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 847 (100.0%) |

| Employers with the most signoffs (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

| Employers with the most hackers (total 4) | |
|---|---|
| Northern.tech | 4 (100.0%) |

### Changelogs

#### monitor-client (1.1.0)

New changes in monitor-client since 1.0.0:

* monitorctl: warn on non-existent command.
* Clean excessive warning from the periodical alert store check.
* Fix failure when sending many stored alerts. Previously, an attempt to send large local alert store could trigger `126 Argument list too long` error and  no alerts would be sent.
  ([MEN-5133](https://tracker.mender.io/browse/MEN-5133))
* Correctly escape especial characters when saving alerts in the local store.
  ([MEN-5133](https://tracker.mender.io/browse/MEN-5133))
* Move local store unlock calls away from the trap, which may lead to races
* monitorctl: report error and exit when enabling/disabling non available checks
  ([MEN-5190](https://tracker.mender.io/browse/MEN-5190))
* monitorctl: Return the exit code properly and no output on successful execution. Previously monitorctl would always exit with code 0 even on errors
  ([MEN-5172](https://tracker.mender.io/browse/MEN-5172))
* monitorctl: Fix the issue with enable, disable, delete and create commands not returning the exit code correctly, which in turn leads to improper exit code of monitorctl tool
  ([MEN-5172](https://tracker.mender.io/browse/MEN-5172))
* Store configuration data on enabled checks.
  ([MEN-5185](https://tracker.mender.io/browse/MEN-5185))
* Remove device_online check, treating all errors to reach the
  Mender server as "device is offline", saving the alerts in the store for
  later re-send.
  ([MEN-5216](https://tracker.mender.io/browse/MEN-5216))
* Add a variable for permanent in-memory key-values for subsystems

  This is then used in the subsystems like so:

  subsystem=disk

  PERMANENT_STORAGE_FOR_DISK[LAST_ALARM]=OK

  or similar, which means now that every subsystem has a unified way of storing
  state data.
* Add example monitor implementation to the examples/monitors, and
  examples/subsystems directory. Install and uninstall them with the
  make (un)install-example-monitors targets in the Makefile. Enable them with the
  'enable-example-monitors' target. The added subsystems are a connectivity
  system, for HTTP HEAD requests to a given server on an optional interface. A
  container subsystem for monitoring container actions as given by docker events,
  and a subsystem for monitoring disk usage of an optional disk, and warn on a
  given treshold, if the disk starts filling up.
  ([MEN-5137](https://tracker.mender.io/browse/MEN-5137))
* Remove records older than given time from alerts store.
  ([MEN-5336](https://tracker.mender.io/browse/MEN-5336))
* Increase the log lines sent within alerts
  ([MEN-5361](https://tracker.mender.io/browse/MEN-5361))
* Handle exiting commands in the streamline logs case.


## monitor-client 1.0.0

_Released 09.28.2021_

### Changelogs

#### monitor-client (1.0.0)

* First release of monitor-client
