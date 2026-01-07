# ProtonPass CLI Binary Mirror

This repository mirrors the official [ProtonPass CLI](https://github.com/protonpass/pass-cli) binaries with daily updates.

> **Note**: This is an unofficial mirror. For the most up-to-date information and official support, please visit the [ProtonPass CLI documentation](https://protonpass.github.io/pass-cli/).

## Quick Download

### Linux

```bash
# Linux x86_64
curl -fsSL -o pass-cli https://github.com/tnfssc/protonpass-cli-bin/releases/latest/download/pass-cli-linux-x86_64
chmod +x pass-cli

# Linux aarch64
curl -fsSL -o pass-cli https://github.com/tnfssc/protonpass-cli-bin/releases/latest/download/pass-cli-linux-aarch64
chmod +x pass-cli
```

### macOS

```bash
# macOS x86_64 (Intel)
curl -fsSL -o pass-cli https://github.com/tnfssc/protonpass-cli-bin/releases/latest/download/pass-cli-macos-x86_64
chmod +x pass-cli

# macOS aarch64 (Apple Silicon)
curl -fsSL -o pass-cli https://github.com/tnfssc/protonpass-cli-bin/releases/latest/download/pass-cli-macos-aarch64
chmod +x pass-cli
```

### Windows (PowerShell)

```powershell
Invoke-WebRequest -Uri https://github.com/tnfssc/protonpass-cli-bin/releases/latest/download/pass-cli-windows-x86_64.zip -OutFile pass-cli.zip
Expand-Archive -Path pass-cli.zip -DestinationPath .
```

## Installation with mise

If you use [mise](https://mise.jdx.dev/), you can install ProtonPass CLI directly from this mirror using the built-in `github` backend.

### Prerequisites

- [mise installed](https://mise.jdx.dev/installing-mise.html)

### Quick Install

Install the latest version:

```bash
mise use github:tnfssc/protonpass-cli-bin
```

This will:
- Automatically detect your platform (OS and architecture)
- Download the appropriate binary
- Install and make it available

### Install a Specific Version

```bash
# Install version 1.3.2
mise use github:tnfssc/protonpass-cli-bin@1.3.2

# Or always use latest
mise use github:tnfssc/protonpass-cli-bin@latest
```

### List Available Versions

```bash
mise ls-remote github:tnfssc/protonpass-cli-bin
```

### Update to Latest Version

```bash
mise upgrade github:tnfssc/protonpass-cli-bin
```

### Persistent Configuration

To make the installation persistent across shell sessions, add this to your `~/.config/mise/config.toml`:

```toml
[tools]
"github:tnfssc/protonpass-cli-bin" = { version = "latest", asset_pattern = "pass-cli-linux-x86_64", bin = "pass-cli" }
```

Replace `asset_pattern` with your platform's binary:

| Platform | Architecture | asset_pattern |
|----------|--------------|---------------|
| Linux | x86_64 | `pass-cli-linux-x86_64` |
| Linux | aarch64 | `pass-cli-linux-aarch64` |
| macOS | x86_64 (Intel) | `pass-cli-macos-x86_64` |
| macOS | aarch64 (Apple Silicon) | `pass-cli-macos-aarch64` |

### Using the Tool

After installation, you can run the binary using mise exec:

```bash
mise exec -- pass-cli --version
mise exec -- pass-cli login
```

Or if you have mise properly activated in your shell, you can run it directly:

```bash
pass-cli --version
pass-cli login
```

> **Note:** Check the installed binary path with `mise where github:tnfssc/protonpass-cli-bin` to verify the exact location.

## Verification

Always verify the binary integrity using the SHA256 checksums:

```bash
# Download checksums
curl -fsSL -O https://github.com/tnfssc/protonpass-cli-bin/releases/latest/download/SHA256SUMS

# Verify your binary
sha256sum -c SHA256SUMS --ignore-missing
```

Or manually check the hash:

```bash
# On Linux/macOS
sha256sum pass-cli
# On Windows
certutil -hashfile pass-cli SHA256
```

## Installation

### Install to a directory in your PATH

```bash
# Move to ~/.local/bin (recommended)
mv pass-cli ~/.local/bin/

# Or install to /usr/local/bin (requires sudo)
sudo mv pass-cli /usr/local/bin/
```

### Log in to ProtonPass

```bash
pass-cli login
```

## Available Versions

Browse all releases: [Releases page](https://github.com/tnfssc/protonpass-cli-bin/releases)

Download a specific version by replacing `latest` with the version tag:

```bash
curl -fsSL -o pass-cli https://github.com/tnfssc/protonpass-cli-bin/releases/download/v1.3.2/pass-cli-linux-x86_64
```

## Update Schedule

This mirror is automatically updated **daily at 00:00 UTC** to include the latest stable release from the official ProtonPass CLI.

## Binary Details

Each release includes the following binaries:

| Binary | Platform | Architecture |
|--------|----------|--------------|
| `pass-cli-linux-x86_64` | Linux | x86_64 |
| `pass-cli-linux-aarch64` | Linux | ARM64 |
| `pass-cli-macos-x86_64` | macOS | x86_64 (Intel) |
| `pass-cli-macos-aarch64` | macOS | ARM64 (Apple Silicon) |
| `pass-cli-windows-x86_64.zip` | Windows | x86_64 |

## Official Sources

- **ProtonPass CLI Repository**: https://github.com/protonpass/pass-cli
- **ProtonPass CLI Documentation**: https://protonpass.github.io/pass-cli/
- **ProtonPass**: https://proton.me/pass

## Support

For issues, questions, or feature requests related to the ProtonPass CLI itself, please use the official channels:

- [GitHub Issues](https://github.com/protonpass/pass-cli/issues)
- [ProtonPass Community](https://proton.me/support)

For issues specific to this mirror (e.g., missing releases, broken downloads), please [open an issue](https://github.com/tnfssc/protonpass-cli-bin/issues).

## License

The ProtonPass CLI is licensed under the GNU General Public License v3.0. See the [official repository](https://github.com/protonpass/pass-cli) for more details.
