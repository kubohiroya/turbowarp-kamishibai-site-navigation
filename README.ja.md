# TurboWarp-Kamishibai Site Navigation

[English](README.md) | 日本語

TurboWarp-Kamishibai のサイト群で共有する、ナビゲーションの契約・renderer・shell assetです。

このリポジトリは、次のサイトが共有するナビゲーションのsource of truthです。

- `kubohiroya/turbowarp-kamishibai-app`
- `kubohiroya/turbowarp-kamishibai-docs`
- `kubohiroya/turbowarp-kamishibai-samples`

このpackageは0.1.0まで`@kubohiroya/tm-kamishibai-site-navigation`として公開していました。contract 2.0.0で
site keyを`turbowarp-kamishibai-app`、`turbowarp-kamishibai-docs`、`turbowarp-kamishibai-samples`へ改名し、
すべてのlinkを改名後のリポジトリとサイトへ向けています。

## 使い方

利用側のサイトリポジトリへpackageをインストールします。

```sh
pnpm add -D @kubohiroya/turbowarp-kamishibai-site-navigation
```

TypeScriptのbuild scriptからナビゲーションを生成または置換します。

```ts
import {
  NAVIGATION_CONTRACT,
  SITE_SHELL_CSS_URL,
  replaceSiteNavigation,
} from "@kubohiroya/turbowarp-kamishibai-site-navigation";
```

`SITE_SHELL_CSS_URL`はpackageに同梱した`site-shell.css`を指します。静的サイトを公開する利用側は、
build時にこのファイルをサイトの出力へコピーしてください。

## 開発

source fileにはTypeScriptを使います。JavaScriptと型宣言fileはbuild出力のみです。

```sh
pnpm install
pnpm verify
```

## リリース手順

1. TypeScript source、`src/navigation-contract.json`、`src/site-shell.css`のいずれかを更新する。
2. `pnpm verify`を実行する。
3. 新しいpackage versionを公開する。
4. 利用側の各リポジトリを、その正確なpackage versionへ更新する。
