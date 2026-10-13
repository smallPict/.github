<a href="https://smallpict.app">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/smallPict/.github/main/profile/assets/banner-dark.png">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/smallPict/.github/main/profile/assets/banner-light.png">
    <img alt="SmallPict: lighter images, faster websites" src="https://raw.githubusercontent.com/smallPict/.github/main/profile/assets/banner-light.png" width="100%">
  </picture>
</a>

<p align="center">
  <a href="https://smallpict.app"><b>Website</b></a> &nbsp;·&nbsp;
  <a href="https://smallpict.app/docs"><b>Docs</b></a> &nbsp;·&nbsp;
  <a href="https://smallpict.app/api-reference"><b>API reference</b></a> &nbsp;·&nbsp;
  <a href="https://smallpict.app/pricing"><b>Pricing</b></a> &nbsp;·&nbsp;
  <a href="https://smallpict.app/dashboard"><b>Dashboard</b></a>
</p>

<br>

SmallPict turns heavy JPEGs and PNGs into **AVIF and WebP**, stores them in your own cloud bucket or ours, and serves them from a **global edge CDN**. Use it as a WordPress plugin, call the REST API from any stack, or let your AI assistant do it through MCP.

<br>

## What we build

<table>
  <tr>
    <td width="33%" valign="top">
      <h3>🧩 WordPress plugin</h3>
      Optimize the whole media library on upload or in bulk, with AVIF + WebP fallback, cloud offload and CDN rewriting. No server CPU load.
      <br><br>
      <a href="https://wordpress.org/plugins/smallpict/">wordpress.org</a> · <a href="https://github.com/smallPict/smallpict-wp">smallpict-wp</a>
    </td>
    <td width="33%" valign="top">
      <h3>⚡ API &amp; SDKs</h3>
      One REST API with official SDKs for seven languages: compress, resize, convert and purge the CDN from your own backend.
      <br><br>
      <a href="https://smallpict.app/docs">Docs</a> · <a href="https://github.com/smallPict/smallpict-sdk">OpenAPI spec</a>
    </td>
    <td width="33%" valign="top">
      <h3>🤖 MCP server</h3>
      Give Claude, Cursor and other MCP clients image optimization tools with one line of config.
      <br><br>
      <a href="https://www.npmjs.com/package/@smallpict/mcp">npm</a> · <a href="https://github.com/smallPict/smallpict-mcp">smallpict-mcp</a>
    </td>
  </tr>
</table>

## Official SDKs

| | Package | Latest | Install |
|---|---|---|---|
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/nodejs/nodejs-original.svg" width="18"> **Node.js** | [`@smallpict/sdk`](https://github.com/smallPict/smallpict-node) | [![npm](https://img.shields.io/npm/v/@smallpict/sdk?style=flat-square&label=&color=0D5385)](https://www.npmjs.com/package/@smallpict/sdk) | `npm install @smallpict/sdk` |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/python/python-original.svg" width="18"> **Python** | [`smallpict`](https://github.com/smallPict/smallpict-python) | [![PyPI](https://img.shields.io/pypi/v/smallpict?style=flat-square&label=&color=0D5385)](https://pypi.org/project/smallpict/) | `pip install smallpict` |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/php/php-original.svg" width="18"> **PHP** | [`smallpict/smallpict-php`](https://github.com/smallPict/smallpict-php) | [![Packagist](https://img.shields.io/packagist/v/smallpict/smallpict-php?style=flat-square&label=&color=0D5385)](https://packagist.org/packages/smallpict/smallpict-php) | `composer require smallpict/smallpict-php` |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/go/go-original.svg" width="18"> **Go** | [`smallpict-go`](https://github.com/smallPict/smallpict-go) | [![Go](https://img.shields.io/github/v/tag/smallPict/smallpict-go?style=flat-square&label=&color=0D5385)](https://pkg.go.dev/github.com/smallpict/smallpict-go) | `go get github.com/smallpict/smallpict-go` |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/ruby/ruby-original.svg" width="18"> **Ruby** | [`smallpict`](https://github.com/smallPict/smallpict-ruby) | [![Gem](https://img.shields.io/gem/v/smallpict?style=flat-square&label=&color=0D5385)](https://rubygems.org/gems/smallpict) | `gem install smallpict` |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/rust/rust-original.svg" width="18"> **Rust** | [`smallpict`](https://github.com/smallPict/smallpict-rust) | [![crates.io](https://img.shields.io/crates/v/smallpict?style=flat-square&label=&color=0D5385)](https://crates.io/crates/smallpict) | `cargo add smallpict` |
| <img src="https://cdn.jsdelivr.net/gh/devicons/devicon@v2.16.0/icons/java/java-original.svg" width="18"> **Java / Kotlin** | [`app.smallpict:smallpict-java`](https://github.com/smallPict/smallpict-java) | [![Maven Central](https://img.shields.io/maven-central/v/app.smallpict/smallpict-java?style=flat-square&label=&color=0D5385)](https://central.sonatype.com/artifact/app.smallpict/smallpict-java) | Maven / Gradle |

Working example apps for every language live in [**smallpict-usecase**](https://github.com/smallPict/smallpict-usecase).

## Quick start

```ts
import { SmallPictClient } from '@smallpict/sdk';
import { readFileSync } from 'node:fs';

const client = new SmallPictClient({ apiKey: process.env.SMALLPICT_API_KEY! });

const result = await client.optimize(readFileSync('./hero.png'), {
  format: 'avif',
  quality: 80,
  maxWidth: 1920,
});

console.log(result.url, `saved ${result.savingsPercentage}%`);
```

<details>
<summary><b>Use it from an AI assistant (MCP)</b></summary>
<br>

```json
{
  "mcpServers": {
    "smallpict": {
      "command": "npx",
      "args": ["-y", "@smallpict/mcp"],
      "env": { "SMALLPICT_API_KEY": "sp_sdk_..." }
    }
  }
}
```

</details>

Get an API key from the [dashboard](https://smallpict.app/dashboard).

## Community &amp; support

- 📖 Questions about the API: start with the [docs](https://smallpict.app/docs)
- 🐛 Found a bug in an SDK or plugin: open an issue in that repository
- 🔒 Security issue: email [security@smallpict.app](mailto:security@smallpict.app), please don't open a public issue
- 💬 Everything else: [support@smallpict.app](mailto:support@smallpict.app)

<br>

<p align="center">
  <sub>Made with care for a faster web · <a href="https://smallpict.app">smallpict.app</a></sub>
</p>
