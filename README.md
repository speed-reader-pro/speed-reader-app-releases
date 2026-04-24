# Speed Reader for macOS — Releases

Public download host for [Speed Reader](https://speed-reader.pro), a native macOS speed-reading app. Source code is kept in a private repository; this repo only stores distributable builds and the Sparkle update feed.

System requirements: **macOS 14 Sonoma or later**.

## Installation

### Homebrew

```bash
brew install --cask speed-reader-pro/tap/speed-reader
```

Or, equivalently:

```bash
brew tap speed-reader-pro/tap
brew install --cask speed-reader
```

### Direct DMG

1. Download the latest build: **[SpeedReader.dmg](https://github.com/speed-reader-pro/speed-reader-app-releases/releases/latest/download/SpeedReader.dmg)**.
2. Open it and drag **Speed Reader.app** into `Applications`.
3. Launch the app. On first open, macOS may prompt for permission — click **Open**.

## Updates

Speed Reader ships with Sparkle auto-updates — once installed, new versions are fetched automatically regardless of how you installed the app. Manual check: **Speed Reader menu → Check for Updates…**

You can also update from the terminal:

```bash
brew update
brew upgrade speed-reader          # if installed via brew
```

Sparkle and Homebrew happily coexist on the same install — both paths land the same signed & notarized DMG, so whichever updates first wins and the other sees no work to do.
