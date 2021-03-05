## How it works.

`hachanges` uses web scraping on the blogpost for the release that it tries to show, and determine which breaking change to list.
The webscraping is done in a [Cloudflare worker](https://workers.cloudflare.com/) and served as a JSON API at https://hachanges.entrypoint.xyz/

This will list breaking changes on versions for the next after the one you are running up to the latest stable version.

**Examples:**
You run version `0.87.0`, and `0.92.0` is published, it will show breaking changes for `0.88`, `0.89`, `0.90`, `0.91`, `0.92`.
You run version `0.92.0`, and `0.92.0` is published, it will not show anything.
You run version `0.91.0`, and `0.92.0` is published, it will show breaking changes for `0.92`.

## Example configuration.yaml

```yaml
breaking_changes:
```

## Configuration options

Key | Type | Required | Default | Description
-- | -- | -- | -- | --
`name` | `string` | `False` | `Potential breaking changes` | Custom name for the entities.
`scan_interval` | `int` | `False` | `300` | Seconds between updates.