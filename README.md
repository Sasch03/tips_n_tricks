# Personal Wiki & Tech Cheatsheets

A personal collection of practical commands, configurations, and quick guides for system customization, hardware troubleshooting, media processing, and system administration.

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
├── linux_arch/
│   └── arch_linux_maintenance_guide.md
└── mac/
    ├── macos_startup_shortcuts.md
    ├── macos_terminal_tweaks.md
    └── macos_usb_bootstick.md
```

---

## Contents Overview

### Hardware & BIOS Guides (`/bios_keys`)
* **[Acer BIOS Keys](bios_keys/bios_keys_acer.md):** BIOS/UEFI setup, boot menu keys, and enabling F12 menu for Acer laptops and desktops.
* **[ASUS BIOS Keys](bios_keys/bios_keys_asus.md):** BIOS/UEFI setup and boot menu shortcuts for ASUS laptops, ROG, TUF, and custom motherboards.
* **[Dell BIOS Keys](bios_keys/bios_keys_dell.md):** Accessing setup (F2) and boot menu (F12) on Dell Latitude, XPS, Inspiron, and OptiPlex systems.
* **[HP BIOS Keys](bios_keys/bios_keys_hp.md):** Key combinations for Startup Menu (Esc), BIOS (F10), Boot Menu (F9), and Diagnostics (F2) on HP/Compaq systems.
* **[Lenovo BIOS Keys](bios_keys/bios_keys_lenovo.md):** Instructions for ThinkPad (F1/F12), IdeaPad (NOVO button/F2), and Lenovo desktops.

### Arch Linux (`/linux_arch`)
* **[Arch Linux Maintenance Guide](linux_arch/arch_linux_maintenance_guide.md):** Step-by-step guide for system upgrades, package cache cleaning, orphan removal, pacnew configuration merging, and systemd journal maintenance (with official ArchWiki citations).

### macOS Utilities (`/mac`)
* **[macOS Startup Shortcuts](mac/macos_startup_shortcuts.md):** Essential key combinations for troubleshooting Intel and Apple Silicon Macs, featuring side-by-side Mac and Windows keyboard layouts.
* **[macOS Terminal Tweaks](mac/macos_terminal_tweaks.md):** Customize system defaults, speed up Dock animations, add spacers, adjust Launchpad grid sizes, and change screenshot formats.
* **[macOS USB Bootstick Guide](mac/macos_usb_bootstick.md):** Complete reference of `createinstallmedia` commands to build bootable USB installers (macOS Sequoia down to OS X Mavericks).

### Media & Automation
* **[YouTube Music MP3 Exporter Cheatsheet](yt_dlp_cheat_sheet.md):** Optimized `yt-dlp` commands and shell aliases for Arch Linux to download high-quality MP3s with ID3v2.3 metadata and embedded PNG thumbnails.

---

## How to Extend

To add new cheat sheets or guides to this repository:

1. Create a new `.md` file in the root directory or inside the appropriate subfolder (`bios_keys/`, `linux_arch/`, `mac/`, etc.).
2. Add a brief description and link to the new file in the **Contents Overview** section of this `README.md`.