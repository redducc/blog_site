---
title: "AOSPA Sky"
dateString: January 2024
draft: false
tags: ["Installation", "sky",]
weight: 999999
---

# Basic requirements

1. Read through the instructions at least once before actually following them, so as to avoid any problems due to any missed steps!

2. Make sure your computer has adb and fastboot.

3. Enable USB debugging on your device.

4. ROM is provided as-is with no warranty. While we attempt to verify everything works you are installing this at your own risk!

5. Both fastboot package and recovery rom is provided.

# Installing AOSPA using fastboot package

- Download aospa-uvite-beta-sky-20240121-image.zip.
- Boot into fastboot using: **adb reboot bootloader**
- Type the following command to flash the ROM:
    **fastboot update --skip-reboot aospa-uvite-beta-sky-20240121-image.zip**
- Click on Enter recovery.
- Click Wipe data/Factory reset, navigating via volume keys and format data.(Skip in case of dirty flashing)
- Flash latest Hyperos V816.0.5.0.UMWCNXM firmware. (If you are afraid to mess with firmware, you can simply flash recovery zip as it includes firmware by default.)
- Reboot to System.

# Installing using recovery

- Download the latest TWRP/aospa recovery image.
- If your device isn’t already in fastboot mode, on the computer, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type: **adb reboot bootloader** You can also boot into fastboot>- Flash boot image:
    **fastboot flash recovery recovery.img**

# Installing from recovery [Method 1]

1. Boot into recovery using:
    **fastboot reboot recovery**
2. Select Wipe Data/factory reset and confirm.(Skip in case of dirty flashing)
3. Go back and select Apply update from ADB.
4. Type the following command in your terminal:
    **adb sideload aospa-uvite-beta-sky-20240121.zip**
5. After installation complete, Reboot to system.

# Installing from recovery [Method 2]

1. Move the ROM zip file to your phone's internal storage.
2. In TWRP, select "Install" and navigate to the location of the ROM zip. Swipe to install.
3. After installation, perform a factory reset: Wipe -> Format Data -> Yes. (Type).(Skip in case of dirty flashing)
4. After installation complete, Reboot to system.

# Things to remember
- If you are on unofficial pa build or any other rom, you need to clean flash. If you are on aospa beta 1 you can simply dirty flash.
- Firmware is included by default in recovery package, so no need to flash seperately.
- If you are sane enough for flashing fastboot build, don't forget to flash firmware(Hyperos V816.0.5.0.UMWCNXM firmware).
- Please report any bug you face with proper logcat, open a command prompt (on Windows) or terminal (on Linux or macOS) window, and type: **adb logcat -c** Now type
    **adb logcat > logs.txt** while recreating the steps to get that specific issue.

# That's all folks
After you’ve double checked that you followed the steps precisely, didn’t skip any and still have questions or got stuck, feel free to ask on our [`Telegram group`](https://t.me/sushmit_chat).
