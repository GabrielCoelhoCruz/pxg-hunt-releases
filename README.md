# pxg-hunt-releases

Public **artifacts-only** feed for [PXG Hunt Analyzer](https://github.com/GabrielCoelhoCruz/pxg-hunt-analyzer) Windows builds.

Contains installers / portable zips and `latest.yml` for `electron-updater`. **No application source.**

## Consumers

Packaged desktop builds check this repo on start and every 4 hours (`autoInstallOnAppQuit`).

## Publishers (maintainers)

From the private source repo:

```bash
# 1. Bump version in apps/desktop/package.json
# 2. Build web + desktop
pnpm desktop:build

# 3. Publish artifacts here (needs token with write to this repo)
cd apps/desktop
pnpm exec electron-builder --win --x64 --publish always
# or: pnpm --filter @pxg/desktop publish:release
```

Set `GH_TOKEN` with `contents: write` on this repository.

electron-builder publish target: `GabrielCoelhoCruz/pxg-hunt-releases`.