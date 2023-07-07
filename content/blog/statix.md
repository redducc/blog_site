---
title: "StatixOS Lisa"
dateString: July 2023
draft: false
tags: ["Installation", "lisa",]
weight: 999999
---

# Basic requirements

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!

2. Make sure your computer has adb and fastboot.

3. Enable USB debugging on your device.

4. ROM is provided as-is with no warranty. While we attempt to verify everything works you are installing this at your own risk!

5. Both fastboot package and recovery rom is provided, flashing via fastboot package is preferred.

# Installing StatixOS using fastboot package

- Download statix_lisa-20230707-13-v6.3-UNOFFICIAL-img.zip
- Boot into fastboot using: **adb reboot bootlaoder**
- Erase your data by: **fastboot -w**
- Type the following command to flash the ROM:
    **fastboot update statix_lisa-20230707-13-v6.3-UNOFFICIAL-img.zip**

# Installing using recovery

- Download the StatixOS boot and vendor_boot images.
- If your device isn’t already in fastboot mode, on the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type: **adb reboot bootloader** You can also boot into fastboot>- Flash boot image:
    **fastboot flash boot boot.img**
- Flash vendorboot image:
    **fastboot flash vendor_boot vendor_boot.img**

# Installing from recovery

1. Boot into recovery using:
    **fastboot reboot recovery**
2. Select Wipe Data/factory reset and confirm.
3. Go back and select Apply update from ADB.
4. Type the following command in your terminal:
    **adb sideload statix_lisa-20230707-13-v6.3-UNOFFICIAL.zip**
5. adb sideload firmware*.zip (only if there's a firmware update).
6. After installation complete, Reboot to system.

# That's all folks
After you’ve double checked that you followed the steps precisely, didn’t skip any and still have questions or got stuck, feel free to ask on our [`Telegram group`](https://t.me/StatixOSLisa).
