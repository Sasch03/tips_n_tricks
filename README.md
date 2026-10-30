# Personal Wiki & Tech Cheatsheets

A personal collection of practical commands, configurations, custom UI pages, and quick guides for system administration, hardware troubleshooting, Linux maintenance, and media processing.

---

## Repository Structure

```text
.
├── .gitattributes
├── README.md
├── yt_dlp_cheat_sheet.md
├── bios_keys/
│   ├── bios_keys_acer.md
│   ├── bios_keys_asus.md
│   ├── bios_keys_dell.md
│   ├── bios_keys_hp.md
│   └── bios_keys_lenovo.md
├── linux/
│   ├── arch/
│   │   ├── arch_linux_apps_and_packages_recommendations.md
│   │   ├── arch_linux_firewall_activation_guide.md
│   │   ├── arch_linux_firmware_updates_guide.md
│   │   ├── arch_linux_installation_guide.md
│   │   ├── arch_linux_maintenance_guide.md
│   │   ├── arch_linux_multilib_activation_guide.md
│   │   └── arch_linux_yay_installation_guide.md
│   └── kde/
│       ├── Import_SysMon-Pages.md
│       ├── kde_systemmonitor_cpu-page.page
│       ├── kde_systemmonitor_disk-page.page
│       └── kde_systemmonitor_temperature-page.page
└── mac/
    ├── macos_startup_shortcuts.md
    ├── macos_terminal_tweaks.md
    └── macos_usb_bootstick.md
```

---

## Contents Overview

### Hardware & BIOS Guides (`/bios_keys`)
* **[Acer BIOS Keys](bios_keys/bios_keys_acer.md):** Access setup, boot menu, and enable F12 options on Acer systems.
* **[ASUS BIOS Keys](bios_keys/bios_keys_asus.md):** BIOS/UEFI setup and boot menu shortcuts for laptops, ROG/TUF gaming, and motherboards.
* **[Dell BIOS Keys](bios_keys/bios_keys_dell.md):** Direct shortcuts for F2 (Setup) and F12 (Boot Menu) on Dell Latitude, XPS, and OptiPlex lines.
* **[HP BIOS Keys](bios_keys/bios_keys_hp.md):** Startup Menu (Esc), BIOS (F10), Boot Menu (F9), and System Diagnostics (F2) for HP/Compaq.
* **[Lenovo BIOS Keys](bios_keys/bios_keys_lenovo.md):** ThinkPad shortcuts (F1/F12), NOVO button instructions, and Lenovo desktop keys.

### Linux (`/linux`)

#### Arch Linux (`/linux/arch`)
* **[Apps & Package Recommendations](linux/arch/arch_linux_apps_and_packages_recommendations.md):** Curated software list for desktop setups.
* **[Firewall Activation Guide](linux/arch/arch_linux_firewall_activation_guide.md):** Setting up and enabling UFW / nftables.
* **[Firmware Updates Guide](linux/arch/arch_linux_firmware_updates_guide.md):** Managing hardware firmware updates via `fwupd`.
* **[Installation Guide](linux/arch/arch_linux_installation_guide.md):** Step-by-step Arch Linux installation instructions.
* **[Maintenance Guide](linux/arch/arch_linux_maintenance_guide.md):** Package upgrades, cache trimming, orphan removal, and `pacnew` management.
* **[Multilib Activation Guide](linux/arch/arch_linux_multilib_activation_guide.md):** Enabling 32-bit software support (Steam, Wine).
* **[yay Installation Guide](linux/arch/arch_linux_yay_installation_guide.md):** Building and configuring the `yay` AUR helper.

#### KDE Desktop (`/linux/kde`)
* **[KDE System Monitor Custom Pages](linux/kde/Import_SysMon-Pages.md):** Guide and pre-configured `.page` templates for monitoring CPU, disk I/O, and hardware temperatures.

### macOS Utilities (`/mac`)
* **[macOS Startup Shortcuts](mac/macos_startup_shortcuts.md):** Recovery, boot loader, and reset key combinations for Intel & Apple Silicon Macs (Mac vs. Windows layouts).
* **[macOS Terminal Tweaks](mac/macos_terminal_tweaks.md):** Dock animations, hidden spacers, transparent hidden apps, and screenshot formats.
* **[macOS USB Bootstick Guide](mac/macos_usb_bootstick.md):** Complete `createinstallmedia` command matrix for macOS Sequoia down to OS X Mavericks.

### Media & Automation
* **[YouTube Music MP3 Exporter Cheatsheet](yt_dlp_cheat_sheet.md):** High-quality audio extraction using `yt-dlp` with ID3v2.3 tags and embedded thumbnails.

---

## How to Extend

1. Add your guide or config file to the appropriate folder (`bios_keys/`, `linux/arch/`, `linux/kde/`, `mac/`, etc.).
2. Update the **Repository Structure** and **Contents Overview** in this `README.md`.