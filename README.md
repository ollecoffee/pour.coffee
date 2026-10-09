# pour.coffee

[A no-nonsense pour over guide](https://pour.coffee): why I switched, the gear I
use, my brew step by step, and a few other recipes. Built with
[Astro](https://astro.build), Tailwind and daisyUI, and deployed to GitHub
Pages.

## Development

```sh
pnpm install   # CI installs with --frozen-lockfile
pnpm dev       # localhost:4321
pnpm build
```

## Structure

It is one page, `src/pages/index.astro`, assembled from `BrewStep`,
`RecipeCard` and `AffiliateCard` in `src/components/`. Site title and links
live in `src/data/config.json`.

Part of [olle.coffee](https://olle.coffee), alongside
[espresso.tools](https://espresso.tools).

## Why there is a pnpm-workspace.yaml

This is not a workspace. pnpm blocks dependency build scripts by default, and
the Astro build fails unless esbuild is allowed to run its postinstall, which
links its platform binary. pnpm 11 moved that setting out of `package.json`, so
`allowBuilds` has to live in this file.
