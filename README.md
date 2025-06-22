# Unofficial .deb Packages for Microsoft Edit

This repository automatically tracks the upstream releases of [microsoft/edit](https://github.com/microsoft/edit) and builds verified `.deb` packages for Ubuntu and Debian-based distributions.

To install, download the latest `.deb` package matching your architecture from the [Releases](https://github.com/MohamedElashri/edit/releases) page.

After downloading, verify the package integrity using the provided SHA256 hash:

```bash
sha256sum -c edit-<version>-<arch>.deb.sha256
````

If verification passes, install the package:

```bash
sudo dpkg -i edit-<version>-<arch>.deb
```

Replace `<version>` and `<arch>` with the values appropriate for your system (e.g., `1.2.0` and `amd64` or `arm64`).

Packages are rebuilt and published automatically within 24 hours of an upstream release.

