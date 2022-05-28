<details>
  <summary>Old readme</summary>
  
  [![GitHub Release][releases-shield]][releases]
[![GitHub Activity][commits-shield]][commits]
[![License][license-shield]](LICENSE.md)

![Project Maintenance][maintenance-shield]
[![BuyMeCoffee][buymecoffeebadge]][buymecoffee]

[![Discord][discord-shield]][discord]
[![Community Forum][forum-shield]][forum]

_Integration to show potential breaking_changes in the current published version based on your loaded components._

## How it works.

`hachanges` uses web scraping on the blogpost for the release that it tries to show, and determine which breaking change to list.
The webscraping is done in a [Cloudflare worker](https://workers.cloudflare.com/) and served as a JSON API at https://hachanges.entrypoint.xyz/v1/

This will list breaking changes on versions for versions released after the one you are running up to the latest stable version.

This will only list breaking changes in 2021.3 and newer.

**Examples:**
You run version `2021.3.0`, and `2021.6.0` is published, it will show breaking changes for `2021.4`, `2021.5`, `2021.6`.
You run version `2021.3.0`, and `2021.3.0` is published, it will not show anything.
You run version `2021.3.0`, and `2021.4.0` is published, it will show breaking changes for `2021.4`.

**This component will set up the following platforms.**

Platform | Description
-- | --
`sensor` | Show info about potential issue with your configuration before upgrading.

## Installation

1. Install with [HACS](https://hacs.xyz/)
2. Add `breaking_changes:` to your HA configuration.

## Example configuration.yaml

```yaml
breaking_changes:
```

## Configuration options

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`name` | `string` | `False` | `Potential breaking changes` | Custom name for the entities.
`scan_interval` | `int` | `False` | `300` | Seconds between updates.

## Contributions are welcome!

If you want to contribute to this please read the [Contribution guidelines](CONTRIBUTING.md)

***

[buymecoffee]: https://www.buymeacoffee.com/ludeeus
[buymecoffeebadge]: https://img.shields.io/badge/buy%20me%20a%20coffee-donate-yellow.svg?style=for-the-badge
[commits-shield]: https://img.shields.io/github/commit-activity/y/custom-components/breaking_changes.svg?style=for-the-badge
[commits]: https://github.com/custom-components/breaking_changes/commits/main
[discord]: https://discord.gg/Qa5fW2R
[discord-shield]: https://img.shields.io/discord/330944238910963714.svg?style=for-the-badge
[exampleimg]: example.png
[hachanges]: https://github.com/ludeeus/hachanges
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[forum]: https://community.home-assistant.io/
[license-shield]: https://img.shields.io/github/license/custom-components/breaking_changes.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-Joakim%20Sørensen%20%40ludeeus-blue.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/custom-components/breaking_changes.svg?style=for-the-badge
[releases]: https://github.com/custom-components/breaking_changes/releases

  
</details>

