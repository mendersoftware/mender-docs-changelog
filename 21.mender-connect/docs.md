---
title: mender-connect
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---


## mender-connect 2.0.2

_Released 06.14.2022_

For internal consumption only.


## mender-connect 2.0.1

_Released 02.02.2022_

### Statistics

A total of 111 lines added, 16 removed (delta 95)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 2 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 111 (100.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 2 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 111 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-connect (2.0.1)

New changes in mender-connect since 2.0.0:

* fix: Global spawned shells count is not always decremented.


## mender-connect 2.0.0

_Released 01.24.2022_

### Statistics

A total of 572 lines added, 949 removed (delta -377)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 8 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 996 (100.0%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 377 (39.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 8 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 996 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-connect (2.0.0)

New changes in mender-connect since 1.2.0:

* Deprecate configuration fields `ServerURL` , `Servers`,
  `ServerCertificate`, `ClientProtocol`, `HTTPSClient` and `SkipVerify`.
  The server configuration is obtained via D-Bus API, for which from
  Mender 3.2 onwards is a local proxy which uses `mender.conf` client
  settings to securely authenticate with the backend server, making the
  client settings in `mender-connect.conf` redundant.
  ([MEN-5203](https://tracker.mender.io/browse/MEN-5203))
* Several robustness fixes around re-connection

  * Trigger re-connection when either token or server URL obtained from
    D-Bus signal has changed. Previously, it was enough with having a
    token with "some length" for the code to believe the device was
    authenticated and not trigger a re-connect.
  * Abort connecting after 10 retries. Previously it would reconnect
    forever with the same server URL, which will result in a deadlock if
    the url (or the token) changed while re-connecting.
  ([MEN-5290](https://tracker.mender.io/browse/MEN-5290))


## mender-connect 1.2.1

_Released 02.09.2022_

### Statistics

A total of 215 lines added, 306 removed (delta -91)

| Developers with the most changesets | |
|---|---|
| Peter Grzybowski | 2 (50.0%) |
| Lluis Campos | 2 (50.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 290 (72.3%) |
| Peter Grzybowski | 111 (27.7%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 186 (60.8%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 401 (100.0%) |

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-connect (1.2.1)

New changes in mender-connect since 1.2.0:

* Several robustness fixes around re-connection
  * Trigger re-connection when either token or server URL obtained from
    D-Bus signal has changed. Previously, it was enough with having a
    token with "some length" for the code to believe the device was
    authenticated and not trigger a re-connect.
  * Abort connecting after 10 retries. Previously it would reconnect
    forever with the same server URL, which will result in a deadlock if
    the url (or the token) changed while re-connecting.
  ([MEN-5290](https://tracker.mender.io/browse/MEN-5290))
* fix: Global spawned shells count is not always decremented.


## mender-connect 1.2.0

_Released 07.14.2021_

### Statistics

A total of 2823 lines added, 957 removed (delta 1866)

| Developers with the most changesets | |
|---|---|
| Alf-Rune Siqveland | 8 (40.0%) |
| Ole Petter Orhagen | 5 (25.0%) |
| Peter Grzybowski | 4 (20.0%) |
| Manuel Zedel | 2 (10.0%) |
| Kristian Amlie | 1 (5.0%) |

| Developers with the most changed lines | |
|---|---|
| Peter Grzybowski | 1949 (64.8%) |
| Alf-Rune Siqveland | 862 (28.7%) |
| Ole Petter Orhagen | 152 (5.1%) |
| Manuel Zedel | 42 (1.4%) |
| Kristian Amlie | 1 (0.0%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 20 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 3006 (100.0%) |

| Employers with the most hackers (total 5) | |
|---|---|
| Northern.tech | 5 (100.0%) |

### Changelogs

#### mender-connect (1.2.0)

New changes in mender-connect since 1.1.0:

* stat(2) file path and verify conditions before starting upload
* Add option to pass src_path to file upload requests
* FIX: Filetransfer owner restrictions checks username not (optional) real-name
* A Fix for group and owner file transfer limits
* Fix the terminal PATH issues in the standard shell by defaulting to
  starting a 'login' shell with the '--login' option. This can be controlled
  through the new configuration field 'ShellArguments', which you can set to
  whatever arguments you want passed to the shell on startup.
  ([MEN-4505](https://tracker.mender.io/browse/MEN-4505))
* Handle the re-connection request even if there is
  no new JWT token from the Mender client
  ([MEN-4694](https://tracker.mender.io/browse/MEN-4694))

## mender-connect 1.1.1

_Released 07.14.2021_

### Statistics

A total of 183 lines added, 47 removed (delta 136)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 3 (75.0%) |
| Peter Grzybowski | 1 (25.0%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 132 (72.1%) |
| Peter Grzybowski | 51 (27.9%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 4 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 183 (100.0%) |

| Employers with the most signoffs (total 0) | |
|---|---|

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-connect (1.1.1)

New changes in mender-connect since 1.1.0:

* Fix the terminal PATH issues in the standard shell by defaulting to
  starting a 'login' shell with the '--login' option. This can be controlled
  through the new configuration field 'ShellArguments', which you can set to
  whatever arguments you want passed to the shell on startup.
  ([MEN-4505](https://tracker.mender.io/browse/MEN-4505))
* Handle the re-connection request even if there is
  no new JWT token from the Mender client
  ([MEN-4694](https://tracker.mender.io/browse/MEN-4694))

## mender-connect 1.1.0

_Released 04.16.2021_

### Changelogs

#### mender-connect (1.1.0)

New changes in mender-connect since 1.0.0:

* Add remote triggers for Mender client's check-update and send-inventory
* [examples/mender-connect.conf] Remove unnecessary ServerURL
* Add handler for File Transfer protocol.
([MEN-4322](https://tracker.mender.io/browse/MEN-4322))
* filetransfer: Add handler for fetching file and file info
* New feature: TCP and UDP port-forwarding
* stat(2) file path and verify conditions before starting upload
* Add option to pass src_path to file upload requests

## mender-connect 1.0.3

_Released 02.09.2022_

### Statistics

A total of 122 lines added, 428 removed (delta -306)

| Developers with the most changesets | |
|---|---|
| Lluis Campos | 3 (100.0%) |

| Developers with the most changed lines | |
|---|---|
| Lluis Campos | 428 (100.0%) |

| Developers with the most lines removed | |
|---|---|
| Lluis Campos | 306 (71.5%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 428 (100.0%) |

| Employers with the most hackers (total 1) | |
|---|---|
| Northern.tech | 1 (100.0%) |

### Changelogs

#### mender-connect (1.0.3)

New changes in mender-connect since 1.0.2:

* Several robustness fixes around re-connection
  * Trigger re-connection when either token or server URL obtained from
    D-Bus signal has changed. Previously, it was enough with having a
    token with "some length" for the code to believe the device was
    authenticated and not trigger a re-connect.
  * Abort connecting after 10 retries. Previously it would reconnect
    forever with the same server URL, which will result in a deadlock if
    the url (or the token) changed while re-connecting.
  ([MEN-5290](https://tracker.mender.io/browse/MEN-5290))


## mender-connect 1.0.2

_Released 07.14.2021_

### Statistics

A total of 184 lines added, 47 removed (delta 137)

| Developers with the most changesets | |
|---|---|
| Ole Petter Orhagen | 2 (66.7%) |
| Peter Grzybowski | 1 (33.3%) |

| Developers with the most changed lines | |
|---|---|
| Ole Petter Orhagen | 133 (72.3%) |
| Peter Grzybowski | 51 (27.7%) |

| Top changeset contributors by employer | |
|---|---|
| Northern.tech | 3 (100.0%) |

| Top lines changed by employer | |
|---|---|
| Northern.tech | 184 (100.0%) |

| Employers with the most signoffs (total 0) | |
|---|---|

| Employers with the most hackers (total 2) | |
|---|---|
| Northern.tech | 2 (100.0%) |

### Changelogs

#### mender-connect (1.0.2)

New changes in mender-connect since 1.0.1:

* Fix the terminal PATH issues in the standard shell by defaulting to
  starting a 'login' shell with the '--login' option. This can be controlled
  through the new configuration field 'ShellArguments', which you can set to
  whatever arguments you want passed to the shell on startup.
  ([MEN-4505](https://tracker.mender.io/browse/MEN-4505))
* Handle the re-connection request even if there is
  no new JWT token from the Mender client
  ([MEN-4694](https://tracker.mender.io/browse/MEN-4694))

## mender-connect 1.0.1

_Released 16.04.2021_

### Changelogs

#### mender-connect (1.0.1)

New changes in mender-connect since 1.0.0:

* [examples/mender-connect.conf] Remove unnecessary ServerURL


## mender-connect 1.0.0

_Released 01.20.2021_

### Changelogs

#### mender-connect (1.0.0)

* First release of mender-connect

