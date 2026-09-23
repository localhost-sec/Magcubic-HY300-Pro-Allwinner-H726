<div align="center">

# Magcubic HY300 Pro
### Allwinner H726 Recovery & Firmware

**Working manufacturer firmware • Recovery documentation • Hardware research**

[![Firmware](https://img.shields.io/badge/Firmware-update.img-success)](../../releases)
[![Platform](https://img.shields.io/badge/SoC-Allwinner%20H726-blue)](https://github.com/localhost-sec/Magcubic-HY300-Pro-Allwinner-H726)
[![Recovery](https://img.shields.io/badge/Recovery-PhoenixUSBPro-orange)](docs/PHOENIXUSBPRO.md)

</div>

---

> [!IMPORTANT]
> **Confirmed working manufacturer firmware:** update.img
>
> The manufacturer-supplied update.img has been tested successfully on the target **Magcubic HY300 Pro / Allwinner H726** projector.
>
> Download it from **Releases**.

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

## 💾 Firmware

### Download

**[Latest firmware release](../../releases/latest)**

Release asset:

    update.img

Verify the downloaded image:

### Windows

    Get-FileHash ".\update.img" -Algorithm SHA256

### Linux

    sha256sum update.img

The published hash must match the exact release asset.

**SHA-256:** `7D3AD14E7E89EAF316348C214F24F304075465DB5C5FC00AE911086927ACE7FD`

## 🔧 Recovery options

### A. Normal USB recovery

Use the manufacturer's USB update procedure with update.img.

See [Windows USB preparation](docs/WINDOWS-USB.md) and [Recovery Checklist](docs/RECOVERY-CHECKLIST.md).

### B. Projector will not boot — PhoenixUSBPro / FEL

Use the dedicated [PhoenixUSBPro emergency recovery guide](docs/PHOENIXUSBPRO.md).

This path is for a projector that cannot boot normally and uses a direct USB connection to a Windows PC.

**You need:**

- PhoenixUSBPro
- Allwinner USB driver
- USB-A-to-USB-A data cable
- normal projector power adapter
- recessed flash button above the HDMI port
- manufacturer update.img


## 📚 Documentation

- [PhoenixUSBPro Emergency Recovery](docs/PHOENIXUSBPRO.md)
- [Firmware Metadata](docs/FIRMWARE-METADATA.md)
- [Recovery Checklist](docs/RECOVERY-CHECKLIST.md)
- [Windows USB Preparation](docs/WINDOWS-USB.md)
- [Firmware & Copyright Notes](LICENSE-NOTES.md)
- [Release procedure](docs/RELEASING.md)

## 📦 Release format

The official release asset should be:

    update.img

Release notes should contain:

    Target: Magcubic HY300 Pro / Allwinner H726
    Firmware: update.img
    Source: Manufacturer
    Status: Tested working
    SHA-256: <hash>
    File size: <bytes>

## 🔐 Firmware integrity

Always calculate the hash from the exact file you intend to flash.

Keep an untouched backup of the manufacturer's original image.

Do not modify, repack, rename, or merge the image with files from another firmware package.

---

<div align="center">

**Magcubic HY300 Pro • Allwinner H726**

**Firmware: update.img • Status: 🟢 Working**

</div>

---

## 🤖 About this README

> **This repository and its documentation were generated with ChatGPT because I was too lazy to write it all myself. 😎**
>
> Please **always double-check the instructions, firmware files, hashes, and recovery procedure before flashing anything**. Hardware revisions and firmware packages can differ, and mistakes can brick the projector.

<div align="center">

*AI-assisted documentation • Human verification required*

</div>
