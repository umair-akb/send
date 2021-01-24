# [![Send](./assets/icon.svg)](https://gitlab.com/timvisee/send/) Send

[![Build status on GitLab CI][gitlab-ci-master-badge]][gitlab-ci-link]
[![Latest release][release-badge]][release-link]
[![Docker image][docker-image-badge]][docker-image-link]
[![Project license][repo-license-badge]](LICENSE)

[docker-image-badge]: https://img.shields.io/badge/docker-latest-blue.svg
[docker-image-link]: https://gitlab.com/timvisee/send/container_registry/eyJuYW1lIjoidGltdmlzZWUvc2VuZCIsInRhZ3NfcGF0aCI6Ii90aW12aXNlZS9zZW5kL3JlZ2lzdHJ5L3JlcG9zaXRvcnkvMTQxODUwNC90YWdzP2Zvcm1hdD1qc29uIiwiaWQiOjE0MTg1MDQsImNsZWFudXBfcG9saWN5X3N0YXJ0ZWRfYXQiOm51bGx9
[gitlab-ci-link]: https://gitlab.com/timvisee/send/pipelines
[gitlab-ci-master-badge]: https://gitlab.com/timvisee/send/badges/master/pipeline.svg
[release-badge]: https://img.shields.io/github/v/tag/timvisee/send
[release-link]: https://gitlab.com/timvisee/send/-/tags
[repo-license-badge]: https://img.shields.io/github/license/timvisee/send.svg

A fork of Mozilla's [Firefox Send][mozilla-send].
Mozilla discontinued Send, this fork is a community effort to keep the project
up-to-date and alive.

- Forked [at][fork-commit] Mozilla's last publicly hosted version
- _Mozilla_ & _Firefox_ branding [is][remove-branding-pr] removed so you can legally self-host
- Kept compatible with [`ffsend`][ffsend] (CLI for Send)
- Dependencies have been updated
- Mozilla's [changes][mozilla-patches] since the fork have been selectively [merged][mozilla-patches-pr]
- Mozilla's experimental report feature, download tokens, trust warnings and FxA changes are not included

Find an up-to-date Docker image here: [docs/docker.md](docs/docker.md)

The original project by Mozilla can be found [here][mozilla-send].
The [`mozilla-master`][branch-mozilla-master] branch holds the `master` branch
as left by Mozilla.
The [`send-v3`][branch-send-v3] branch holds the commit tree of Mozilla's last
publicly hosted version, which this fork is based on.
The [`send-v4`][branch-send-v4] branch holds the commit tree of Mozilla's last
experimental version which was still a work in progress (featuring file
reporting, download tokens, trust warnings and FxA changes), this has
selectively been merged into this fork.
Please consider to [donate][donate] to allow me to keep working on this.

Thanks [Mozilla][mozilla] for building this amazing tool!

[branch-mozilla-master]: https://gitlab.com/timvisee/send/-/tree/mozilla-master
[branch-send-v3]: https://gitlab.com/timvisee/send/-/tree/send-v3
[branch-send-v4]: https://gitlab.com/timvisee/send/-/tree/send-v4
[donate]: https://timvisee.com/donate
[ffsend]: https://github.com/timvisee/ffsend
[fork-commit]: https://gitlab.com/timvisee/send/-/commit/3e9be676413a6e1baaf6a354c180e91899d10bec
[mozilla-patches-pr]: https://gitlab.com/timvisee/send/-/merge_requests/3
[mozilla-patches]: https://gitlab.com/timvisee/send/-/compare/3e9be676413a6e1baaf6a354c180e91899d10bec...mozilla-master
[mozilla-send]: https://github.com/mozilla/send
[mozilla]: https://mozilla.org/
[remove-branding-pr]: https://gitlab.com/timvisee/send/-/merge_requests/2

---

**Docs:** [FAQ](docs/faq.md), [Encryption](docs/encryption.md), [Build](docs/build.md), [Docker](docs/docker.md), [Metrics](docs/metrics.md), [More](docs/)

---

## Table of Contents

* [What it does](#what-it-does)
* [Requirements](#requirements)
* [Development](#development)
* [Commands](#commands)
* [Configuration](#configuration)
* [Localization](#localization)
* [Contributing](#contributing)
* [Testing](#testing)
* [Deployment](#deployment)
* [Clients](#clients)
* [License](#license)

---

## What it does

A file sharing experiment which allows you to send encrypted files to other users.

---

## Requirements

- [Node.js 12.x](https://nodejs.org/)
- [Redis server](https://redis.io/) (optional for development)
- [AWS S3](https://aws.amazon.com/s3/) or compatible service (optional)

---

## Development

To start an ephemeral development server, run:

```sh
npm install
npm start
```

Then, browse to http://localhost:8080

---

## Commands

| Command          | Description |
|------------------|-------------|
| `npm run format` | Formats the frontend and server code using **prettier**.
| `npm run lint`   | Lints the CSS and JavaScript code.
| `npm test`       | Runs the suite of mocha tests.
| `npm start`      | Runs the server in development configuration.
| `npm run build`  | Builds the production assets.
| `npm run prod`   | Runs the server in production configuration.

---

## Configuration

The server is configured with environment variables. See [server/config.js](server/config.js) for all options and [docs/docker.md](docs/docker.md) for examples.

---

## Localization

Send localization is managed via [Pontoon](https://pontoon.mozilla.org/projects/test-pilot-firefox-send/), not direct pull requests to the repository. If you want to fix a typo, add a new language, or simply know more about localization, please get in touch with the [existing localization team](https://pontoon.mozilla.org/teams/) for your language or Mozilla’s [l10n-drivers](https://wiki.mozilla.org/L10n:Mozilla_Team#Mozilla_Corporation) for guidance.

see also [docs/localization.md](docs/localization.md)

---

## Contributing

Pull requests are always welcome! Feel free to check out the list of ["good first issues"](https://github.com/mozilla/send/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22).

---

## Testing

| ENVIRONMENT | URL
|-------------|-----
| Production  | <https://send.firefox.com/>
| Stage       | <https://stage.send.nonprod.cloudops.mozgcp.net/>
| Development | <https://send2.dev.lcip.org/>

---

## Deployment

see also [docs/deployment.md](docs/deployment.md)

---

## Clients

- Web: _this repository_
- Command-line: [`ffsend`](https://github.com/timvisee/ffsend)
- Android: _see [Android](#android) section_

#### Android

The android implementation is contained in the `android` directory,
and can be viewed locally for easy testing and editing by running `ANDROID=1 npm
start` and then visiting <http://localhost:8080>. CSS and image files are
located in the `android/app/src/main/assets` directory.

---

## License

[Mozilla Public License Version 2.0](LICENSE)

[qrcode.js](https://github.com/kazuhikoarase/qrcode-generator) licensed under MIT

---
