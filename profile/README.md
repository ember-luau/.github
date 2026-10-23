<div align="center">

<a href="https://luaupm.com">
  <img src="https://luaupm.com/ember.png" alt="Ember logo" width="110" />
</a>

# Ember

**A package manager for Luau.**

<a href="https://luaupm.com"><img src="https://img.shields.io/badge/luaupm.com-f23c1b?style=flat-square&logoColor=white" alt="Website" /></a>
<a href="https://luaupm.com/search"><img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fcdn.luaupm.com%2Fstats.json&query=%24.packages&label=packages&color=f23c1b&style=flat-square" alt="Packages" /></a>
<a href="https://luaupm.com"><img src="https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fcdn.luaupm.com%2Fstats.json&query=%24.downloads_total&label=downloads&color=f23c1b&style=flat-square" alt="Downloads" /></a>
<a href="https://discord.gg/NYfNd7yq5n"><img src="https://img.shields.io/badge/discord-5865F2?style=flat-square&logoColor=white" alt="Discord" /></a>
<img src="https://img.shields.io/badge/license-MIT-2ea44f?style=flat-square" alt="MIT license" />

[Browse packages](https://luaupm.com/search) · [Docs](https://luaupm.com/docs) · [Policies](https://luaupm.com/policies) · [Discord](https://discord.gg/NYfNd7yq5n)

</div>

---

Ember is a package registry and a CLI, `embr`, for Luau and everything built
on it. Publish a package once, and install it in Roblox, Roblox Server,
[Lune](https://github.com/lune-org/lune), [Lute](https://github.com/luau-lang/lute),
[Seal](https://github.com/seal-runtime/seal), [Zune](https://github.com/Scythe-Technology/zune)
or plain Luau projects. Packages in Alloy, Loom and Luwu ship their own
sources too.

```sh
cargo install embr
embr self install      # puts embr and embx on PATH
```

The [latest release](https://github.com/ember-luau/ember/releases/latest) has
prebuilt binaries. Run `embr self install` on those too. The
[installation guide](https://luaupm.com/docs/installation) has the full steps.

One command adds a dependency, and one more installs it:

```sh
embr add chief/core
embr install
```

To publish, sign in with GitHub. Your first publish claims your scope:

```sh
embr publish
```

## How it works

- **Names have scopes.** Every package is `scope/name`. A scope belongs to the
  GitHub account that publishes under it first, so nobody can squat a global
  name.
- **Versions do not change.** Nobody can change or overwrite a published
  version. `embr yank` keeps a version out of new installs, and
  `embr deprecate` marks a package or a version with a reason.
- **Each project has its own rules.** The `[target]` of a project sets its
  environment and language. A package for another runtime or language fails
  the install, and the error gives the reason.
- **Downloads are free and have no limit.** An edge CDN serves the packages
  and the search index with no metering. An install in CI needs no token.
- **Wally and pesde packages work too.** `embr` resolves and installs from
  both registries, so your project can move before the ecosystem does.

## More than dependencies

The CLI also covers the rest of a Luau project:

- `embr tool` pins GitHub-released binaries, such as Rojo and darklua, for one
  project or for all of them. `embx` runs one without an install.
- `embr run` runs your project scripts with those tools on PATH.
- `embr studio` opens the place of the project in Roblox Studio.
- `embr outdated` lists the dependencies that have a newer release.
- `embr patch` edits a dependency and keeps the edit across installs.
- `embr mcp` gives a coding agent package search, as an MCP server.
- Workspaces keep a monorepo of packages in one manifest tree.

## What lives where

| Repo | What it is |
| --- | --- |
| [ember](https://github.com/ember-luau/ember) | The `embr` CLI. It installs, publishes, reads `ember.toml`, pins tools and runs scripts |
| [index](https://github.com/ember-luau/index) | Public package metadata and scope ownership, as plain files in a repo |

The registry worker behind publish, search and the API is not public, and
neither is the source of [luaupm.com](https://luaupm.com). The CLI has the MIT
license.

Found a bug? Open an issue on the repo it is in, or ask in
[Discord](https://discord.gg/NYfNd7yq5n). Found a security problem in a
package or in the registry? Send an email to
[admin@emberpm.dev](mailto:admin@emberpm.dev), and do not open a public issue.
The full rules are at [luaupm.com/policies](https://luaupm.com/policies).

<small>Luau is a trademark of Roblox Corporation. Ember is an independent project, not affiliated with or endorsed by Roblox or the Luau team.</small>
