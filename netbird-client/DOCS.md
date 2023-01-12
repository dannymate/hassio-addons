# Home Assistant Community Add-on: NetBird-Client

[NetBird][netbird] is an open-source VPN management platform built on top of WireGuard® making it easy to create secure private networks for your organization or home.

It requires zero configuration effort leaving behind the hassle of opening ports, complex firewall rules, VPN gateways, and so forth.

NetBird uses NAT traversal techniques to automatically create an overlay peer-to-peer network connecting machines regardless of location (home, office, data center, container, cloud, or edge environments and now HASSIO with this add-on), unifying virtual private network management experience.

## Installation

The installation of this add-on is pretty straightforward and not different in
comparison to installing any other Hass.io add-on.

1. Add my Hass.io add-ons repository (**https://github.com/dannymate/hassio-addons**) to your Hass.io instance.
2. Install the "NetBird-Client" add-on.
3. If you are using the central NetBird instance you can either use the URL generated in the log or you can use a `SETUP_KEY`. If hosting your own then you'll want to set `ADMIN_URL` & `MANAGEMENT_URL` and again only need to set up the `SETUP_KEY` if you don't want to login via the log generated URL.
4. Start the "NetBird-Client" add-on.
5. Feels free to check the logs for `NetBird-Client` to make sure its booted correctly.
6. This client will show up in your NetBird dashboard.

## Configuration

You'll see the config file at `/config/netbird/config.json` after first boot.

### Option: `log_level`

The `log_level` option controls the level of log output by the addon and can
be changed to be more or less verbose, which might be useful when you are
dealing with an unknown issue. Possible values are:

- `trace`: Show every detail, like all called internal functions.
- `debug`: Shows detailed debug information.
- `info`: Normal (usually) interesting events.
- `warning`: Exceptional occurrences that are not errors.
- `error`: Runtime errors that do not require immediate action.
- `fatal`: Something went terribly wrong. Add-on becomes unusable.

Please note that each level automatically includes log messages from a
more severe level, e.g., `debug` also shows `info` messages. By default,
the `log_level` is set to `info`, which is the recommended setting unless
you are troubleshooting.

### Option: `ADMIN_URL`

Admin Panel URL [http|https]://[host]:[port] (default "https://app.netbird.io")

Tells NetBird the URL through which you administrate your NetBird clients.
You'll find that the log generates a login URL you can use instead of configuring a `SETUP_KEY`. (If you're not already connected to a NetBird instance.)

### Option: `MANAGEMENT_URL`

Management Service URL [http|https]://[host]:[port] (default "https://api.wiretrustee.com:33073")

The client will use this URL to communicate with your NetBird instance api.

### Option: `SETUP_KEY`

Setup key obtained from the Management Service Dashboard (used to register peer)

This token is like a password for connecting your client to NetBird, you can leave this
option empty if you would prefer to login via a URL generated in the log with the `ADMIN_URL`.

## Changelog & Releases

This repository keeps a change log using [GitHub's releases][releases]
functionality.

Releases are based on [Semantic Versioning][semver], and use the format
of `MAJOR.MINOR.PATCH`. In a nutshell, the version will be incremented
based on the following:

- `MAJOR`: Incompatible or major changes.
- `MINOR`: Backwards-compatible new features and enhancements.
- `PATCH`: Backwards-compatible bugfixes and package updates.

## Support

Got questions?

You have several options to get them answered:

- The [Home Assistant Discord chat server][discord-ha] for general Home
  Assistant discussions and questions.
- The Home Assistant [Community Forum][forum].
- Join the [Reddit subreddit][reddit] in [/r/homeassistant][reddit]

You could also [open an issue here][issue] GitHub.

## Authors & contributors

The original setup of this repository was by [Daniel Burgess][dannymate], forked from [Franck Nijhof][frenck]'s [Zerotier-One add-on][zt-one-addon].

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


<!-- GITHUB LINKS -->
[contributors]: https://github.com/dannymate/hassio-addons/graphs/contributors
[issue]: https://github.com/dannymate/hassio-addons/issues
[releases]: https://github.com/hassio-addons/addon-zerotier/releases
[dannymate]: https://github.com/dannymate

<!-- Forums -->
[discord-ha]: https://discord.gg/c5DvZ4e
[forum]: https://community.home-assistant.io/t/home-assistant-community-add-on-zerotier-one/109091?u=frenck
[reddit]: https://reddit.com/r/homeassistant

[semver]: http://semver.org/spec/v2.0.0.htm
[netbird]: https://netbird.io/

<!-- Frenck -->
[zt-one-addon]: https://github.com/hassio-addons/addon-zerotier
[frenck]: https://github.com/frenck
