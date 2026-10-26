# Diana ZCode Theme 0.1.0-beta.1

Status: **public GitHub Beta; standalone archive is a visual blueprint only**.

## Public implementation

- Publishes reviewable CSS, token maps, artwork contracts, local assets, documentation, and validation.
- Publishes no executable adapter, debugging launch command, listener, local state, logs, screenshots, or target binary.
- The repository alone does not claim a live mount.

## Compatibility snapshot

Current launcher delivery: [RC.10](https://github.com/lanmengSakura/diana-multi-app-launcher/releases/tag/v0.1.0-beta.4-rc.10)
bundles a separate opt-in adapter for exact ZCode `3.16.3.8992`, alongside the
legacy `3.6.5.4145` adapter. A personal adapter registration is no longer required.
This repository's standalone archive remains artwork/CSS only. The 3.16 local
workspace evidence and public-package checks are not full logged-in or
cross-machine acceptance; see [COMPATIBILITY.md](COMPATIBILITY.md).

- Full artwork was last verified on ZCode `3.6.5.4145`.
- Day/night colors, hover/current rail states, responsive layout, and click-through artwork were checked in that build.
- A newer build requires fresh selectors and interaction validation.

## Final release gate

- Re-run the private adapter from a clean ZCode launch.
- Verify day/night, sidebar indices, rail hover/current states, long conversation, narrow/maximized layout, restart, and restore.
- Confirm decorative layers never capture pointer input or cover native controls.
- Run `npm test`, record executable signature, and inspect the public repository tree once more.
