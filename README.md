# Unofficial Packages for Microsoft Edit

This repository automatically tracks the upstream releases of [microsoft/edit](https://github.com/microsoft/edit) and builds:

* Verified `.deb` packages for Ubuntu and Debian-based distributions.
* A standalone `edit` binary for macOS Apple Silicon (arm64).

## Linux

To install on Ubuntu/Debian, download the latest `.deb` package for your architecture from the [Releases](https://github.com/MohamedElashri/edit/releases) page.

Verify its integrity:

```bash
sha256sum -c edit-<version>-<arch>.deb.sha256
```

Then install:

```bash
sudo dpkg -i edit-<version>-<arch>.deb
```

### One-liner (latest version)

Run this command to fetch, verify, and install the latest release:

```bash
VERSION=$(curl -s https://api.github.com/repos/MohamedElashri/edit/releases/latest | jq -r .tag_name) && \
ARCH=$(dpkg --print-architecture) && \
curl -sL https://github.com/MohamedElashri/edit/releases/download/$VERSION/edit-${VERSION#v}-$ARCH-linux-gnu.deb -o edit.deb && \
curl -sL https://github.com/MohamedElashri/edit/releases/download/$VERSION/edit-${VERSION#v}-$ARCH-linux-gnu.deb.sha256 -o edit.deb.sha256 && \
sha256sum -c edit.deb.sha256 && sudo dpkg -i edit.deb
```

---

## macOS Apple Silicon (arm64)

Download the latest `edit-<version>-macos-arm64` binary and install it:

```bash
VERSION=$(curl -s https://api.github.com/repos/MohamedElashri/edit/releases/latest | jq -r .tag_name)
FILE=edit-${VERSION#v}-macos-arm64
URL=https://github.com/MohamedElashri/edit/releases/download/$VERSION/$FILE

# download binary
curl -sL $URL -o $FILE

# make executable and install
chmod +x $FILE
sudo mv $FILE /usr/local/bin/edit
```

---

Packages are rebuilt and published automatically within 24 hours of each upstream release.
