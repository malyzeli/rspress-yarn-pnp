# Reproduction for `web-infra-dev/rspress` issue #1246

Repository contains a minimal reproduction
of [referenced issue](https://github.com/web-infra-dev/rspress/issues/1246), set
up based on a [Quick start](https://rspress.dev/guide/start/getting-started)
guide from Rspress website, the only difference being that we use Yarn
with [PnP](https://yarnpkg.com/features/pnp) enabled.

## Problem

**Rspress** seems unable to load dependencies when
using [Yarn PnP](https://yarnpkg.com/features/pnp) even though
it's [already supported by Rspack and Rsbuild](https://github.com/web-infra-dev/rspack/issues/2236)
(I can confirm we are using both these tools in our projects).

## Non-factors

- Doesn't matter if using
  Yarn [zero-installs](https://yarnpkg.com/features/caching#zero-installs) or
  not
- Doesn't matter if there is `type: "module"` in `package.json` or not
- Doesn't matter if `react` and `react-dom` are explicitly added as dependencies

## Reproduction steps

1. Clone this repository
2. Run `yarn install` - should be managed by Yarn 4.12.0 included in the repo
3. Run any Rspress script (`yarn build`) – it should fail with dependency
   resolution errors

Logs are included in the repository under [`logs`](./logs) folder.
