# Getting Started

## Installation

Fatou runs on Linux, macOS, and Windows (x86_64 and arm64), and is available
from several sources.

### Cargo

Install from [crates.io](https://crates.io/crates/fatou) with Cargo:

```bash
cargo install fatou
```

### Homebrew

On macOS or Linux:

```bash
brew install jolars/tap/fatou
```

### npm

The `fatou-cli` package bundles a prebuilt binary:

```bash
npm install -g fatou-cli
```

### PyPI

Install the binary as a Python tool:

```bash
uv tool install fatou
# or
pipx install fatou
```

### AUR

On Arch Linux, install the prebuilt
[`fatou-bin`](https://aur.archlinux.org/packages/fatou-bin) package with an AUR
helper:

```bash
paru -S fatou-bin
```

### Nix

Fatou is available as `fatou` in
[Nixpkgs](https://search.nixos.org/packages?channel=unstable&show=fatou). For a
shell with Fatou available:

```bash
nix shell nixpkgs#fatou
```

For a persistent NixOS installation, add `pkgs.fatou` to
`environment.systemPackages`.

### mise and Aqua

[mise](https://mise.jdx.dev/dev-tools/backends/aqua.html) can install Fatou
through its Aqua backend:

```bash
mise use aqua:jolars/fatou
```

Commit the resulting `mise.toml` to share the selected version. With
[Aqua](https://aquaproj.github.io/docs/tutorial/) directly, run `aqua init` if
the project has no `aqua.yaml`, then add and install Fatou:

```bash
aqua g -i jolars/fatou
aqua install
```

Commit `aqua.yaml` to share the selected version. Both tools use the
[`jolars/fatou` registry
entry](https://github.com/aquaproj/aqua-registry/tree/main/pkgs/jolars/fatou).

### Install script

The installer selects the release for your platform and installs to a user-local
directory. On macOS or Linux:

```sh
curl --proto '=https' --tlsv1.2 -sSf https://fatou.dev/install | sh
```

On Windows, run this in PowerShell:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -Command "irm https://fatou.dev/install.ps1 | iex"
```

### Prebuilt binaries

Download an archive for your platform from the [releases
page](https://github.com/jolars/fatou/releases) and put the `fatou` binary on
your `PATH`.

### From source

Clone the repository and build a release binary:

```bash
git clone https://github.com/jolars/fatou
cd fatou
cargo build --release
```

The binary is written to `target/release/fatou`.

### dprint

To format Julia files with dprint, add the [Fatou dprint
plugin](integrations.md#dprint). It bundles the formatter and requires neither
Julia nor the Fatou CLI. Follow the linked recipe for setup and configuration.

## First Run

Format a file in place, then check it for lint findings:

```bash
fatou format file.jl
fatou lint file.jl
```

Lint findings cause a nonzero exit status. To apply fixes, follow the
[fix-and-format workflow](linting.md#apply-fixes).

Continue with [Formatting](formatting.md) for directory runs, checks without
writing, and preservation verification, or [Linting](linting.md) for rule
selection and suppressions. Use [Configuration](configuration.md) to share
project settings, [Editor Setup](editors.md) to connect the language server, and
[Integrations](integrations.md) to automate checks. The [CLI
Reference](../reference/cli.md) lists all commands and options.
