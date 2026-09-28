---
title: mender-container-modules
taxonomy:
    category: docs
shortcode-core:
    active: false
github: false
---

## 1.0.1 - 2026-09-16


### Bug fixes

- cd into manifest dir beforing listing running containers ([MEN-9641](https://northerntech.atlassian.net/browse/MEN-9641))
- Fix stale volume mount paths after reboot for compositions using relative volume paths ([MEN-10102](https://northerntech.atlassian.net/browse/MEN-10102))
- gen_docker-compose now correctly matches and clears the provides keys of previously installed compositions ([MEN-10103](https://northerntech.atlassian.net/browse/MEN-10103))
- docker-compose Update Module's cleanup step no longer fails due to cleanup/image_ids not existing ([MEN-10101](https://northerntech.atlassian.net/browse/MEN-10101))
- Manifests with subdirectories no longer produce errors from grep being run on the subdirectories ([MEN-10101](https://northerntech.atlassian.net/browse/MEN-10101))
- Rollback to a previous composition reassigns the tags to container images used by the previous composition (the new attempted composition might have assigned the tags to new images) ([MEN-10114](https://northerntech.atlassian.net/browse/MEN-10114))

### All tickets resolved in this release

| Ticket |
|---|
| [MEN-9641](https://northerntech.atlassian.net/browse/MEN-9641) |
| [MEN-10102](https://northerntech.atlassian.net/browse/MEN-10102) |
| [MEN-10103](https://northerntech.atlassian.net/browse/MEN-10103) |
| [MEN-10101](https://northerntech.atlassian.net/browse/MEN-10101) |
| [MEN-10114](https://northerntech.atlassian.net/browse/MEN-10114) |


## mender-container-modules 1.0.0 (2026-01-13)

First release of mender-container-modules

