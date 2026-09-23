<div align="center">

# Magcubic HY300 Pro
### Allwinner H726 Recovery & Firmware Documentation

Hardware research • Firmware verification • Recovery notes

<a href="https://github.com/localhost-sec/Magcubic-HY300-Pro-Allwinner-H726">Repository</a> ·
<a href="https://github.com/Hen-Dricks/HY300-Ultimate">Community Reference</a>

</div>

---

> [!WARNING]
> **Firmware flashing can permanently brick the projector.**
> Use firmware intended for the exact hardware revision. Never mix HY300 variants, rename files without vendor instructions, or interrupt a confirmed flash.

## Project status

| Item | Status |
|---|---|
| Device | **Magcubic HY300 Pro** |
| SoC / platform | **Allwinner H726** |
| Recovery state | 🔴 Previously unresponsive after USB recovery attempt |
| Manufacturer firmware | 🟡 Obtained, not independently verified |
| Known-good image hash | ⬜ Not recorded |
| Known-good flashing procedure | ⬜ Not established |
| USB filesystem tested | **FAT32** |
| Network observation | **TCP/10012 open** at one point |

This repository keeps **verified facts**, **observations**, and **experiments** clearly separated.

## Hardware identity

### Known

- Product: **Magcubic HY300 Pro**
- Platform: **Allwinner H726**
- Manufacturer image name seen: **Magcubic HY300 Pro Allwinner H726.img**
- Other image examined: **update-001.img**
- Reported update-001.img size: **2,262,962,688 bytes**

### Still to document

- PCB / motherboard revision
- Exact SoC marking
- Storage IC
- RAM markings
- Factory firmware/build number
- Power-adapter rating
- USB port labels and behavior

Before another blind recovery attempt, photograph the board and record all markings.

## Firmware

### Manufacturer image

Preserve the manufacturer's original image **byte-for-byte**.

Record:

    Filename:
    Firmware version:
    Hardware revision:
    File size:
    SHA-256:
    Source:
    Date received:
    Manufacturer instructions:
    Redistribution permission:

### Verify on Windows

    $path = ".\Magcubic HY300 Pro Allwinner H726.img"
    Get-Item $path | Select-Object Name,Length,LastWriteTime
    Get-FileHash $path -Algorithm SHA256

Do not publish or flash a modified copy as the manufacturer image.

## Image investigation

The previously inspected update-001.img was reported to contain recognizable strings / structures including:

- IMAGEWTY
- sys_config.fex

These findings are useful for analysis, but **do not prove compatibility** and do not identify the correct flashing mechanism.

> **Observed ≠ verified**

## Recovery history

1. Manufacturer firmware was obtained.
2. USB flash media was prepared.
3. FAT32 was tested for USB recovery.
4. A USB firmware recovery attempt was made.
5. The attempt did not restore normal operation.
6. The projector was subsequently treated as bricked / unresponsive.
7. A USB A-to-A cable was unavailable during part of the investigation.
8. A phone / Termux recovery path was considered/tested but did not provide a working recovery.
9. Network investigation was performed while the projector was reachable; TCP port 10012 was observed open at one point.
10. The HY300-Ultimate project was used as a community reference.

## Recovery methods

| Method | Purpose | Current state |
|---|---|---|
| Android / OTA | Normal update | Not verified |
| Vendor USB updater | Factory/user recovery | Tested, unsuccessful |
| Bootloader USB | Boot-time recovery | Not verified |
| Allwinner FEL | Low-level recovery | Not verified |
| UART / serial | Boot diagnostics | Not verified |

An IMG image alone does **not** tell us which mechanism the manufacturer intended.

Do not assume that copying an image to USB, renaming it, or using another HY300 image is sufficient.

## Recommended workflow

### 1. Identify the exact board

Photograph and record:

- projector label
- motherboard
- PCB revision
- SoC marking
- storage chip
- RAM markings
- USB ports
- power section

### 2. Verify the manufacturer image

Calculate SHA-256 and preserve an untouched master copy.

### 3. Follow the vendor package exactly

Use the supplied filename, directory structure, filesystem requirements, and recovery trigger sequence.

### 4. Do not interrupt a confirmed flash

Do not remove power or USB media while a genuine update is in progress.

### 5. If USB recovery fails

Stop repeating random image and filename combinations.

Move to diagnostics:

- USB enumeration
- UART output
- board identification
- storage identification
- Allwinner FEL detection
- backup before further writes

## Windows USB preparation

Identify the removable disk first:

    Get-Disk | Format-Table Number,FriendlyName,Size,PartitionStyle

Verify the disk by **model and capacity** before formatting.

Use FAT32 only when the vendor procedure requires FAT32.

Verify the firmware:

    Get-FileHash ".\Magcubic HY300 Pro Allwinner H726.img" -Algorithm SHA256

Keep an untouched master copy.

## Repository layout

    .
    ├── README.md
    ├── LICENSE-NOTES.md
    └── docs
        ├── FIRMWARE-METADATA.md
        ├── RECOVERY-CHECKLIST.md
        └── WINDOWS-USB.md

## Research philosophy

This project intentionally separates:

- **Verified facts**
- **Observed behavior**
- **Unverified hypotheses**
- **Experimental recovery methods**

That prevents an experimental procedure from accidentally becoming a "known-good" flashing guide.

## References

- Community reference: https://github.com/Hen-Dricks/HY300-Ultimate
- Project repository: https://github.com/localhost-sec/Magcubic-HY300-Pro-Allwinner-H726

## Firmware redistribution

Only publish manufacturer firmware when redistribution is permitted. Otherwise publish metadata, hashes, documentation, and the official/vendor source.

---

<div align="center">

**Recovery status: 🔴 UNRESOLVED**

Document first. Verify second. Flash last.

</div>
