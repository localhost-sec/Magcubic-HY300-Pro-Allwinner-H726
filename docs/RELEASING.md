# Firmware Release Procedure

## Canonical firmware

The verified manufacturer firmware for this project is:

`update.img`

The GitHub **Releases** page is the canonical public download location.

## Release checklist

1. Obtain the original manufacturer `update.img`.
2. Keep an untouched backup.
3. Calculate its SHA-256.
4. Confirm the file size.
5. Upload the unmodified file as a Release asset named `update.img`.
6. Add the target information to the release notes.
7. Put the SHA-256 in the release notes and `docs/FIRMWARE-METADATA.md`.
8. Never replace the binary with a modified or repacked image.

## Release notes template

    Magcubic HY300 Pro - Allwinner H726

    Firmware: update.img
    Source: Manufacturer
    Status: Tested working
    SHA-256: <hash>
    File size: <bytes>

## Download

Users should download `update.img` from the latest GitHub Release and verify the SHA-256 before copying it to recovery media.

## Important

The older `update-001.img` discussed during the investigation is not the verified release firmware. The release artifact is `update.img`.
