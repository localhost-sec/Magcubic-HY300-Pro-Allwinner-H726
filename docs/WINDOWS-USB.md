# Windows USB Preparation

## 1. Identify the USB drive

Open PowerShell as Administrator:

    Get-Disk | Format-Table Number,FriendlyName,Size,PartitionStyle

Confirm the removable drive by **model and capacity**.

> Never format a disk until you have verified its number.

## 2. Filesystem

Use **FAT32 only when the manufacturer's recovery instructions require it**.

For a normal removable drive, Windows Disk Management is sufficient.

## 3. Verify the firmware

    $path = ".\Magcubic HY300 Pro Allwinner H726.img"
    Get-Item $path | Select-Object Name,Length,LastWriteTime
    Get-FileHash $path -Algorithm SHA256

Record the resulting SHA-256 in docs/FIRMWARE-METADATA.md.

## 4. Copy the vendor package

Copy the manufacturer's files without modification.

Do not:

- Rename files unless instructed
- Mix files from another model or revision
- Edit or repack the image
- Remove companion files supplied by the vendor

## 5. Before powering the projector

Verify:

- Correct firmware
- Correct filename
- Correct USB filesystem
- Correct USB port
- Correct button/power sequence

## 6. After the attempt

Record:

- LED behavior
- Display behavior
- USB behavior
- Whether the projector boots
- Firmware/build shown after recovery

This makes the next recovery attempt reproducible.
