# NestDroid releases

Signed release builds of **NestDroid**, an Android sandbox + encrypted tunnel with a Lumen OS
desktop shell, an app container, an encrypted vault, a firewall and a strict no-log policy.

**Latest: NestDroid 1.6.89** — [download the APK](nestdroid-1.6.89.apk) ·
[release notes](https://github.com/Tripartitus/nestdroid-releases/releases/tag/v1.6.89) ·
SHA-256 `2f176e648c053a847d135fb45f6aede58d929791c68103eb04c1159f0d8d5c63`

**This repository contains only release binaries and screenshots.** No source code, build scripts
or mapping files are published here. Every download is a finished, signed APK.

![NestDroid desktop, dark theme](docs/screenshots/02-desktop-dark.png)

## What's inside

- **Lumen OS desktop** — Windows 11-style Start menu, centered taskbar, floating windows, wallpapers and light/dark themes.
- **Built-in apps** — Files, Notes, Media, Terminal, Browser, Vault, Calculator, Clock and Minesweeper.
- **Sandbox and container** — isolated guest engine, virtual APK space, sealed file imports.
- **Wine and handheld** — Windows-program runtime and Game Boy / DS emulation.
- **Security** — encrypted vault, firewall, traffic monitor, TLS guard and a strict no-log policy.
- **WireGuard tunnel** — WARP or imported configs, with host-mediated egress.

## Screenshots

All screenshots are from the 1.6.89 release build.

### Desktop and shell

| | |
| --- | --- |
| ![Lock screen](docs/screenshots/01-lock-screen.png) | ![Start menu](docs/screenshots/03-start-menu.png) |
| **Lock screen** — local admin account, clock and one-tap unlock. | **Start menu** — pinned apps, recents and quick settings. |

### Built-in apps

| | |
| --- | --- |
| ![Browser](docs/screenshots/05-browser.png) | ![Notes](docs/screenshots/06-notes.png) |
| **Browser** — secure address pill, content blocker and offline start page. | **Notes** — sealed editor; notes are encrypted before they touch disk. |
| ![Calculator](docs/screenshots/07-calculator.png) | ![Clock](docs/screenshots/08-clock.png) |
| **Calculator** — themed keypad, history and tap-to-copy results. | **Clock** — clock, stopwatch and countdown timer. |

### Security and storage

| | |
| --- | --- |
| ![Security](docs/screenshots/09-security.png) | ![Vault](docs/screenshots/12-vault.png) |
| **Security** — firewall, TLS guard, traffic ledger and surveillance tools. | **Vault** — AES-256-GCM objects sealed by the device keystore. |
| ![Files](docs/screenshots/13-files.png) | ![Container](docs/screenshots/15-container.png) |
| **Files** — sealed downloads and vault objects in one browser. | **Container** — virtual package space and encrypted file imports. |

### Sandbox, Wine and handheld

| | |
| --- | --- |
| ![Terminal](docs/screenshots/14-terminal.png) | ![Sandbox](docs/screenshots/16-sandbox.png) |
| **Terminal** — Linux-style console inside the isolated guest. | **Sandbox** — engine status, virtual device and reset controls. |
| ![Wine](docs/screenshots/17-wine.png) | ![Handheld](docs/screenshots/18-handheld.png) |
| **Wine** — Windows runtime channel, graphics and controller diagnostics. | **Handheld** — Game Boy / DS emulator with on-screen controls. |

### Network, settings and themes

| | |
| --- | --- |
| ![Tunnel](docs/screenshots/19-tunnel.png) | ![Settings](docs/screenshots/04-settings-dark.png) |
| **Tunnel** — WireGuard / WARP status and custom gateway. | **Settings** — appearance, wallpaper, desktop and taskbar. |
| ![Desktop, light theme](docs/screenshots/10-desktop-light.png) | ![Settings, light theme](docs/screenshots/11-settings-light.png) |
| **Desktop, light theme** — the bloom wallpaper follows the accent. | **Settings, light theme** — the same controls in light mode. |

## Download

**NestDroid 1.6.89** is available in this repository and on the Releases page — both are the same
signed build:

- **In this repository:** [`nestdroid-1.6.89.apk`](nestdroid-1.6.89.apk)
- **From Releases:** [`nestdroid-1.6.89.apk`](https://github.com/Tripartitus/nestdroid-releases/releases/download/v1.6.89/nestdroid-1.6.89.apk)
- **Release page:** [NestDroid 1.6.89](https://github.com/Tripartitus/nestdroid-releases/releases/tag/v1.6.89)

| Version | APK | SHA-256 | Size |
| --- | --- | --- | --- |
| 1.6.89 | `nestdroid-1.6.89.apk` | `2f176e648c053a847d135fb45f6aede58d929791c68103eb04c1159f0d8d5c63` | 9,783,204 bytes |

Verify the download before installing:

```sh
sha256sum nestdroid-1.6.89.apk
```

## Install

1. Allow installs from this source on the device (Android will offer it the first time).
2. Open the APK and confirm the install. NestDroid targets API 28 and runs on Android 8.0 and newer.
3. On first launch, create the local administrator account. It stays on the device; nothing is
   registered online.

## What the release build is

- **Signed release variant:** R8-obfuscated app classes, shrunk resources, `android:debuggable="false"`
  in the merged manifest. Debug builds are never uploaded.
- **No logging:** log call sites are stripped at build time and a compile-time switch pins the no-log
  policy to strict, whatever the Settings toggle says. The diagnostics export is disabled in this build.
- **Persistent sessions:** browser cookies (site logins), encrypted downloads, imported Wine programs
  and handheld battery saves survive restarts, locking and shutdown.
- **A real reset:** Sandbox → RESET erases the account, vault, cookies, preferences, caches and the
  guest snapshot, then closes the app — the next launch is a fresh install.

## Notes

- The container is built on BCore (Apache-2.0); its license notice is bundled in the app.
- NestDroid is local-only: no analytics, no accounts on a server, no telemetry.
- These APKs are signed with a development certificate; verify the checksum above, and only install
  builds published on this page.
