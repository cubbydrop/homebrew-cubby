# 🔒 Cubby — CLI for CubbyDrop

Zero-knowledge encrypted file sharing from your terminal.

```
   ██████╗██╗   ██╗██████╗ ██████╗ ██╗   ██╗
  ██╔════╝██║   ██║██╔══██╗██╔══██╗╚██╗ ██╔╝
  ██║     ██║   ██║██████╔╝██████╔╝ ╚████╔╝
  ██║     ██║   ██║██╔══██╗██╔══██╗  ╚██╔╝
  ╚██████╗╚██████╔╝██████╔╝██████╔╝  ██║
   ╚═════╝ ╚═════╝ ╚═════╝ ╚═════╝   ╚═╝
```

**Encrypt files before they leave your machine.** Upload, download, and manage encrypted files on [CubbyDrop](https://cubbydrop.com) — all from the terminal. AES-256-GCM encryption happens locally; the server never sees your data.

## Install

### Homebrew (macOS & Linux)

```bash
brew tap cubbydrop/cubby
brew install cubby
```

### Direct download

```bash
curl -fsSL https://releases.cubbydrop.com/install.sh | sh
```

### Manual download

Binaries for all platforms available at [releases.cubbydrop.com](https://releases.cubbydrop.com).

| Platform | Architecture | Download |
|----------|-------------|----------|
| macOS | Apple Silicon | [cubby_0.1.0_darwin_arm64.tar.gz](https://releases.cubbydrop.com/cubby/v0.1.0/cubby_0.1.0_darwin_arm64.tar.gz) |
| macOS | Intel | [cubby_0.1.0_darwin_amd64.tar.gz](https://releases.cubbydrop.com/cubby/v0.1.0/cubby_0.1.0_darwin_amd64.tar.gz) |
| Linux | x86_64 | [cubby_0.1.0_linux_amd64.tar.gz](https://releases.cubbydrop.com/cubby/v0.1.0/cubby_0.1.0_linux_amd64.tar.gz) |
| Linux | ARM64 | [cubby_0.1.0_linux_arm64.tar.gz](https://releases.cubbydrop.com/cubby/v0.1.0/cubby_0.1.0_linux_arm64.tar.gz) |
| Windows | x86_64 | [cubby_0.1.0_windows_amd64.zip](https://releases.cubbydrop.com/cubby/v0.1.0/cubby_0.1.0_windows_amd64.zip) |
| Windows | ARM64 | [cubby_0.1.0_windows_arm64.zip](https://releases.cubbydrop.com/cubby/v0.1.0/cubby_0.1.0_windows_arm64.zip) |

## Usage

### Interactive TUI

Run `cubby` to open the interactive dashboard:

```bash
cubby
```

Navigate with arrow keys, select with Enter. Upload files, browse your uploads, check account status — all from the terminal.

### Quick commands

```bash
# Log in to your CubbyDrop account
cubby login

# Upload a file — get an encrypted share link
cubby upload secret-report.pdf

# Download and decrypt a shared file
cubby download "https://cubbydrop.com/d/abc123#encryptionKey"

# List your active files
cubby list

# Check account status
cubby status
```

### Upload options

```bash
cubby upload doc.pdf --password mysecret        # Password-protected
cubby upload doc.pdf --expiry 72                # Expires in 72 hours
cubby upload doc.pdf --max-downloads 5          # Limit downloads
cubby upload doc.pdf --delete-on-download       # Self-destruct after download
```

## How it works

1. **Encrypt locally** — AES-256-GCM encryption happens on your machine
2. **Upload encrypted** — only ciphertext reaches the server
3. **Share the link** — the encryption key is in the URL fragment (`#key`), never sent to the server
4. **Decrypt locally** — recipients decrypt on their machine too

The server never sees your plaintext. That's zero-knowledge encryption.

## Links

- [CubbyDrop](https://cubbydrop.com) — Web app
- [Integrations](https://cubbydrop.com/integrations) — Slack, Discord, Microsoft Teams
- [Privacy Policy](https://cubbydrop.com/legal/privacy)
- [Terms of Service](https://cubbydrop.com/legal/terms)
