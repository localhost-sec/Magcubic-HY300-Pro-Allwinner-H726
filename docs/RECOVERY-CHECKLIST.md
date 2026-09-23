# Recovery Checklist

> Goal: one reproducible, verified recovery procedure — not a collection of guesses.

## Before flashing

- [ ] Confirm **HY300 Pro + H726** hardware
- [ ] Photograph projector label
- [ ] Photograph motherboard
- [ ] Record PCB revision
- [ ] Record SoC marking
- [ ] Record storage IC
- [ ] Record RAM markings
- [ ] Record firmware/build if the device boots
- [ ] Obtain firmware directly from manufacturer/vendor
- [ ] Calculate SHA-256
- [ ] Preserve an untouched master copy
- [ ] Confirm vendor filename
- [ ] Confirm vendor filesystem requirement
- [ ] Confirm vendor button/power sequence

## USB preparation

- [ ] Identify the removable disk
- [ ] Confirm it is not the Windows system disk
- [ ] Format FAT32 only if required
- [ ] Copy only the required vendor files
- [ ] Preserve the original filename
- [ ] Safely eject the USB

## Recovery attempt

- [ ] Follow the documented vendor trigger sequence
- [ ] Watch LED/display behavior
- [ ] Record USB behavior
- [ ] Do not interrupt a confirmed write
- [ ] Record the exact result

## Failure path

Stop trying random firmware or filename combinations.

Collect:

- LED behavior
- USB enumeration logs
- UART/serial output if accessible
- PCB markings
- storage identification
- firmware filename
- SHA-256
- vendor instructions
- error messages

Then choose the next diagnostic path based on evidence.
