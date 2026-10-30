# Create a Bootable macOS Installation Media

This guide explains how to use the `createinstallmedia` command in Terminal to create a bootable USB installer for macOS / OS X.

## Prerequisites

1. **Format the USB Drive:**
   * Format: **Mac OS Extended (Journaled)**
   * Scheme: **GUID Partition Map**
   * Volume Name: **`MyVolume`** *(If using a different name, update the path in the commands accordingly)*.

2. **Download macOS Installer:**
   * The installer must reside in the `/Applications` folder.

> ⚠️ **Note:** The target volume (`MyVolume`) will be completely erased during this process.

## Commands by macOS / OS X Version

### macOS Sequoia (15)

```bash
sudo /Applications/Install\ macOS\ Sequoia.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Sonoma (14)

```bash
sudo /Applications/Install\ macOS\ Sonoma.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Ventura (13)

```bash
sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Monterey (12)

```bash
sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Big Sur (11)

```bash
sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Catalina (10.15)

```bash
sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Mojave (10.14)

```bash
sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS High Sierra (10.13)

```bash
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

### macOS Sierra (10.12)

```bash
sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ macOS\ Sierra.app
```

### OS X El Capitan (10.11)

```bash
sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app
```

### OS X Yosemite (10.10)

```bash
sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Yosemite.app --nointeraction
```

### OS X Mavericks (10.9)

```bash
sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Mavericks.app
```

## 🛠 Procedure & Troubleshooting

1. Execute the matching command in **Terminal**.
2. Type your **administrator password** when prompted *(characters will not appear on screen)*.
3. Confirm erasing the USB drive by typing `Y` and pressing `Enter`.
4. Wait until the process finishes with `Install media now available at "/Volumes/Install macOS..."`.