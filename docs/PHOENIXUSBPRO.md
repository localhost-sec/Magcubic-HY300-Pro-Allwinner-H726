# PhoenixUSBPro Recovery

## When to use this

Use PhoenixUSBPro when the Magcubic HY300 Pro / Allwinner H726 does not boot normally and the USB-stick update method cannot be used.

This method uses the Allwinner low-level FEL recovery path. H726 HY300 recovery references describe using the recessed flash button above the HDMI port, a USB-A-to-USB-A cable, and the projector power connection so the flashing utility can detect the device. [H726 recovery reference](https://androidpctv.com/firmware-magcubic-hy300-pro-ultra-h726/) [community recovery procedure](https://github.com/well0nez/magcubic-root/blob/master/README.md)

> [!WARNING]
> This is a low-level firmware operation. It can erase the installed system and can brick the device if the wrong image is used or the connection is interrupted.
>
> **Use only the verified manufacturer update.img from this project's Releases. Do not use update-001.img as a substitute.**

## What you need

- Windows PC
- PhoenixUSBPro
- Allwinner USB driver required by PhoenixUSBPro
- A good USB-A-to-USB-A data cable
- The verified manufacturer firmware: update.img
- Magcubic HY300 Pro H726 projector
- Normal projector power adapter
- Paperclip or suitable non-damaging tool for the recessed flash button

Allwinner documentation describes PhoenixUSBPro/PhoenixSuit as Windows USB burning tools, and factory flashing requires the correct driver and firmware image.

## 1. Install PhoenixUSBPro and the driver

Install PhoenixUSBPro on Windows.

Install the Allwinner USB driver supplied with the projector/vendor package or flashing-tool package.

Open Device Manager before starting so you can watch for a newly detected USB device.

## 2. Prepare the firmware

Download the release asset named:

    update.img

Do not rename or modify it.

Verify the SHA-256 published with the release:

    Get-FileHash ".\update.img" -Algorithm SHA256

Select this exact update.img in PhoenixUSBPro.

## 3. Prepare the projector

1. Disconnect the projector's power adapter.
2. Make sure the projector is completely off.
3. Locate the small recessed flash/reset button above the HDMI port.
4. Connect the USB-A-to-USB-A cable between the projector's USB port and the Windows PC.
5. Keep the flash button held.

The H726 recovery guidance specifically identifies the small button above HDMI as the flash control and uses a USB-A-to-A connection to the PC.

## 4. Start PhoenixUSBPro

1. Run PhoenixUSBPro.exe as Administrator.
2. Select the manufacturer update.img.
3. Start the burn/flash operation so the program is waiting for a device.
4. With the flash button held, connect the projector's normal power supply.
5. Keep the button held briefly while Windows/PhoenixUSBPro detects the device.
6. Release the button after detection.

H726 recovery guidance describes holding the flash button while connecting USB and power until the flashing program detects the projector.

## 5. Confirm FEL detection

The projector may have:

- no picture
- a black screen
- no Android boot animation
- only an LED indication

That does not necessarily mean FEL entry failed.

Check Device Manager for a newly enumerated Allwinner USB device. Exact naming depends on the driver and tool version.

## 6. Flash

Once PhoenixUSBPro recognizes the device:

1. Confirm the selected image is update.img.
2. Start the firmware write if PhoenixUSBPro has not started automatically.
3. Do not disconnect the USB cable.
4. Do not remove projector power.
5. Do not press other buttons.
6. Wait for PhoenixUSBPro to report successful completion.

Allwinner flashing documentation warns against disconnecting the device during firmware loading.

## 7. Finish the recovery

When PhoenixUSBPro reports success:

1. Stop/close the burning operation according to the tool.
2. Disconnect projector power.
3. Disconnect the USB-A-to-A cable.
4. Wait a few seconds.
5. Reconnect the normal power adapter.
6. Boot the projector normally.

The first boot after a full firmware write can take longer than a normal boot.

## If PhoenixUSBPro does not detect the projector

### Cable

Use a genuine USB-A-to-A data cable. A charge-only cable cannot provide the required USB data connection.

### USB port

Try another direct USB port on the PC and avoid hubs while troubleshooting.

### Driver

Check Device Manager for an unknown device or newly appearing Allwinner USB device. Reinstall the vendor Allwinner USB driver if necessary.

### Button timing

Repeat the FEL entry sequence:

- power disconnected
- USB connected to PC
- hold the recessed flash button
- connect projector power
- wait for USB detection
- release after detection

### Power

Use the projector's normal power adapter as required by the recovery procedure. USB power alone is not a substitute unless a documented procedure specifically says otherwise.

### Image

Verify that PhoenixUSBPro is loading:

    update.img

and not an older test image.

## If the projector is completely dead

A dead display does not prove the SoC is dead.

Try FEL detection before concluding that board-level repair is required.

If Windows still sees nothing, collect diagnostics instead of repeatedly flashing:

- exact LED behavior
- Device Manager changes
- USB connection/disconnection sounds
- motherboard/PCB markings
- SoC marking
- storage chip marking
- power-adapter rating

At that point, UART/serial or board-level diagnosis may be more useful than further blind flashing.

## Important distinction

### Normal recovery

    USB drive -> FAT32 -> vendor update procedure -> update.img

### Emergency recovery

    Windows PC
          |
      USB-A-to-A
          |
    HY300 Pro H726
          |
       FEL mode
          |
    PhoenixUSBPro
          |
       update.img

These are different mechanisms. Do not mix the file layout or trigger procedure between them.

## Verified project firmware

Filename: update.img

Source: manufacturer

Target: Magcubic HY300 Pro / Allwinner H726

Status: tested working

See:

- Firmware metadata
- Recovery checklist
- Windows USB preparation
- GitHub Releases
