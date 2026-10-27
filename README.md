![GitHub Downloads (all assets, all releases)](https://img.shields.io/github/downloads/gaofengnan/zoxide-debian/total)
![GitHub Downloads (all assets, latest release)](https://img.shields.io/github/downloads/gaofengnan/zoxide-debian/latest/total)
![GitHub Release](https://img.shields.io/github/v/release/gaofengnan/zoxide-debian)
![GitHub Release Date](https://img.shields.io/github/release-date/gaofengnan/zoxide-debian)

<h1>
   <p align="center">
     <a href="https://zoxide.org/"><img src="https://github.com/gaofengnan/zoxide-debian/blob/main/zoxide-logo.png" alt="zoxide Logo" width="128" style="margin-right: 20px"></a>
     <a href="https://www.debian.org/"><img src="https://github.com/gaofengnan/zoxide-debian/blob/main/debian-logo.png" alt="Debian Logo" width="104" style="margin-left: 20px"></a>
     <br>zoxide for Debian
   </p>
</h1>
<p align="center">
 zoxide is a smarter cd command, inspired by z and autojump.
</p>

# zoxide for Debian

> Fork of [dariogriffo/zoxide-debian](https://github.com/dariogriffo/zoxide-debian) (MIT); the original packaging is by Dario Griffo. Served at [deb.gaofn.xyz](https://deb.gaofn.xyz) for Debian 12 (bookworm) and 13 (trixie).

This repository contains build scripts to produce the _unofficial_ Debian packages
(.deb) for [zoxide](https://github.com/ajeetdsouza/zoxide/) hosted at [deb.gaofn.xyz](https://deb.gaofn.xyz)

Currently supported Debian distros are:
- Bookworm (v12)
- Trixie (v13)
- Forky (v14)
- Sid (testing)

Currently supported Ubuntu distros are:
- Jammy (22.04)
- Noble (24.04)
- Questing (25.10)
- Resolute (26.04)

Supported architectures:
- amd64 (x86_64) - All distributions
- arm64 (aarch64) - All distributions
- armel (ARM EABI) - Debian only
- armhf (ARM hard float) - All distributions
- i386 (x86 32-bit) - Debian only
- riscv64 (RISC-V 64-bit) - Trixie, Forky, Sid, Noble and later

The packages include the zoxide binary, man pages and shell completions for
bash, fish and zsh.

This is an unofficial community project to provide a package that's easy to
install on Debian. If you're looking for the zoxide source code, see
[zoxide](https://github.com/ajeetdsouza/zoxide/).

## Install/Update

### The Debian way

```sh
sudo install -d -m 0755 /etc/apt/keyrings
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.gpg -o /etc/apt/keyrings/deb.gaofn.xyz.gpg
sudo curl -fsSL https://deb.gaofn.xyz/deb.gaofn.xyz.sources -o /etc/apt/sources.list.d/deb.gaofn.xyz.sources
# Debian 12 (bookworm): fetch deb.gaofn.xyz-bookworm.sources instead
sudo apt update
sudo apt install -y zoxide
```

### Manual Installation

1. Download the .deb package for your Debian version available on
   the [Releases](https://github.com/gaofengnan/zoxide-debian/releases) page.
2. Install the downloaded .deb package.

```sh
sudo dpkg -i <filename>.deb
```
## Updating

To update to a new version, just follow any of the installation methods above. There's no need to uninstall the old version; it will be updated correctly.

## Building

### Build for single architecture
```sh
./build.sh <zoxide_version> <build_version> <architecture>
# Example: ./build.sh 0.10.0 1 arm64
```

### Build for all architectures
```sh
./build.sh <zoxide_version> <build_version> all
# Example: ./build.sh 0.10.0 1 all
```

## Roadmap

- [x] Produce a .deb package on GitHub Releases
- [x] Set up a debian mirror for easier updates
- [x] Multi-architecture support (amd64, arm64, armel, armhf, riscv64, i386)

## Disclaimer

- This repo is not open for issues related to zoxide. This repo is only for _unofficial_ Debian packaging.
