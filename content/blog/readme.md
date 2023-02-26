---
title: "Installation Guide For Xiaomi 11 Lite Ne 5G"
dateString: Feb 2023
draft: false
tags: ["Installation", "lisa",]
weight: 999999
---

# Basic requirements

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!

2. Make sure your computer has adb and fastboot. Setup instructions can be found here.

3. Enable USB debugging on your device.

4. ROM is provided as-is with no warranty. While we attempt to verify everything works you are installing this at your own risk!

# Installing recovery using fastboot

- Download the Project Awaken boot and vendor_boot images.
- If your device isn’t already in fastboot mode, on the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type: **adb reboot bootloader** You can also boot into fastboot mode via a key combination: With the device powered off, hold Volume Down + Power. Keep holding both buttons until the word “FASTBOOT” appears on the screen, then release.
- Flash boot image:
    **fastboot flash boot boot.img**

# Installing Project Awaken

1. Boot into recovery using:
    **fastboot reboot recovery**
2. Select Wipe Data/factory reset and confirm (In case of clean flash else skip this step).
3. Go back and select Apply update from ADB.
4. Type the following command in your terminal:
    **adb sideload rom.zip**
5. adb sideload firmware*.zip (only if there's a firmware update).
6. After installation complete, Reboot to system.

# That's all folks
After you’ve double checked that you followed the steps precisely, didn’t skip any and still have questions or got stuck, feel free to ask on our [`Telegram group`](https://t.me/awakenosolisa).


