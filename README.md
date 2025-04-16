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
- This kit is **only for Samsung A70s (SM-A707F)** running **Android 11**.  
  Using it on other devices or firmware versions may cause irreversible damage.

## ⚙️ Installation Sections

- 🚧 [Prerequisites](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-prerequisites)
- 🔧 [Flashing LineageOS Recovery](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-flashing-lineageos-recovery)
- 🔧 [Flashing LineageOS ROM](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-flashing-lineageos-rom)
- 🔧 [Installing Magisk and Magisk Modules](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-installing-magisk-and-magisk-modules)
- 📦 [Core Modules](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-core-modules)
- 🌟 [Useful Modules](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-useful-modules)
- 🗑️ [Uninstallation](https://github.com/daivik007/Rooting-A70s?tab=readme-ov-file#-uninstallation)

## 🚧 Prerequisites

1. Make sure your phone is on the latest firmware for your region. In this case, it is Android 11.
2. A Windows machine.
3. Download required files from [Release](https://github.com/daivik007/Rooting-A70s/releases/new).

### To unlock bootloader

- Go to Settings > About Phone > Software information > Click **Build Number** a couple of times
- This should enable **Developer options** for your samsung device after entering your password.
- Go in Developer options > **Enable OEM unlocking**.

## 🔧 Flashing LineageOS Recovery

1. Shutdown your phone.
2. Hold `Vol+` and `Vol-` and connect your phone to a PC.
3. Click volume up to continue the process on warning page.
4. Now your device is in **Download Mode**.  
   _For verification, FRP Lock and OEM Lock should be OFF and KG STATUS should be checking._

5. Open **Odin** and select:
   - `AP` → Select the **Lineage OS recovery** provided.
   - `BL`, `CP`, `CSC` → Leave blank.
6. In Options, only check `F. Reset Time`.
7. Click **Start** and wait for the flash to complete.
8. Now you have your **Recovery** installed succesfully.

![Odin Recovery](./Screenshot_2.png)

## 🔧 Flashing LineageOS ROM

1. Hold `Vol-` and `Power` to hard restart.
2. Shift to `Vol+` and `Power` to go to **Recovery**.
3. Go to Factory Reset > Format system partition.
4. Then, go to Apply Update > Apply from ADB.
5. From the ADB folder, launch **cmd-here.exe**.

```
adb sideload [local path of custom rom]
```

6. Then again go for applying update from ADB.
7. If signature verification failed, install anyway.

```
adb sideload [magisk.apk path]
```

8. Repeat applying update from ADB

```
adb sideload [MindTheGapps path]
```

9. Reboot. Here it won't reboot and will ask for data reset.
10. Allow data reset and you'll be fine.

## 🔧 Installing Magisk and Magisk Modules

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

### Module Installation

- Download the .zip file of the module
- Go to Magisk > Modules > Install from storage
- Select the .zip package
- Reboot!

### Passing Play Integrity

1. Download PIF, TrickyStore, TrickyStore Addon.
2. Install PIF and reboot.
3. Install TrickyStore and reboot.
4. After reboot, cick on the action button on PIF module.
5. Go to `/data/adb` using [ZArchiver](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver&hl=en_IN). There you will find a `pif.json` file.
6. Copy that file to `data/adb/modules/playintegrityfix`.
7. Install TrickyStore Addon and reboot.
8. After reboot, click on the action button of `TrickStore` module. this will install KsuWebUI if you do not have KsuWebUI or MMRL installed. KsuWebUI is preferred.
9. Open KsuWebUI and click on Tricky Store.
10. Click on menu > click on `Set Valid Keybox`.
11. Click on menu again > click on `Set Security Patch` > click on `Get Security Patch` > click on `Save`.
12. Done. Now you should have basic, device and strong integrity in both legacy and new response.

_Do not check play integrity too frequently. Do not check at all if not necessary. Because if you check too frequently, Google with get sus._

## 📦 Core Modules

### 🔹 [PlayIntegrityFix](https://github.com/chiteroman/PlayIntegrityFix)

Files: `relative file location`  
This module tries to fix Play Integrity and SafetyNet verdicts to get a valid attestation.

### 🔹 [TrickyStore](https://github.com/5ec1cff/TrickyStore)

Files: `relative file location`  
This module is used for modifying the certificate chain generated for android key attestation.

### 🔹 [TrickyStore Addon](https://github.com/KOWX712/Tricky-Addon-Update-Target-List)

Files: `relative file location`  
This module is used for configuring Tricky Store target.txt with KSU WebUI.

### 🔹 [playcurlNEXT](https://github.com/daboynb/playcurlNEXT)

Files: `relative file location`  
This is a rewrite of Playcurl, the old version became outdated as many things have changed. Paradoxically, this is more lightweight and easier to use.

### 🔹 [LSposed_mod](https://github.com/mywalkb/LSPosed_mod)

Files: `relative file location`  
A Riru / Zygisk module trying to provide an ART hooking framework which delivers consistent APIs with the OG Xposed, leveraging LSPlant hooking framework.

## 🌟 [Useful Modules](https://awesome-android-root.link/apps)

### 🔹 [WearableSpoof](https://github.com/Simon1511/WearableSpoof)

Files: `relative file location`  
WearableSpoof is a module for LSPosed that lets you use Samsung apps (for example Wearable/Gear, SmartThings, ...) on Samsung phones running AOSP ROMs.

Required Files: [APK](https://www.apkmirror.com/apk/samsung-electronics-co-ltd/galaxy-buds2/galaxy-buds2-manager-7-0-25022451-release/galaxy-buds2-manager-7-0-25022451-android-apk-download/?redirected=thank_you_invalid_nonce),
[Restricted Settings](https://xdaforums.com/t/restricted-settings-for-non-playstore-apps.4714632/)

### 🔹 [Twifucker](https://github.com/Xposed-Modules-Repo/com.twifucker.hachidori/)

Files: `relative file location`  
Twitter modded LSposed module

Required Files: [APK](https://twitter.en.uptodown.com/android/download/1056623309)

### 🔹 [InstaEclipse](https://github.com/ReSo7200/InstaEclipse)

Files: `relative file location`  
InstaEclipse is an LSPosed module designed to enhance your Instagram experience with advanced features like developer options, ghost mode, distraction-free mode, and more!

Required Files: [APK](https://www.apkmirror.com/apk/instagram/instagram-instagram/instagram-377-0-0-0-10-release/instagram-377-0-0-0-10-3-android-apk-download/?redirected=download_invalid_nonce)

### 🔹 [ReVancedXposed](https://github.com/chsbuffer/ReVancedXposed)

Files: `relative file location`  
Revanced app versions for YouTube, YouTube Music and Spotify

### 🔹 [Magisk iOS Emoji](https://github.com/Keinta15/Magisk-iOS-Emoji)

Files: `relative file location`  
Systemlessly replaces the emoji font with iOS Emoji.

### 🔹 [Disable FLAG SECURE](https://github.com/VarunS2002/Xposed-Disable-FLAG_SECURE)

Files: `relative file location`  
Xposed Module to Disable `FLAG_SECURE`, enabling screenshots, screen sharing and recording in apps that normally wouldn't allow it.

### 🔹 [Private DNS Android](https://github.com/karasevm/PrivateDNSAndroid)

Files: `relative file location`  
A quick settings tile to switch your private dns provider. Supports any number of providers. Makes it easy to turn adblocking dns servers on or off with just a single tap.

### 🔹 [Pixelify Google Photos](https://github.com/BaltiApps/Pixelify-Google-Photos)

Files: `relative file location`  
LSPosed / EdXposed module to add Google Pixel features on Google Photos for any device.

### 🔹 [Looki75 Product Sans Font](https://github.com/Looki75/looki75productsansfont)

Files: `relative file location`  
This is a module to install Google Sans font (aka Product Sans) systemlessly through Magisk.

### 🔹 [YABP](https://github.com/Magisk-Modules-Alt-Repo/YetAnotherBootloopProtector)

Files: `relative file location`  
This module try to protect your device from bootloops and system ui failures caused by Magisk/KernelSU/APatch Modules.

### 🔹 [GMS Flags](https://github.com/polodarb/GMS-Flags)

Files: `relative file location`  
GMS Flags is a tool for changing parameters in Google services to activate or deactivate certain functionality in Google applications.

### 🔹 [StevenBlock](https://github.com/mikropsoft/StevenBlock)

Files: `relative file location`  
Advanced Ad-Blocking Module for Android. Compatible with Magisk, KernelSU, and APatch.

### 🔹 [GCAM](https://www.celsoazevedo.com/files/android/google-camera/dev-BigKaka/f/dl80/3/)

Files: `relative file location`  
Google Pixel Camera MOD for Samsung A70s.

## 🗑️ Uninstallation

### Magisk Modules

**Method 1: Via Magisk App (Recommended)**

1. **Open the Magisk App**.
2. Go to the **Modules** section.
3. Find the module you want to remove.
4. Tap the **trash icon** next to the module.
5. **Reboot** your device.

> ✅ This is the safest and cleanest way to uninstall a module.

---

**Method 2: Disable Module Without Booting (If Device is Bootlooping)**

1. **Boot into Custom Recovery (e.g., TWRP)**.
2. Navigate to:
   ```
   /data/adb/modules/
   ```
3. Delete the folder of the module you want to remove.

   Example:

   ```bash
   rm -rf /data/adb/modules/module-name
   ```

4. Optionally, delete the file:
   ```
   /data/adb/modules/module-name/update
   ```
5. **Reboot** your device.

---

**Method 3: Using Magisk’s `disable` Flag (Advanced Recovery Option)**

1. In custom recovery, **create a file** named:
   ```
   /cache/.disable_magisk
   ```
2. This **disables all modules** temporarily.
3. Boot the phone, open Magisk, and remove the faulty module.
4. Reboot normally.

### Magisk

_Use this only if you want to remove Magisk and unroot your device completely._

1. **Open the Magisk App**.
2. Tap the **Settings icon** (⚙️).
3. Scroll down and tap on **Uninstall Magisk**.
4. Choose **"Complete Uninstall"**.
5. Magisk will prompt for reboot. Tap **Yes**.
6. Your phone will **reboot and Magisk will be removed**.

> ✅ This will restore your stock `boot.img` if you originally patched it with Magisk.

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

_It should only take 1-2 reboots to get to boot up the OS. If it takes more than that, consider your phone in a bootloop. Head over to this [video](https://www.youtube.com/watch?v=SL6IoYwI8Kg) to get out of bootloop._

## 🙏 Credits

This project wouldn’t be possible without the contributions and efforts of various developers and communities across the Android and rooting ecosystem.

### 🔧 Tools & Frameworks

- **LineageOS** – [https://lineageos.org](https://lineageos.org)
- **Magisk** by topjohnwu – [https://github.com/topjohnwu/Magisk](https://github.com/topjohnwu/Magisk)
- **Odin Flash Tool** – Proprietary Samsung flashing tool
- **ADB & Fastboot Tools** – [https://developer.android.com/studio/releases/platform-tools](https://developer.android.com/studio/releases/platform-tools)

### 📦 Core Modules & Contributors

- **PlayIntegrityFix** – [@chiteroman](https://github.com/chiteroman)
- **TrickyStore & Addon** – [@5ec1cff](https://github.com/5ec1cff), [@KOWX712](https://github.com/KOWX712)
- **playcurlNEXT** – [@daboynb](https://github.com/daboynb)
- **LSposed_mod** – [@mywalkb](https://github.com/mywalkb)

### 🌟 Useful Modules & Creators

- **WearableSpoof** – [@Simon1511](https://github.com/Simon1511)
- **Twifucker** – [@Xposed-Modules-Repo](https://github.com/Xposed-Modules-Repo/com.twifucker.hachidori/)
- **InstaEclipse** – [@ReSo7200](https://github.com/ReSo7200)
- **ReVancedXposed** – [@chsbuffer](https://github.com/chsbuffer)
- **Magisk iOS Emoji** – [@Keinta15](https://github.com/Keinta15)
- **Disable FLAG_SECURE** – [@VarunS2002](https://github.com/VarunS2002)
- **Private DNS Android** – [@karasevm](https://github.com/karasevm)
- **Pixelify Google Photos** – [@BaltiApps](https://github.com/BaltiApps)
- **Looki75 Product Sans Font** – [@Looki75](https://github.com/Looki75)
- **YABP** – [@Magisk-Modules-Alt-Repo](https://github.com/Magisk-Modules-Alt-Repo)
- **GMS Flags** – [@polodarb](https://github.com/polodarb)
- **StevenBlock** – [@mikropsoft](https://github.com/mikropsoft)
- **GCAM Port** – [BigKaka](https://www.celsoazevedo.com/files/android/google-camera/dev-BigKaka/)

### 📁 Additional Resources

- **ZArchiver** – [Google Play Store](https://play.google.com/store/apps/details?id=ru.zdevs.zarchiver&hl=en_IN)
- **APKMirror** – [https://www.apkmirror.com](https://www.apkmirror.com)
- **XDA Forums** – [https://xdaforums.com](https://xdaforums.com)

---

Special thanks to the open-source Android modding community and everyone who contributed directly or indirectly to this project 💙

## 📜 License

This project is released with respect to the licenses of included open-source projects.  
Please refer to their respective licenses for usage guidelines.
