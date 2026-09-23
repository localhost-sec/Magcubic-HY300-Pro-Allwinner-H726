# HY300 Pro H726 Recovery Checklist

## Before flashing

- [ ] Confirm exact H726 hardware variant
- [ ] Photograph projector label
- [ ] Photograph motherboard markings
- [ ] Record board revision
- [ ] Record SoC and storage markings
- [ ] Obtain firmware directly from manufacturer/vendor
- [ ] Calculate SHA-256
- [ ] Preserve original image unchanged
- [ ] Confirm vendor filename
- [ ] Confirm filesystem requirement
- [ ] Confirm button/power sequence

## USB

- [ ] Identify removable disk
- [ ] Confirm it is not the system disk
- [ ] Format FAT32 only when required
- [ ] Copy only vendor files
- [ ] Safely eject USB

## Flash

- [ ] Follow documented trigger sequence
- [ ] Watch LED/display changes
- [ ] Do not interrupt a confirmed write
- [ ] Record result

## Failure

Stop blind image/filename combinations. Collect LED behavior, USB enumeration logs, UART output if available, motherboard photos, firmware SHA-256, vendor instructions, and error messages.