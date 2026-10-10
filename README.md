# TurboWarp-Kamishibai Site Navigation

Shared site navigation contract, renderer, and shell assets for the TurboWarp-Kamishibai site family.

This repository is the source of truth for the navigation shared by:

- `kubohiroya/turbowarp-kamishibai-app`
- `kubohiroya/turbowarp-kamishibai-docs`
- `kubohiroya/turbowarp-kamishibai-samples`

This package was published as `@kubohiroya/tm-kamishibai-site-navigation` up to 0.1.0. Contract 2.0.0
renames the site keys to `turbowarp-kamishibai-app`, `turbowarp-kamishibai-docs`, and
`turbowarp-kamishibai-samples`, and points every link at the renamed repositories and sites.

## Usage

Install the package in a consuming site repository.

```sh
pnpm add -D @kubohiroya/turbowarp-kamishibai-site-navigation
```

Render or replace navigation from TypeScript build scripts.

```ts
import {
  NAVIGATION_CONTRACT,
  SITE_SHELL_CSS_URL,
  replaceSiteNavigation,
} from "@kubohiroya/turbowarp-kamishibai-site-navigation";
```

`SITE_SHELL_CSS_URL` points to the packaged `site-shell.css` asset. Consumers that publish a static
site should copy that file into their site output during build.

## Development

Use TypeScript for source files. JavaScript and declaration files are build output only.

```sh
pnpm install
pnpm verify
```

## Release Flow

1. Update the TypeScript source, `src/navigation-contract.json`, or `src/site-shell.css`.
2. Run `pnpm verify`.
3. Publish a new package version.
4. Update each consuming repository to the exact package version.
