# Firmware Metadata

## Manufacturer firmware — VERIFIED

| Field | Value |
|---|---|
| Product | **Magcubic HY300 Pro** |
| Platform | **Allwinner H726** |
| Firmware filename | **update.img** |
| Source | **Manufacturer** |
| Compatibility | **Verified on target projector** |
| Working status | **Confirmed / tested** |
| Firmware version | **TBD** |
| Hardware revision | **TBD** |
| File size | **TBD** |
| SHA-256 | **TBD** |
| Release | [GitHub Releases](../../releases) |

## Integrity

Calculate the hash from the exact release asset.

### Windows PowerShell

    Get-FileHash ".\update.img" -Algorithm SHA256

### Linux

    sha256sum update.img

Do not invent or estimate a hash.

## Previous investigation artifact

| Field | Value |
|---|---|
| Filename | `update-001.img` |
| Reported size | **2,262,962,688 bytes** |
| Observed strings | `IMAGEWTY`, `sys_config.fex` |
| SHA-256 | Not recorded |
| Status | **Not the verified release firmware** |

> **Important:** The working manufacturer firmware is **`update.img`**. The older `update-001.img` artifact should not be used as a substitute.

## Release requirements

The firmware release should contain exactly the manufacturer's original `update.img` without modification or repackaging.

Release metadata should include:

    Target: Magcubic HY300 Pro
    SoC: Allwinner H726
    File: update.img
    Source: Manufacturer
    Status: Tested working
    SHA-256: <calculated from release asset>
