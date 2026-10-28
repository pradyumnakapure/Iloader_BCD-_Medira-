# iLoader Memory+ — Unofficial BCD & iOS IPA Installer

**An unofficial iLoader modification for installing compatible iOS applications through USB, with Increased Memory Limit requested during signing and a dedicated one-click BCD installer.**

<p align="center">
  <a href="https://paypal.me/PRADYUMNAKAPURE">
    <img src="https://img.shields.io/badge/Donate-PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white" alt="Donate via PayPal" />
  </a>
  <a href="upi://pay?pa=pradumna.kapure%40ptyes&pn=Pradyumna%20Kapure&cu=INR&tn=Support%20iLoader%20Memory%2B">
    <img src="https://img.shields.io/badge/Donate-UPI%20India-5F259F?style=for-the-badge" alt="Donate using UPI" />
  </a>
</p>

<p align="center">
  <a href="https://t.me/iloadersupport">
    <img src="https://img.shields.io/badge/Telegram-Join%20Support%20Channel-26A5E4?style=for-the-badge&logo=telegram&logoColor=white" alt="Join Telegram Support Channel" />
  </a>
</p>

**Quick links:** [Telegram Support](https://t.me/iloadersupport) · [Download Latest Release](../../releases/latest) · [Donate via PayPal](https://paypal.me/PRADYUMNAKAPURE) · [Donate via UPI - pradyumna.kapure@pytes]

If you find this project useful, please consider supporting independent development. Contributions help with installation improvements, testing, compatibility work, and future updates. Every contribution is appreciated!

---

## Project Status

**Status: Working — frontend and Rust checks passed; developer reports the BCD installation is working.**

This unofficial modification adds a dedicated **BCD (Memory+)** installation option to the existing iLoader application while preserving the original installation and device-management features.

| Feature | Status |
|---|---|
| Frontend production build | ✅ Passed |
| Rust backend compilation check | ✅ Passed |
| Dedicated BCD (Memory+) button | ✅ Implemented |
| Download latest BCD release | ✅ Implemented |
| IPA extraction | ✅ Implemented |
| Existing iLoader signing workflow | ✅ Integrated |
| USB installation workflow | ✅ Integrated |
| Madeira (Memory+) installer | ✅ Preserved |
| Import IPA functionality | ✅ Preserved |
| Increased Memory Limit requested during signing | ✅ Implemented |
| EVA authorization across different signing profiles | ⚠️ Not guaranteed |
| Compatibility with every iOS application or game | ⚠️ Not guaranteed |

These checks establish that the code builds successfully. They do not mean every application, entitlement, device, or game has been independently tested.

## Features

### Memory+ IPA Installation

- Install compatible iOS application packages (`.ipa`) from a Windows PC.
- Use iLoader's existing Apple-account and signing workflow.
- Request the Increased Memory Limit entitlement during signing.
- Install applications to a connected iPhone or iPad.
- Import a local IPA through the existing Import IPA option.
- Follow download, extraction, and installation progress.
- Retain the original iLoader account and device-management features.

**Entitlement note:** Increased Memory Limit is requested during signing, but whether it is granted depends on the signing method and authorized provisioning profile. Extended Virtual Addressing (EVA) is a separate capability and is not guaranteed by this modification.

### One-Click BCD (Memory+) Installer

The main addition is a dedicated **BCD (Memory+)** button.

The installation workflow:

1. Queries the official BCD GitHub Releases API when installation starts.
2. Finds an IPA asset in the latest release.
3. Downloads the IPA.
4. Verifies a matching published SHA-256 checksum when one is available.
5. Extracts the IPA and locates its application bundle.
6. Passes the extracted app through iLoader's existing signing and installation workflow.
7. Installs it on the selected, connected device.

Official BCD repository: https://github.com/thebcd69/bcd-games

Latest BCD releases: https://github.com/thebcd69/bcd-games/releases

The current downloader selects the first IPA asset returned in the latest release. If multiple IPA assets are published, the intended asset may need to be selected explicitly.

### Existing Features Retained

- Madeira (Memory+) installation.
- Import IPA.
- Apple account sign-in.
- Connected-device selection.
- Device pairing functionality.
- Certificate and App ID management.
- Installation progress and error reporting.

## Requirements

### Windows PC

- Windows PC with the dependencies required by iLoader.
- USB cable compatible with your iPhone or iPad.
- iTunes device support or the equivalent USB device support required by iLoader.
- Internet access for downloading BCD.
- A supported Apple account configured in iLoader.
- Bun and Rust for development builds.

### iPhone or iPad

- A compatible iOS or iPadOS device.
- A USB connection to the computer.
- Device unlocked and trusted by the computer.
- A supported signing and provisioning setup.
- Sufficient storage for the application and its data.

BCD has additional device, iOS-version, JIT and hardware requirements. Check its [official documentation](https://github.com/thebcd69/bcd-games) before attempting to run games.

## How to Use

### Install an IPA

1. Open iLoader Memory+ on Windows.
2. Connect your iPhone or iPad by USB.
3. Unlock the device and approve the Trust This Computer prompt if it appears.
4. Sign in through iLoader.
5. Select the connected device.
6. Click **Import IPA**.
7. Select the compatible IPA file.
8. Follow the installation progress and resolve any displayed errors.

### Install BCD with Memory+

1. Open iLoader Memory+.
2. Connect and select your device.
3. Sign in through iLoader.
4. Click **BCD (Memory+)**.
5. Allow the latest release to download.
6. Allow the IPA to extract and the application to be signed.
7. Wait for installation to finish.
8. Open BCD on your device and follow its setup instructions for JIT and other required components.

### Install Madeira with Memory+

The existing Madeira (Memory+) button remains available and continues to use its own download, extraction, signing, and installation workflow.

## Game Compatibility and Benchmarks

BCD is a separate project for running selected Windows PC games on iPhone and iPad. It uses Wine, FEX, DXMT, Metal and other components to run and render Windows applications on Apple hardware.

The following information comes from the upstream BCD project and its tester reports. **These are not benchmarks produced by this iLoader modification, and the FPS values are not guaranteed on every device.**

### Published FPS Reports

| Game | Reported hardware and settings | Reported performance |
|---|---|---|
| Final Fantasy VII Remake Intergrade | M5 iPad Pro, low settings, 900p | 30 FPS |
| Kingdom Hearts III | M5 iPad Pro, highest settings | Mostly 60 FPS |
| Metro 2033 Redux | iPhone 17 Pro, tessellation disabled | 60 FPS |
| Ratchet & Clank: Rift Apart | Upstream work-in-progress report | Around 20 FPS with visual glitches |

Performance varies substantially with hardware, graphics settings, game version, memory requirements, iOS version, and thermal conditions.

### Games With Built-In Tuned Settings

The upstream BCD project lists tuned settings for these games:

| Game | Compatibility information |
|---|---|
| God of War | Built-in tuned settings |
| Ghost of Tsushima | Built-in tuned settings |
| Horizon Zero Dawn | Built-in tuned settings |
| Horizon Forbidden West | Built-in tuned settings |
| Red Dead Redemption 2 | Tuned settings, including Rockstar Launcher support |
| Grand Theft Auto V Legacy | Built-in tuned settings |
| Grand Theft Auto V Enhanced | Built-in tuned settings |
| Grand Theft Auto IV: The Complete Edition | Built-in tuned settings |
| Counter-Strike 2 | Built-in tuned settings |
| Crysis Remastered | Built-in tuned settings |
| Crysis 2 Remastered | Built-in tuned settings |
| Crysis 3 Remastered | Built-in tuned settings |

**Tuned settings do not guarantee that a game starts, runs smoothly, or can be completed.** Consult the upstream compatibility information for the latest results.

### Games Reported Running by Testers

The upstream BCD README lists the following games as having reached gameplay in tester logs or reports:

- Celeste
- Cleared Hot
- Dark Souls II: Scholar of the First Sin
- Dead Space (2008)
- DELTARUNE
- Doom 3
- Fallout: New Vegas
- Far Cry 3
- Final Fantasy VII Remake Intergrade
- Kingdom Hearts III
- Marie's Room
- METAL GEAR SOLID: Peace Walker — Master Collection Version
- Metro 2033 Redux
- Moonlighter
- Timberborn
- Tomb Raider (2013)
- Warcraft II: Battle.net Edition

These reports do not establish that every title was completed from start to finish. Compatibility and performance depend on the device and settings, and many games may not work yet.

### Additional Games Receiving Settings or Compatibility Work

The upstream BCD release notes have also mentioned settings, fixes, or troubleshooting for games including:

- Clair Obscur: Expedition 33
- Grand Theft Auto IV
- Grand Theft Auto: San Andreas — The Definitive Edition
- Grand Theft Auto: Vice City
- Unrailed! 2
- Spelunky 2
- Stellar Blade demo
- FINAL FANTASY RESONANCE demo
- Phoenix Wright: Ace Attorney Trilogy
- LEGO Party!
- 1000xRESIST
- Monster Hunter Stories 3 (Trial)
- Monster Hunter Rise
- No Rest for the Wicked
- Marvel's Spider-Man Remastered
- Marvel's Spider-Man: Miles Morales
- Need for Speed Underground 2
- Jetboard Joust
- STAR WARS Galactic Racer
- BeamNG.drive
- BlazBlue Entropy Effect
- DARK SOULS III
- RAIDOU Remastered
- Yakuza: Like a Dragon
- Batman: Arkham City GOTY
- Lonely Mountains: Snow Riders
- Subnautica 2
- Red Dead Redemption
- Resident Evil 2
- Resident Evil 7 biohazard

These titles are included as examples of ongoing upstream compatibility work. They are **not all verified as playable**, and this list does not assign an FPS benchmark to them.

**Current game compatibility and reports:** https://github.com/thebcd69/bcd-games

**Latest release notes:** https://github.com/thebcd69/bcd-games/releases

## Important Memory and JIT Notes

### Increased Memory Limit

This modification requests Increased Memory Limit during the existing app-signing workflow. The resulting app's actual entitlements should be inspected if confirmation is required.

### Extended Virtual Addressing (EVA)

EVA is separate from Increased Memory Limit. This project does not guarantee that EVA will be authorized or enabled. Entitlements are controlled by the signing method and provisioning profile.

### JIT

BCD requires JIT for its Windows-game execution workflow. Successfully installing BCD does not automatically confirm that JIT is configured or available. Follow the setup instructions in the official BCD documentation.

## Building From Source

### Prerequisites

Install Git, Bun and Rust, and ensure the USB device support required by iLoader is configured on Windows.

### Install dependencies and build the frontend

From the project root:

```powershell
bun install
bun run build
```

### Check the Rust backend

```powershell
Set-Location ".\src-tauri"
cargo check
Set-Location ..
```

### Run in development

```powershell
bun run tauri dev
```

### Build the distributable application

```powershell
bun run tauri build
```

Check the generated installers under:

`src-tauri/target/release/bundle/`

The available installer formats depend on the project's Tauri bundle configuration.

## Troubleshooting

### Device not detected

- Unlock the device.
- Reconnect the USB cable.
- Approve the trust prompt if shown.
- Check that Apple device support is installed.
- Restart iLoader and select the device again.

### BCD download failed

- Check the internet connection.
- Open the official BCD releases page.
- Confirm the latest release contains a downloadable IPA.
- Check whether GitHub is accessible from the PC.

### Installation or signing failed

- Check the displayed error message.
- Confirm that your Apple account is signed in.
- Confirm the device is selected.
- Check signing and provisioning restrictions.
- Review iLoader logs for more detailed information.

### A game crashes or performs poorly

- Consult BCD's current compatibility information.
- Check the device-specific requirements.
- Review the game's recommended settings.
- Follow BCD's instructions for sending logs and reporting failures.

### Need Help?

For project-related questions, installation troubleshooting, and community discussion, visit the Telegram support channel:

**[➡️ Join the iLoader Support Telegram Channel](https://t.me/iloadersupport)**

When reporting a problem, include the Windows version, iOS version, device model, operation being performed, and relevant error message. Do not share Apple passwords, private keys, or other sensitive account details in public support chats.

## Credits and Upstream Projects

This project is an unofficial modification of [iLoader](https://github.com/nab138/iloader).

- **iLoader:** https://github.com/nab138/iloader
- **BCD:** https://github.com/thebcd69/bcd-games
- **Madeira:** https://github.com/willfaust/Madeira
- **Tauri:** https://tauri.app/

The original projects and their contributors retain their respective rights and licenses. Preserve original copyright notices, license files, branding requirements and applicable third-party notices.

## Licensing and Disclaimer

This repository is an unofficial community modification. It is not affiliated with, endorsed by, or supported by Apple, the original iLoader maintainers, the BCD developers, the Madeira developers, or any game publisher.

The original iLoader source is licensed under MIT, while its branding and name have separate restrictions. BCD has its own GPLv3-based licensing terms and additional notices. Review the relevant upstream license files before redistributing a modified application or any third-party assets.

This project does not include or grant rights to commercial games. Users must use legally obtained game files and their own authorized accounts.

The software is provided without a guarantee that every IPA, entitlement, device, game or configuration will work. Memory entitlements, JIT support, stability and performance depend on external restrictions and the target device.

---

## ☕ Support This Project

If iLoader Memory+ helps you, please consider supporting its continued development. Donations help fund development time, testing, compatibility improvements, bug fixes, and documentation.

<p align="center">
  <a href="https://paypal.me/PRADYUMNAKAPURE">
    <img src="https://img.shields.io/badge/Donate-PayPal-00457C?style=for-the-badge&logo=paypal&logoColor=white" alt="Donate via PayPal" />
  </a>
  <a href="upi://pay?pa=pradumna.kapure%40ptyes&pn=Pradyumna%20Kapure&cu=INR&tn=Support%20iLoader%20Memory%2B">
    <img src="https://img.shields.io/badge/Donate-UPI%20India-5F259F?style=for-the-badge" alt="Donate using UPI" />
  </a>
</p>

### 🌍 International Donations

**[💙 Donate via PayPal](https://paypal.me/PRADYUMNAKAPURE)**

International supporters can open the PayPal.Me page and enter their contribution amount, subject to PayPal's eligibility and payment requirements.

### 🇮🇳 Donations from India

**[🇮🇳 Pay via UPI](upi://pay?pa=pradumna.kapure%40ptyes&pn=Pradyumna%20Kapure&cu=INR&tn=Support%20iLoader%20Memory%2B)**

UPI ID: `pradumna.kapure@ptyes`

Open the link on a device with a compatible UPI app. Check the recipient details in the app before confirming the payment. If the link does not open, use the UPI ID directly in your payment app.

### Telegram Community Support

Need help, want to report a bug, or have suggestions for future versions?

**[💬 Join the iLoader Support Channel on Telegram](https://t.me/iloadersupport)**

### Thank You!

Every contribution, no matter the size, is appreciated. Your support helps me keep improving this project and making it more useful for the community.

Contributions are voluntary and do not guarantee particular features, support, or release dates.

**Thank you for supporting independent development! ❤️**

This is an independent community project and is not affiliated with Apple or the original iLoader maintainers.
