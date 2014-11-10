#iBasso DX90 firmware modified by Lurker

**DISCLAIMER:** No changes were made to the basic player functionality and behavior! Expect the same bugs and misbehavior found in the base stock firmware! **No warranty at all: use the modified firmware at your own risk and responsibility!**

**NOTE:** starting with v2.1.5, to tell which version is running, go to _Settings_->_Advanced_->_System Info_ and check the _Model number_. The modification version number (L0, L1 etc) is right after the actual model number (DX90).

- [`DX90FirmwareV2.1.5-L2.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L2.7z) - Based on L1. Unregistered video codecs [(4)](#4-unregistered-video-codecs), image size reduced (5), gapless buffer size increased (6), adb in _USB Charge Only_ mode (7).
- [`DX90FirmwareV2.1.5-L1.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L1.7z) - fonts replaced [(1)](#1-fonts-replaced), unused services disabled [(2)](#2-unused-services-disabled).
- [`DX90FirmwareV2.1.5-L0.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L0.7z) - unused services disabled [(2)](#2-unused-services-disabled).
- [`DX90FirmwareV2.1.0-Roboto-NoServices-Fast-Intl.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.0-Roboto-NoServices-Fast-Intl.7z) - fonts replaced [(1)](#1-fonts-replaced), unused services disabled [(2)](#2-unused-services-disabled), CPU at performance mode [(3)](#3-cpu-is-always-working-at-the-highest_performance), unregistered video codecs [(4)](#4-unregistered-video-codecs).

Firmware images (`update.img`) are compressed with [7-Zip](http://www.7-zip.org/) for it produces significantly smaller archives compared to ZIP.

##Instruction for firmware update:
1. Extract the archive file, and copy the `update.img` into the DX90.
2. Once copied, safely disconnect the DX90 from the computer.
3. Select _Settings_->_Advanced_->_System Update_ (the system update option appears only after the update.img is inside the DX90).
4. Click "OK" to start the firmware update.
5. The DX90 will reboot after firmware update completed. 
6. Select _Settings_->_Advanced_->_Factory Reset_ to reset the DX90. This is to avoid conflicts with residual settings from the previous firmware.
7. Delete the `update.img` from DX90.

#Detailed description of the changes

##Introduction for those who seeks the sound quality
All firmware versions for iBasso DX90, stock or with my modifications, are bit perfect. It means, with EQ turned off, the *sound data is not affected by the software, and is transferred to the DAC exactly as it is*. Any difference in sound signatures between versions are resulted from different conditions under which the hardware is running.

##1. Fonts replaced

iBasso uses `Microsoft YaHei` for Latin-based and Chinese characters, and `Nimbus Sans Global Bold` for the rest (Cyrillic, Japanese, Korean, Thai etc). It also uses pre-calculated character width tables, which (confirmed by calculations!) do not correspond to any, or any combination, of those fonts. Regardless of the reason iBasso went this way, the resulting texts look awful for me, and it was the primary reason for the firmware modification.

The two fonts used by iBasso are replaced with one, which is `Roboto Condensed`, with the missing characters merged from `Arial Unicode MS`. Character width tables were calculated from the actual font metrics.

**Note:** still sometimes character spacing may look odd, but this is due to character widths are rounded to integer number of pixels, and because iBasso does not use kerning in text rendering.

##2. Unused services disabled

The full list is:
* `netd` (internet servers and services).
* `debuggerd` (gdb debugger interface, also creates crash logs of native applications).
* `rild` (controls wireless hardware).
* `rild3` (controls wireless hardware).
* `mediaserver` (indexes media files, provides access to them for Android applications).
* `installd` (required to install Android applications from APK).
* `servicemanager` (Android applications interface to hardware and resources).

It is obvious that none of them have any use in DX90. Note for the last two items: DX90 has removed Dalvik JVM, so there is no a way to install and run Android apps!

##3. CPU is always working at the highest performance

**Note:** iBasso has incorporated this modification into stock firmware version 2.1.5.

Changes in the CPU working frequency during audio playback affects the stability of the power source and temperature, probably, also the stability of the sound stream from CPU to DAC. So, stable CPU speed also means stable power and temperature of other components: DAC, clock generator, op-amps. Stability of the environment parameters of the DAC and clock generator also leads to lower jitter.

The OS kernel supports the following CPU performance governors:
* `performance` (highest frequency)
* `ondemand` (frequency depends on CPU load; fast raise, fast scale down)
* `interactive` (frequency depends on CPU load; fast raise, slow scale down)
* `powersave` (lowest frequency)

The CPU in DX90 supports only two frequencies: 312 and 504MHz. It means, it only can be switched between these two frequencies. The power consumptions at these frequencies differ in around 2 times, and power dissipation at the high speed is notably more than at the low speed. But CPU in DX90 is not the main power consumer: display, flash, RAM, DAC and analog part (including headphone amplifier) in total consume much more. It means, the overall power consumption is not much increased when CPU is running in performance mode. Increased power consumption is more noticable for those who listen mostly MP3s, and much less for those who prefer high-resolution flacs and DSD.

Obviously, the firmware with this change is influenced by warming-up effect: from the cold start, it takes some minutes to achieve the working stable conditions. Then, it works in the most clean sound playback conditions that can be reached now.

##4. Unregistered video codecs

This tweak was implemented in modifications to 2.1.0, but not documented.

The codec set used by Mango player includes video playback related stuff. The tweak is to remove video codecs from declarations. If you hear the difference between 2.1.5-L1 and 2.1.5-L2, most probably this difference is caused by this tweak.

##5. Image size reduced

Stock firmware 2.1.5 image contains two redundant copies of the OS kernel. I believe they just take the space and increase the image size, and that's why I believe it is safe to remove them.

##6. Gapless buffer

The default buffer for gapless playback is 100 ms, meaning, the sound can be interrupted, if 100 ms is not enough to prepare the next file for playback. Increasing the buffer to 200 ms decreases the chance of such interrupts.

##7. ADB runs in _USB Charge Only_ mode

ADB is Android Debug Bridge. Though it is intended for debugging Android applications, some power users find it useful as well. It does not harm, nor it affects the sound. The only side effect for regular users is a "new device found" message on connecting DX90 to Windows in _Charge Only_ mode. You may ignore it, and ignore unrecognized device, or install "Android ADB Interface" drivers.

I never saw complains from Rockbox for DX90 (which has ADB turned on) users, and ADB is useful for myself to check the results of modifications, so I decided to keep it in the public release.
