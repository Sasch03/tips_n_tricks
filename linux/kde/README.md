# KDE System Monitor - Custom Pages & Import Guide

This directory contains pre-configured custom pages for the **KDE System Monitor** (`plasma-systemmonitor`). These pages provide dedicated views for monitoring hardware performance and thermals on KDE Plasma environments.

---

## Included Custom Pages

* **`kde_systemmonitor_cpu-page.page`**
  * Tracks individual CPU core frequencies, usage percentages, load averages, and active process distribution.
* **`kde_systemmonitor_disk-page.page`**
  * Displays real-time read/write throughput, I/O operations, disk space usage across partitions, and drive activity.
* **`kde_systemmonitor_temperature-page.page`**
  * Dedicated thermal monitoring for CPU packages, GPU junction/edge temperatures, NVMe drives, and fan speeds.

---

## How to Import Pages into KDE System Monitor

1. Open **KDE System Monitor** from your application menu or terminal (`plasma-systemmonitor`).
2. In the bottom-left corner of the window, click on **"Tools"** or **"Edit Pages"** (or click the **`+`** icon to add a page).
3. Click the **"Import Page..."** button (or hamburger menu -> Import).
4. Navigate to `linux/kde/` within this repository and select the `.page` file you want to import.
5. Click **Open**. The new page will appear in your left sidebar navigation.

---

## Manual Installation Path (Alternative)

If you prefer installing pages directly via the file system:

Copy the `.page` files directly to your user configuration folder:

```bash
cp *.page ~/.local/share/ksysguard/
# or on newer Plasma 6 setups:
cp *.page ~/.local/share/plasma-systemmonitor/
```

Restart KDE System Monitor to load the newly imported pages.