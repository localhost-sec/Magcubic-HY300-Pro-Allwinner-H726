<div align="center">

# Magcubic HY300 Pro
### Allwinner H726 Recovery & Firmware

**Working manufacturer firmware • Recovery documentation • Hardware research**

[![Firmware](https://img.shields.io/badge/Firmware-update.img-success)](../../releases)
[![Platform](https://img.shields.io/badge/SoC-Allwinner%20H726-blue)](https://github.com/localhost-sec/Magcubic-HY300-Pro-Allwinner-H726)
[![Status](https://img.shields.io/badge/Recovery-Verified-success)](https://github.com/localhost-sec/Magcubic-HY300-Pro-Allwinner-H726)

</div>

---

> [!IMPORTANT]
> **Confirmed working manufacturer firmware:** `update.img`
>
> The `update.img` package was supplied by the manufacturer and has been tested on the target **Magcubic HY300 Pro / Allwinner H726** projector.
>
> Download it from the repository's **Releases** page. Keep the release file unchanged.

## 📡 Device

| Property | Value |
|---|---|
| Model | **Magcubic HY300 Pro** |
| SoC | **Allwinner H726** |
| Firmware | **update.img** |
| Firmware source | **Manufacturer** |
| Firmware status | 🟢 **Working / tested** |
| USB media | FAT32 tested |
| Previous network observation | TCP/10012 open at one point |

## 💾 Firmware download

### Official project release

**Firmware filename:** `update.img`

**Download:** [Latest Release](../../releases/latest)

The release is the preferred distribution point for this project.

### Verify the download

After downloading the release asset, calculate its SHA-256.

**Windows PowerShell**

    Get-FileHash ".\update.img" -Algorithm SHA256

**Linux**

    sha256sum update.img

The resulting hash should be recorded in [Firmware Metadata](docs/FIRMWARE-METADATA.md).

> [!WARNING]
> Do not rename, edit, repack, truncate, or merge `update.img` with firmware files from another HY300/HY300 Pro board revision.

## 🔧 Recovery / update procedure

Use the **manufacturer's intended USB update method** for this image.

### Prepare the USB drive

1. Use a reliable USB flash drive.
2. Back up anything on it.
3. Format it as **FAT32** when required by the manufacturer procedure.
4. Copy the manufacturer file **exactly as supplied**:

       update.img

5. Safely eject the USB drive.

### Start the projector recovery/update

Follow the physical button / power sequence supplied by the manufacturer for your unit.

The exact trigger sequence is hardware/bootloader specific. **Do not substitute a guessed button combination.**

### During the update

If the projector clearly begins a firmware update:

- keep stable power connected;
- do not remove the USB drive;
- do not rename or modify the image;
- do not interrupt the process.

Wait until the manufacturer procedure indicates completion.

## 🧪 What we learned during recovery

The investigation established several useful facts:

- The projector is the **Magcubic HY300 Pro** H726 variant.
- The manufacturer supplied a working firmware image named **`update.img`**.
- USB recovery/update was investigated using FAT32 media.
- An earlier artifact named **`update-001.img`** was examined.
- That earlier artifact was reported as **2,262,962,688 bytes** and contained recognizable strings including `IMAGEWTY` and `sys_config.fex`.
- The earlier `update-001.img` should **not** be treated as the official working firmware.
- A USB A-to-A cable was unavailable during part of the original investigation.
- A phone/Termux recovery path did not provide the working recovery method.
- TCP port **10012** was observed open while the projector was reachable on the network.
- The [HY300-Ultimate](https://github.com/Hen-Dricks/HY300-Ultimate) project was used as a community reference.

## 🧭 Recovery methods

| Method | Status |
|---|---|
| Manufacturer `update.img` | 🟢 **Working / tested** |
| USB / FAT32 update media | 🟢 **Used in recovery process** |
| Android / OTA | ⚪ Not documented |
| Bootloader USB recovery | ⚪ Hardware-specific |
| Allwinner FEL | ⚪ Not required for the verified manufacturer update |
| UART / serial | ⚪ Diagnostic only |

## 📚 Documentation

- [Firmware metadata](docs/FIRMWARE-METADATA.md)
- [Recovery checklist](docs/RECOVERY-CHECKLIST.md)
- [Windows USB preparation](docs/WINDOWS-USB.md)
- [Firmware & copyright notes](LICENSE-NOTES.md)

## 📦 Release contents

The intended release should contain:

    update.img

Recommended release notes:

- Target: **Magcubic HY300 Pro / Allwinner H726**
- Source: **manufacturer**
- Status: **tested working**
- SHA-256: record the hash of the exact release asset

## 🔐 Integrity

Always verify the checksum of the file you are about to place on the recovery USB.

Keep a second untouched copy of the manufacturer's original `update.img`.

## ⚠️ Important distinctions

### Working firmware

`update.img` is the **manufacturer-provided image that has been tested and works on this target device**.

### Older investigation artifact

`update-001.img` is an **earlier investigated image**. Its relationship to the working manufacturer package is not established. Do not use it as a substitute for `update.img`.

### Cross-flashing

Do not use firmware from visually similar HY300/HY300 Pro devices unless the hardware revision is confirmed identical.

---

<div align="center">

**Magcubic HY300 Pro • Allwinner H726**

**Firmware: `update.img` • Status: 🟢 Working**

</div>
