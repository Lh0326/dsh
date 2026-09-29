# DeepSeek Harness

English | [中文](README.zh.md)

> **Lh0326's fork of [deepseek-ai/deepseek-harness](https://github.com/deepseek-ai/deepseek-harness).** This repository provides a source checkout for studying and extending the upstream harness. The related [dsh-pet-desktop](https://github.com/Lh0326/dsh-pet-desktop) project adds a desktop pet interface in a separate repository.

DeepSeek Harness (`dsh`) is an open-source agent harness developed by [DeepSeek AI](https://deepseek.com).

It uses an architecture where **everything is a plugin**, and is powered by [Cordis](https://github.com/cordiverse/cordis), whose design is described in [_A Programming Paradigm for Spatiotemporal Composability_](https://github.com/cordiverse/paper).

## What you can explore

- **Run an agent:** use the Web UI or a headless profile to work with project files, commands, plans, and delegated tasks.
- **Compose capabilities:** assemble model providers, tools, permissions, and session services through Cordis plugins and profile configuration.
- **Build integrations:** use the TypeScript or Python SDK, or develop a plugin using the existing extension points.

These capabilities come from the upstream project. This fork's README distinguishes the source checkout below from the upstream npm release.

## Developer preview

DeepSeek Harness is currently in _developer preview_ and is iterating rapidly. **THERE WILL BE COMPATIBILITY-BREAKING CHANGES.**

## Run

### Run from `npm`

With Node.js 22.19+ in the 22.x line, or Node.js 24+, run the upstream published package:

```sh
npx @deepseek-ai/dsh web
```

The command starts the Web UI, served at `http://127.0.0.1:3080` by default. Open **Settings → Models** to configure a provider, then select a workspace before sending a task. See [Web UI guide](docs/user/guide/index.md).

### Run from source

To run this fork, use the same Node.js requirement and the `pnpm@11.7.0` version pinned in [package.json](package.json). Installation and build require network access; running model tasks requires a configured provider.

```sh
git clone https://github.com/Lh0326/dsh.git
cd dsh
pnpm install --frozen-lockfile
pnpm run build
pnpm dsh web
```

The server prints its listening URL. For other launch modes and arguments, see the [CLI reference](apps/cli/README.md). If setup fails, check the required runtime versions and the [development guide](docs/development.md) before changing the lockfile.

## Source reading map

| Start here | What it covers |
|---|---|
| [Architecture](docs/architecture.md) | Plugin composition, the agent loop, and extension points |
| [Package groups](packages/README.md) | How capabilities are divided across packages |
| [Runnable examples](examples/README.md) | Example configurations and application entry points |
| [Plugin development](docs/user/develop/basic/) | Creating and composing your own plugin |
| [TypeScript SDK](packages/sdk/README.md) / [Python SDK](python/README.md) | Integrating the harness into another application |

## Community and support

- Feel free to submit feedback or bug reports through [GitHub Discussions](https://github.com/deepseek-ai/deepseek-harness/discussions).
- Add the [`dsh-plugin`](https://github.com/topics/dsh-plugin) topic to your plugin repository for discoverability.
- Join <a href="https://discord.gg/Ycq5dCaS4">DeepSeek Harness Discord community</a>.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Development

Start with the [development guide](docs/development.md) and [architecture documentation](docs/architecture.md).

For agents, follow [AGENTS.md](AGENTS.md).

## License

[MIT](LICENSE)

Third-party dependencies and their licenses are disclosed in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
