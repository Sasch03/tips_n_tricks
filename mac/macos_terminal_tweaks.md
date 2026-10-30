# macOS Terminal Tweaks & Customizations

A collection of useful Terminal commands (`defaults write`) to customize macOS and optimize the user interface.

> **Note:** Execute these commands in the **Terminal**. Some tweaks require administrative privileges (`sudo`) or restarting specific services (e.g., `killall Dock`).

## Table of Contents

* [Dock Customizations](#dock-customizations)
  * [Speed Up Dock Hiding](#speed-up-dock-hiding)
  * [Add Dock Spacers](#add-dock-spacers)
  * [Make Hidden Apps Transparent](#make-hidden-apps-transparent)
* [System & Notifications](#system--notifications)
  * [Disable Disk Eject Warning](#disable-disk-eject-warning)
* [Screenshots](#screenshots)
  * [Change Default Format to JPG](#change-default-format-to-jpg)
* [Launchpad Layout](#launchpad-layout)
* [Miscellaneous](#miscellaneous)
  * [Screen Saver as Wallpaper](#screen-saver-as-wallpaper)

## Dock Customizations

### Speed Up Dock Hiding

Removes the delay and animation when automatically hiding and showing the Dock.

**Enable:**

```bash
defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -int 0; killall Dock
```

**Undo (Default Values):**

```bash
defaults write com.apple.dock autohide-delay -float 0.5; defaults write com.apple.dock autohide-time-modifier -int 0.5; killall Dock
```

### Add Dock Spacers

Adds empty spaces to the Dock to visually group applications. Run the command multiple times for additional spacers.

**Standard Spacer:**

```bash
defaults write com.apple.dock persistent-apps -array-add '{tile-data={}; tile-type="spacer-tile";}' && killall Dock
```

**Small Spacer (Half-Height):**

```bash
defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="small-spacer-tile";}' && killall Dock
```

> **Tip:** You can remove a spacer by simply dragging it out of the Dock.

### Make Hidden Apps Transparent

Makes the icons of hidden applications (Cmd + H) semi-transparent in the Dock.

```bash
defaults write com.apple.Dock showhidden -bool TRUE && killall Dock
```

## System & Notifications

### Disable Disk Eject Warning

Disables the *"Disk Not Ejected Properly"* warning notification when disconnecting a drive without ejecting it first.

> ⚠️ **Important:** Requires restarting your Mac to fully take effect.

**Disable Warning:**

```bash
sudo defaults write /Library/Preferences/SystemConfiguration/com.apple.DiskArbitration.diskarbitrationd.plist DADisableEjectNotification -bool YES && sudo pkill diskarbitrationd
```

**Re-Enable Warning:**

```bash
sudo defaults delete /Library/Preferences/SystemConfiguration/com.apple.DiskArbitration.diskarbitrationd.plist DADisableEjectNotification && sudo pkill diskarbitrationd
```

*Alternatively:* Download [Ejectify](https://ejectify.app).

## Screenshots

### Change Default Format to JPG

Changes the screenshot output format from PNG (default) to JPG.

```bash
defaults write com.apple.screencapture type jpg
```

> **Undo:** Replace `jpg` with `png` at the end of the command.

## Launchpad Layout

Customize the number of columns and rows displayed in the Launchpad. Replace `X` and `Y` with your desired numbers.

**Change Column Count (`X`):**

```bash
defaults write com.apple.dock springboard-columns -int X; killall Dock
```

**Change Row Count (`Y`):**

```bash
defaults write com.apple.dock springboard-rows -int Y; killall Dock
```

**Reset Layout to Default:**

```bash
defaults delete com.apple.dock springboard-rows; defaults delete com.apple.dock springboard-columns; defaults write com.apple.dock ResetLaunchPad -bool TRUE; killall Dock
```

## Miscellaneous

### Screen Saver as Wallpaper

Runs the current screensaver directly as an animated desktop wallpaper.

```bash
/System/Library/Frameworks/ScreenSaver.framework/Resources/ScreenSaverEngine.app/Contents/MacOS/ScreenSaverEngine -background
```

> **Note:** Stop the process in Terminal using `Ctrl + C` to close the screensaver background.