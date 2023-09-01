---
title: "AOSPA Sky"
dateString: September 2023
draft: false
tags: ["Installation", "sky",]
weight: 999999
---

# Basic requirements

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!

2. Make sure your computer has adb and fastboot.

3. Enable USB debugging on your device.

4. ROM is provided as-is with no warranty. While we attempt to verify everything works you are installing this at your own risk!

5. Both fastboot package and recovery rom is provided, flashing via fastboot package is preferred.

# Installing AOSPA using fastboot package

- Download aospa_sky-img-eng.redducc.zip
- Boot into fastboot using: **adb reboot bootloader**
- Erase your data by: **fastboot -w**
- Type the following command to flash the ROM:
    **fastboot update aospa_sky-img-eng.redducc.zip**

# Installing using recovery

- Download the TWRP recovery image from [here](https://github.com/pjgowtham/recovery_device_xiaomi_sky/releases).
- If your device isn’t already in fastboot mode, on the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type: **adb reboot bootloader** You can also boot into fastboot>- Flash boot image:
    **fastboot flash recovery twrp-3.7.0_12-0_LOCAL-20230826-04-sky.img**

# Installing from recovery [Method 1]

1. Boot into recovery using:
    **fastboot reboot recovery**
2. Select Wipe Data/factory reset and confirm.
3. Go back and select Apply update from ADB.
4. Type the following command in your terminal:
    **adb sideload aospa-topaz-unofficial-sky-20230901.zip**
5. After installation complete, Reboot to system.

#Installing from recovery [Method 2]

1. Move the ROM zip file to your phone's internal storage.
2. In TWRP, select "Install" and navigate to the location of the ROM zip. Swipe to install.
3. After installation, perform a factory reset: Wipe -> Format Data -> Yes. (Type)
4. After installation complete, Reboot to system.

# That's all folks
After you’ve double checked that you followed the steps precisely, didn’t skip any and still have questions or got stuck, feel free to ask on our [`Telegram group`](https://t.me/stayparanoid_sky).
