# Tailscale / Headscale

A [labdex](https://github.com/labdex-app/labdex) plugin. Devices of a tailnet into Discovery (their 100.x and fd7a:… addresses), so they can be assigned to hosts, e.g. in a network of your remote-access area; known devices report online or offline as host status.

**Version** 1.0 · **Works with** labdex >=1.3,<2 · **Plugin id** `tailscale`

> [!WARNING]
> Built with AI, for home labs only: labdex and its plugins were written largely with an AI
> coding assistant (Claude), directed and reviewed by a human. They haven't had an independent
> security audit and may contain security problems. Run them on a trusted home network.

## Install

It ships with labdex: **Plugins › Marketplace**, then *Install* (nothing is downloaded). Updates arrive through the official Marketplace (signed with the labdex project key).

## Settings

| Setting | Notes |
| --- | --- |
| Coordination server |  |
| Server URL | Headscale's URL; for Tailscale leave empty (api.tailscale.com) |
| Tailnet | Tailscale only: '-' = the API key's tailnet |
| API key | Tailscale: an API access token (devices:core:read). Headscale: headscale apikeys create |
| An offline device is | Laptops and phones go offline all the time; 'down' sends host.down |

## Actions

- **Check connection** (run)
- **Read devices** (run)

## Releasing

Bump `version` in `plugin.yaml`, add a `## <version>` section to `CHANGELOG.md`, commit, then
publish a GitHub release tagged `v<version>` (web UI, or `gh release create v<version> --target main --notes ""`).
The release workflow signs the plugin with the `LABDEX_SIGNING_KEY` secret, attaches the zip and
`CHANGELOG.md` to the release and puts that version's CHANGELOG section into its description.
Files listed in `.releaseignore` stay out of the zip.
