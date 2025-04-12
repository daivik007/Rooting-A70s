![LineageOS Logo](./lineage.png)

# Samsung A70s Rooting Kit

This repository provides a complete rooting kit for the Samsung A70s (SM-A707F variant) running **LineageOS 21**.  
It includes all necessary tools and files to root your device safely and efficiently.

## 📦 Included in the Kit

- **Booting Files** (Recovery + Boot image)
- **Magisk Modules** (Required modules for Magisk)
- **Odin Software** (Proprietary software for modifying Samsung recovery)
- **Misc Apps** (Google apps and others)

## ⚠️ Warnings and Risks

- Rooting **will void your warranty**.
- There's a **risk of bootloop** if instructions are not followed carefully.
- **Backup your data!** This process may require a factory reset.
- This kit is **only for Samsung A70s (SM-A707F)** running **LineageOS 21**.  
  Using it on other devices or firmware versions may cause irreversible damage.

## ⚙️ Installation Sections

- [Prerequisites](https://github.com/daivik007/Rooting-A70s#prerequisites)
- [Flashing LineageOS Recovery](https://github.com/daivik007/Rooting-A70s#flashing-lineageos-recovery)
- [Flashing LineageOS ROM](https://github.com/daivik007/Rooting-A70s#flashing-lineageos-rom)
- Installing Magisk and modules
- Adding modules to Magisk
- Removing modules
- Revert back to Stock UI

## Prerequisites

1. Make sure your phone is on the latest firmware for your region. In this case, it is Android 11.
2. A Windows machine
3. Clone this repo in your PC

```
git clone https://github.com/daivik007/Rooting-A70s.git
```

4. Install Samsung drivers from the repo

### To unlock bootloader

- Go to Settings > About Phone > Software information > Click **Build Number** a couple of times
- This should enable **Developer options** for your samsung device after entering your password.
- Go in Developer options > **Enable OEM unlocking**.

## Flashing LineageOS Recovery

1. Shutdown your phone.
2. Hold `Vol+` and `Vol-` and connect your phone to a PC.
3. Click volume up to continue the process on warning page.
4. Now your device is in **Download Mode**.
5. Open **Odin** and select:
   - `AP` → Select the **Lineage OS recovery** provided.
   - `BL`, `CP`, `CSC` → Leave blank.
6. In Options, uncheck everything.
7. Click **Start** and wait for the flash to complete.
8. Now you have your **Recovery** installed succesfully.

![Odin Recovery](./Screenshot_2.png)

## Flashing LineageOS ROM

1. Hold `Vol-` and `Power` to hard restart.
2. Shift to `Vol+` and `Power` to go to **Recovery**.
3. Here, go to Apply Update > Apply from ADB.
4. From the ADB folder, launch **cmd-here.exe**.

```
adb sideload [local path of custom rom]
```

5. Then again go for applying update from ADB.
6. If signature verification failed, install anyway.

```
adb sideload [magisk.apk path]
```

7. Repeat applying update from ADB

```
adb sideload [MindTheGapps path]
```

8. Reboot. Here it won't reboot and will ask for data reset.
9. Allow data reset and you'll be fine.

## Installing Magisk and modules

### Installing Magisk

1. Launch Magisk from app drawer and download the app from toast notification.
2. After rebooting, launch magisk and you should see Magisk icon.
3. Launch Magisk and click **Install** in the Magisk card and select **Direct Install** to install Magisk.
4. After reboot, launch Magisk again and go to it's settings. Enable this:
   - Hide the Magisk app
   - Systemless hosts
   - Zygisk
   - Enforce DenyList
   - User Authentication

### Installing Modules

### Reverting to Stock ROM

1. Connect your phone to a PC with USB.
2. Enable USB Debugging
   - Go to settings
   - Scroll down to About Phone
   - Scroll down to Build number
   - Click it several times and you should have developer options enabled.
   - Go to system > Developer options
   - Under debugging, enable USB debugging and Rooted debugging.
3. Install **Samsung USB Drivers** from the repository.
4. Keep the **Stock Firmware** folder ready.
5. Launch the **Odin** tool.
6. Now under the **ADB** folder, launch **cmd-here.exe** and type

```
adb reboot download
```

7. Now in Odin, you should see `<ID:0/006> Added!!` in the log
8. For adding files, select the appropriate files that matches the name from the **Stock Firmware** folder
9. In `CSC`, add CSC_OMC_ODM file.

![Odin stock](./Screenshot_3.png)

10. Now just hit Start and you are good to go!

## 🙏 Credits

- [LineageOS](https://lineageos.org/)
- [Magisk by topjohnwu](https://github.com/topjohnwu/Magisk)
- [TWRP Recovery](https://twrp.me/)
- Special thanks to all open-source developers who made this possible.

---

## 📜 License

This project is released with respect to the licenses of included open-source projects.  
Please refer to their respective licenses for usage guidelines.
