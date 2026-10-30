# Arch Linux System Maintenance & Hygiene Guide

A practical guide to keeping an Arch Linux system clean, stable, and up to date. Unlike point-release distributions, Arch Linux requires active maintenance to ensure smooth rolling updates and avoid system breakage.

> **Note:** Always check [Arch Linux News](https://archlinux.org/news/) before running major updates to stay informed about required manual interventions.  
> *Source:* [ArchWiki - System Maintenance: Upgrading the system](https://wiki.archlinux.org/title/System_maintenance#Upgrading_the_system)

---

## Table of Contents

* [1. System Upgrades](#1-system-upgrades)
* [2. Cleaning Package Cache](#2-cleaning-package-cache)
* [3. Managing Orphaned Packages](#3-managing-orphaned-packages)
* [4. Managing Configuration (.pacnew / .pacsave) Files](#4-managing-configuration-pacnew--pacsave-files)
* [5. Checking System Health & Failed Services](#5-checking-system-health--failed-services)
* [6. Systemd Journal Maintenance](#6-systemd-journal-maintenance)
* [7. References & Sources](#7-references--sources)

---

## 1. System Upgrades

### Full System Upgrade
Always perform full system updates. Never run `pacman -Sy` alone to install packages, as partial upgrades are unsupported and can break dependencies.

```bash
sudo pacman -Syu
```
*Source:* [ArchWiki - Pacman: Upgrading packages](https://wiki.archlinux.org/title/Pacman#Upgrading_packages)

### Updating Mirror List
Update package mirrors periodically to ensure fast download speeds and synced repositories.

```bash
sudo reflector --protocol https --latest 20 --sort rate --save /etc/pacman.d/mirrorlist
```
*Source:* [ArchWiki - Reflector](https://wiki.archlinux.org/title/Reflector)

---

## 2. Cleaning Package Cache

Pacman does not automatically remove old downloaded package versions from `/var/cache/pacman/pkg/`. Over time, this directory can grow significantly.

### Trimming Cache with `paccache`
The `paccache` script (part of the `pacman-contrib` package) safely removes cached packages while retaining the most recent versions as fallbacks for downgrades.

**Keep the last 2 versions of installed packages:**
```bash
sudo paccache -rk2
```
*Source:* [ArchWiki - Pacman: Cleaning the package cache](https://wiki.archlinux.org/title/Pacman#Cleaning_the_package_cache)

**Remove all cached versions of uninstalled packages:**
```bash
sudo paccache -ruk0
```
*Source:* [ArchWiki - Pacman: Cleaning the package cache](https://wiki.archlinux.org/title/Pacman#Cleaning_the_package_cache)

**Automate cache cleaning with systemd timer:**
```bash
sudo systemctl enable --now paccache.timer
```
*Source:* [ArchWiki - Pacman: Cleaning the package cache](https://wiki.archlinux.org/title/Pacman#Cleaning_the_package_cache)

---

## 3. Managing Orphaned Packages

Orphans are packages that were installed as dependencies for another program but are no longer required by any installed package.

### Find Orphaned Packages
```bash
pacman -Qdt
```
*Source:* [ArchWiki - Pacman/Tips and tricks: Removing unused packages (orphans)](https://wiki.archlinux.org/title/Pacman/Tips_and_tricks#Removing_unused_packages_(orphans))

### Remove Orphaned Packages Safely
```bash
sudo pacman -Rns $(pacman -Qdtq)
```
*Source:* [ArchWiki - Pacman/Tips and tricks: Removing unused packages (orphans)](https://wiki.archlinux.org/title/Pacman/Tips_and_tricks#Removing_unused_packages_(orphans))

> **Note:** If no orphans are found, `pacman -Qdtq` outputs nothing, causing `pacman -Rns` to throw an error (`error: no targets specified`). This is expected behavior.

---

## 4. Managing Configuration (.pacnew / .pacsave) Files

When a package update includes a new default configuration file and you modified the existing one, Pacman creates a `.pacnew` file instead of overwriting your changes.

### Find all `.pacnew` files
```bash
pacman -Qii | grep "pacnew"
```
*or using `find`:*
```bash
sudo find /etc -name "*.pacnew"
```
*Source:* [ArchWiki - Pacnew and Pacsave files](https://wiki.archlinux.org/title/Pacnew_and_Pacsave_files)

### Interactively Review and Merge Files
Use `pacdiff` (from `pacman-contrib`) to compare and merge configuration files side by side:

```bash
sudo DIFFPROG=meld pacdiff
```
*Source:* [ArchWiki - Pacnew and Pacsave files: Managing .pacnew files](https://wiki.archlinux.org/title/Pacnew_and_Pacsave_files#Managing_.pacnew_files)

---

## 5. Checking System Health & Failed Services

### Check for Failed Systemd Services
```bash
systemctl --failed
```
*Source:* [ArchWiki - System Maintenance: Check for errors](https://wiki.archlinux.org/title/System_maintenance#Check_for_errors)

### Check Failed User Services
```bash
systemctl --user --failed
```
*Source:* [ArchWiki - System Maintenance: Check for errors](https://wiki.archlinux.org/title/System_maintenance#Check_for_errors)

### Check High-Priority Journal Errors
```bash
journalctl -p 3 -xb
```
*Source:* [ArchWiki - Systemd/Journal: Filtering output](https://wiki.archlinux.org/title/Systemd/Journal#Filtering_output)

---

## 6. Systemd Journal Maintenance

Systemd logs can grow large over time if unrestricted.

### Check Journal Disk Usage
```bash
journalctl --disk-usage
```
*Source:* [ArchWiki - Systemd/Journal: Journal size limit](https://wiki.archlinux.org/title/Systemd/Journal#Journal_size_limit)

### Trim Logs Older Than 2 Weeks
```bash
sudo journalctl --vacuum-time=2weeks
```
*Source:* [ArchWiki - Systemd/Journal: Clean log files](https://wiki.archlinux.org/title/Systemd/Journal#Clean_log_files)

### Limit Max Journal Size to 500M
```bash
sudo journalctl --vacuum-size=500M
```
*Source:* [ArchWiki - Systemd/Journal: Clean log files](https://wiki.archlinux.org/title/Systemd/Journal#Clean_log_files)

---

## 7. References & Sources

1. **ArchWiki - System Maintenance:** [https://wiki.archlinux.org/title/System_maintenance](https://wiki.archlinux.org/title/System_maintenance)
2. **ArchWiki - Pacman:** [https://wiki.archlinux.org/title/Pacman](https://wiki.archlinux.org/title/Pacman)
3. **ArchWiki - Pacman/Tips and Tricks:** [https://wiki.archlinux.org/title/Pacman/Tips_and_tricks](https://wiki.archlinux.org/title/Pacman/Tips_and_tricks)
4. **ArchWiki - Pacnew and Pacsave files:** [https://wiki.archlinux.org/title/Pacnew_and_Pacsave_files](https://wiki.archlinux.org/title/Pacnew_and_Pacsave_files)
5. **ArchWiki - Systemd/Journal:** [https://wiki.archlinux.org/title/Systemd/Journal](https://wiki.archlinux.org/title/Systemd/Journal)
6. **ArchWiki - Reflector:** [https://wiki.archlinux.org/title/Reflector](https://wiki.archlinux.org/title/Reflector)