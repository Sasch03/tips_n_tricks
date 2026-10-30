# macOS Startup Shortcuts & Troubleshooting Guide

Essential key combinations to diagnose, repair, and recover Macs (MacBooks, iMacs, Mac minis) across all generations.

---

## Key Mapping Reference (Windows vs. Mac)

When using a standard Windows keyboard on a Mac:

| Mac Key | Windows Equivalent |
| :--- | :--- |
| **Command ($\mathbf{\text{Cmd}} / \mathbf{\mathcal{cmd}}$)** | **Windows Key ($\mathbf{\text{Win}}$)** |
| **Option ($\mathbf{\text{Opt}}$ / Alt)** | **Alt Key** |
| **Control ($\mathbf{\text{Ctrl}}$)** | **Ctrl Key** |
| **Shift** | **Shift** |

---

## Apple Silicon Macs (M1 / M2 / M3 / M4)

For modern Macs with Apple Silicon:

1. Shut down the Mac completely.
2. Press and **hold the Power button** until you see **"Loading startup options..."**.
3. Select **Options** to access Recovery, or choose a boot drive.

---

## Intel-Based Macs (Older Models & Legacy)

For Intel Macs, press and hold the key combination **immediately after pressing the Power button** (or after hearing the startup chime).

### 1. Recovery & OS Reinstallation

| Purpose | Mac Keyboard | Windows Keyboard |
| :--- | :--- | :--- |
| **Built-in Recovery** *(Local partition)* | $\text{Cmd} + \text{R}$ | $\text{Win} + \text{R}$ |
| **Internet Recovery** *(Latest compatible OS)* | $\text{Option} + \text{Cmd} + \text{R}$ | $\text{Alt} + \text{Win} + \text{R}$ |
| **Internet Recovery** *(Original factory OS)* | $\text{Shift} + \text{Option} + \text{Cmd} + \text{R}$ | $\text{Shift} + \text{Alt} + \text{Win} + \text{R}$ |

### 2. Boot & Hardware Troubleshooting

| Action / Mode | Description | Mac Keyboard | Windows Keyboard |
| :--- | :--- | :--- | :--- |
| **Startup Manager** | Choose boot drive / USB stick | Hold $\text{Option}$ | Hold $\text{Alt}$ |
| **Apple Diagnostics / AHT** | Hardware test utility | Hold $\text{D}$ (or $\text{Option} + \text{D}$) | Hold $\text{D}$ (or $\text{Alt} + \text{D}$) |
| **Reset NVRAM / PRAM** | Fixes resolution, boot, & sound issues | $\text{Cmd} + \text{Option} + \text{P} + \text{R}$ | $\text{Win} + \text{Alt} + \text{P} + \text{R}$ |
| **Safe Mode** | Disables non-essential extensions | Hold $\text{Shift}$ | Hold $\text{Shift}$ |
| **Verbose Mode** | Displays text boot logs for debugging | $\text{Cmd} + \text{V}$ | $\text{Win} + \text{V}$ |
| **Single-User Mode** | Command-line root environment | $\text{Cmd} + \text{S}$ | $\text{Win} + \text{S}$ |
| **Target Disk Mode** | Mount Mac as external drive | Hold $\text{T}$ | Hold $\text{T}$ |
| **Force Eject Media** | Eject CD/DVD on optical drives | Hold $\text{Mouse Click}$ or $\text{Eject}$ | Hold $\text{Mouse Click}$ |

---

## Resetting the SMC (System Management Controller)

Fixes power, battery, fan noise, and display/lid issues on Intel Macs.

* **MacBooks with Non-Removable Battery:** Press $\text{Shift} + \text{Control} + \text{Option}$ (left side) $+$ $\text{Power}$ for 10 seconds, then release and power on.
* **MacBooks with Removable Battery:** Remove battery, hold $\text{Power}$ for 5 seconds, reinsert battery, and power on.
* **Desktop Macs (iMac / Mac mini / Mac Pro):** Unplug power cord for 15 seconds, plug back in, wait 5 seconds, then power on.