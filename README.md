# Home Assistant Community Add-on: NetBird-Client

[![License][license-shield]](LICENSE.md)

![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports armhf Architecture][armhf-shield]
![Supports armv7 Architecture][armv7-shield]
![Supports i386 Architecture][i386-shield]

![Project Maintenance][maintenance-shield]
[![GitHub Activity][commits-shield]][commits]

[![Community Forum][forum-shield]][forum]

Connect your devices into a single secure private WireGuard®-based mesh network with SSO/MFA and simple access controls.

## About

[NetBird][netbird] is an open-source VPN management platform built on top of WireGuard® making it easy to create secure private networks for your organization or home.

It requires zero configuration effort leaving behind the hassle of opening ports, complex firewall rules, VPN gateways, and so forth.

NetBird uses NAT traversal techniques to automatically create an overlay peer-to-peer network connecting machines regardless of location (home, office, data center, container, cloud, or edge environments and now HASSIO with this add-on), unifying virtual private network management experience.

[:books: Read the full add-on documentation][docs]

## Support

Got questions?

You have several options to get them answered:

- The [Home Assistant Discord chat server][discord-ha] for general Home
  Assistant discussions and questions.
- The Home Assistant [Community Forum][forum].
- Join the [Reddit subreddit][reddit] in [/r/homeassistant][reddit]

You could also [open an issue here][issue] GitHub.

## Contributing

This is an active open-source project. We are always open to people who want to
use the code or contribute to it.

We have set up a separate document containing our
[contribution guidelines](.github/CONTRIBUTING.md).

Thank you for being involved! :heart_eyes:

## Authors & contributors

The original setup of this repository was by [Daniel Burgess][dannymate], forked from [Franck Nijhof][frenck]'s [Zerotier-One add-on][zt-one-addon].

Contributors
Glenn Sommer
Felix Arnold

For a full list of all authors and contributors,
check [the contributor's page][contributors].

## License

MIT License

Copyright (c) 2019-2022 Franck Nijhof
Copyright (c) 2022-2023 Daniel Burgess

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

<!-- Arch Shields -->
[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg

<!-- Github Links -->
[commits]: https://github.com/dannymate/hassio-addons/commits/main
[contributors]: https://github.com/dannymate/hassio-addons/graphs/contributors
[issue]: https://github.com/dannymate/hassio-addons/issues
[docs]: https://github.com/dannymate/hassio-addons/blob/main/netbird-client/DOCS.md
[dannymate]: https://github.com/dannymate

<!-- Frenck -->
[zt-one-addon]: https://github.com/hassio-addons/addon-zerotier
[frenck]: https://github.com/frenck

<!--Github Shields -->
[commits-shield]: https://img.shields.io/github/commit-activity/y/dannymate/hassio-addons.svg
[license-shield]: https://img.shields.io/github/license/dannymate/hassio-addons.svg
[maintenance-shield]: https://img.shields.io/maintenance/yes/2024.svg

<!-- HASSIO Forum -->
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg
[forum]: https://community.home-assistant.io/t/netbird-client-add-on/517762
[reddit]: https://reddit.com/r/homeassistant

[netbird]: https://netbird.io/
