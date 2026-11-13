# Hush App Builder

Automated CI builder for Hush-patched social applications, powered by [SysAdminDoc](https://github.com/SysAdminDoc) patches and [Morphe](https://github.com/MorpheApp).

[![Build Status](https://github.com/moch1oka/hush-builder/actions/workflows/ci.yml/badge.svg)](https://github.com/moch1oka/hush-builder/actions/workflows/ci.yml)
[![Latest Release](https://img.shields.io/github/v/release/moch1oka/hush-builder?sort=date&label=Release)](https://github.com/moch1oka/hush-builder/releases)

---

## Supported Applications

| Application | Package Name | Patch Source | Target Architecture |
|---|---|---|---|
| **Facebook Hush** | `com.facebook.katana` | [SysAdminDoc/Hushfacebook](https://github.com/SysAdminDoc/Hushfacebook) | `arm64-v8a` |
| **Messenger Hush** | `com.facebook.orca` | [SysAdminDoc/HushMessenger](https://github.com/SysAdminDoc/HushMessenger) | `arm64-v8a` |
| **Instagram Hush** | `com.instagram.android` | [SysAdminDoc/HushGram](https://github.com/SysAdminDoc/HushGram) | `arm64-v8a` |
| **Threads Hush** | `com.instagram.barcelona` | [SysAdminDoc/HushThreads](https://github.com/SysAdminDoc/HushThreads) | `arm64-v8a` |
| **TikTok Hush** | `com.zhiliaoapp.musically` | [SysAdminDoc/hushfeed](https://github.com/SysAdminDoc/hushfeed) | `arm64-v8a` |

---

## Downloads and Installation

### 1. Direct Download
Download the latest standalone APKs directly from [GitHub Releases](https://github.com/moch1oka/hush-builder/releases).

### 2. Obtainium (Recommended for Auto-Updates)
You can track and install updates for all 5 apps automatically using [Obtainium](https://github.com/ImranR98/Obtainium):

- **Import via Link:** Copy the deep link in [`hush-linkobtainium.txt`](./hush-linkobtainium.txt) and open it in Obtainium.
- **Import via File:** In Obtainium, go to `Import / Export` -> `Import from Storage` and select [`hush-obtainium-config.json`](./hush-obtainium-config.json).

---

## Features

- **Automated Upstream Checking:** Scheduled GitHub Actions workflow runs daily to detect new patch releases from SysAdminDoc.
- **Standalone Non-Root APKs:** Pre-patched APKs signed with custom keystore, ready for installation on any non-rooted or rooted device.
- **Optimized Size:** Uses native `--striplibs` via Morphe CLI to strip unneeded native architectures while maintaining proper library alignment.
- **Direct CDN Integration:** Automated stock APK downloading via APKPure CDN with apkeep fallback.

---

## Configuration

Settings can be customized in [`config.toml`](./config.toml). See [`CONFIG.md`](./CONFIG.md) for detailed configuration options.

---

## Credits

- [SysAdminDoc](https://github.com/SysAdminDoc) for Hush patches (Hushfacebook, HushMessenger, HushGram, HushThreads, hushfeed).
- [MorpheApp](https://github.com/MorpheApp) for Morphe CLI and patcher tooling.
- [j-hc](https://github.com/j-hc/revanced-magisk-module) for the underlying builder architecture.
