#iBasso DX90 firmware modified by Lurker

**DISCLAIMER:** No changes were made to the basic player functionality and behavior! Expect the same bugs and misbehavior found in the base stock firmware! **No warranty at all: use the modified firmware at your own risk and responsibility!**

**NOTE:** starting with v2.1.5, to tell which version is running, go to _Settings_->_Advanced_->_System Info_ and check the _Model number_. The modification version number (L0, L1 etc) is right after the actual model number (DX90).

- [**`DX90FirmwareV2.5.1-L1.7z`**](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.5.1-L1.7z) - same as L0, but with default fonts.
- [**`DX90FirmwareV2.5.1-L0.7z`**](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.5.1-L0.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]), custom built NTFS drivers ([8]), ultimate cleanup ([9]).
- [`DX90FirmwareV2.4.0-L2.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.4.0-L2.7z) - same as L1, but with default fonts.
- [`DX90FirmwareV2.4.0-L1.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.4.0-L1.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]), custom built NTFS drivers ([8]), ultimate cleanup ([9]).
- [`DX90FirmwareV2.4.0-L0.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.4.0-L0.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]), custom built exFAT/NTFS drivers ([8]).
- [`DX90FirmwareV2.3.0-L1.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.3.0-L1.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]), custom built exFAT/NTFS drivers ([8]).
- [`DX90FirmwareV2.3.0-L0.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.3.0-L0.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]).
- [`DX90FirmwareV2.2.0-L1.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.2.0-L1.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]), custom built exFAT/NTFS drivers ([8]).
- [`DX90FirmwareV2.2.0-L0.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.2.0-L0.7z) - fonts replaced ([1]), adb in _USB Charge Only_ mode ([7]). **Note:** In this build, iBasso already have done all the optimizations that I did before, and even more!
- [`DX90FirmwareV2.1.8-L1.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.8-L1.7z) - same as L0, but with default fonts.
- [`DX90FirmwareV2.1.8-L0.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.8-L0.7z) - fonts replaced ([1]), unused services disabled ([2]), unregistered video codecs ([4]), firmware image size reduced ([5]), adb in _USB Charge Only_ mode ([7]).
- [**`DX90FirmwareV2.1.5-L5.7z`**](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L5.7z) - same as L4, but with default fonts.
- [**`DX90FirmwareV2.1.5-L4.7z`**](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L4.7z) - based on L2, with custom built NTFS drivers ([8]) and ultimate cleanup ([9]).
- [`DX90FirmwareV2.1.5-L3.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L3.7z) - same as L2, but with default fonts.
- [`DX90FirmwareV2.1.5-L2.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L2.7z) - based on L1. Unregistered video codecs ([4]), firmware image size reduced ([5]), gapless buffer size increased ([6]), adb in _USB Charge Only_ mode ([7]).
- [`DX90FirmwareV2.1.5-L1.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L1.7z) - fonts replaced ([1]), unused services disabled ([2]).
- [`DX90FirmwareV2.1.5-L0.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.5-L0.7z) - unused services disabled ([2]).
- [`DX90FirmwareV2.1.0-Roboto-NoServices-Fast-Intl.7z`](https://github.com/Lurker00/DX90-firmware/raw/master/release/DX90FirmwareV2.1.0-Roboto-NoServices-Fast-Intl.7z) - fonts replaced ([1]), unused services disabled ([2]), CPU at performance mode ([3]), unregistered video codecs ([4]).

[1]: #1-fonts-replaced
[2]: #2-unused-services-disabled
[3]: #3-cpu-is-always-working-at-the-highest-performance
[4]: #4-unregistered-video-codecs
[5]: #5-image-size-reduced
[6]: #6-gapless-buffer
[7]: #7-adb-runs-in-usb-charge-only-mode
[8]: #8-custom-built-exfat-and-ntfs-drivers
[9]: #9-ultimate-cleanup

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

In DAPs, with limited space and one battery as the power source for both digital and analog circuits, the sound signature also depends on CPU load. So, any changes in the firmware code, even unrelated directly to the sound path, may affect the sound signature.

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

**Note:** iBasso has incorporated this modification into stock firmware partially in version 2.1.8, and fully starting from version 2.2.0. Actually, they have removed even more!

##3. CPU is always working at the highest performance

Changes in the CPU working frequency during audio playback affects the stability of the power source and temperature, probably, also the stability of the sound stream from CPU to DAC. So, stable CPU speed also means stable power and temperature of other components: DAC, clock generator, op-amps. Stability of the environment parameters of the DAC and clock generator also leads to lower jitter.

The OS kernel supports the following CPU performance governors:
* `performance` (highest frequency)
* `ondemand` (frequency depends on CPU load; fast raise, fast scale down)
* `interactive` (frequency depends on CPU load; fast raise, slow scale down)
* `powersave` (lowest frequency)

The CPU in DX90 supports only two frequencies: 312 and 504MHz. It means, it only can be switched between these two frequencies. The power consumptions at these frequencies differ in around 2 times, and power dissipation at the high speed is notably more than at the low speed. But CPU in DX90 is not the main power consumer: display, flash, RAM, DAC and analog part (including headphone amplifier) in total consume much more. It means, the overall power consumption is not much increased when CPU is running in performance mode. Increased power consumption is more noticable for those who listen mostly MP3s, and much less for those who prefer high-resolution flacs and DSD.

Obviously, the firmware with this change is influenced by warming-up effect: from the cold start, it takes some minutes to achieve the working stable conditions. Then, it works in the most clean sound playback conditions that can be reached now.

**Note:** iBasso has incorporated this modification into stock firmware starting from version 2.1.5.

##4. Unregistered video codecs

This tweak was implemented in modifications to 2.1.0, but not documented.

The codec set used by Mango player includes video playback related stuff. The tweak is to remove video codecs from declarations. If you hear the difference between 2.1.5-L1 and 2.1.5-L2, most probably this difference is caused by this tweak.

**Note:** iBasso has incorporated this modification into stock firmware starting from version 2.2.0.

##5. Image size reduced

Stock firmware 2.1.5 image contains two redundant copies of the OS kernel. I believe they just take the space and increase the image size, and that's why I believe it is safe to remove them.

Stock firmware 2.1.8 image contains two redundant copies of the OS kernel as well, but I've removed only one of them.

**Note:** iBasso has incorporated this modification into stock firmware starting from version 2.2.0. Also, they have removed a lot of other files that are not used, so that 2.2.0 has the smallest image file size!

##6. Gapless buffer

The default buffer for gapless playback is 100 ms, meaning, the sound can be interrupted, if 100 ms is not enough to prepare the next file for playback. Increasing the buffer to 200 ms decreases the chance of such interrupts.

**Note:** iBasso has incorporated this modification into stock firmware starting from version 2.1.8, increasing the buffer to 1000 ms.

##7. ADB runs in _USB Charge Only_ mode

ADB is Android Debug Bridge. Though it is intended for debugging Android applications, some power users find it useful as well. It does not harm, nor it affects the sound. The only side effect for regular users is a "new device found" message on connecting DX90 to Windows in _Charge Only_ mode. You may ignore it, and ignore unrecognized device, or install "Android ADB Interface" drivers.

I never saw complains from Rockbox for DX90 (which has ADB turned on) users, and ADB is useful for myself to check the results of modifications, so I decided to keep it in the public release.

##8. Custom built exFAT and NTFS drivers
Recently I've finished [my port of exFAT and NTFS drivers for Android](https://github.com/Lurker00/Android-fs) and decided to use them in DX90 firmware. They are built from the latest original source code (DX90 uses old versions), and I've made some changes to exFAT driver which I found useful for DX90:
* Original exFAT driver relies on proper unmount of the file system, which often can't be achieved for a battery powered device. With an accidental power loss, or hot SD card unplug, the original driver may leave the file system in a damaged state.
* Original exFAT driver make unneeded writes to the SD card: every boot and unmount (marks the volume as "opened" and "closed"), and on every file access (by modifying last access time).
 
My build of drivers never change last access time for both exFAT and NTFS, and exFAT driver "opens" the volume only on requrests that require writes. Also, the exFAT driver now keeps the volume "closed", and in consistent state, as much as possible, preventing file system corruption on device power loss or SD card hot unplug.

Avoiding unneeded writes may also reduce the famous "fade in/fade out" problem, which, by my opinion, is rooted into ["wear leveling"](https://en.wikipedia.org/wiki/Wear_leveling) activity of an SD card internal controller.

**Note:** I've found that in 2.4.0 iBasso started to use kernel mode exFAT drivers. I've removed mine from 2.4.0L1 and L2.

##9. Ultimate cleanup

This finalizes the process started by "unused services disabled ([2])", and is based on the [work done for DX80](https://github.com/Lurker00/DX80-firmware/blob/master/release/README.md). I mean it, because now `MangoPlayer` is the only running process, apart from the `kernel`, `init`, which are required, obviously, and `vold`, that serves media mounts!

The stock firmware image contains a lot of files that are not actually used. I've removed most of them.

The MangoPlayer sound library uses a proprietary implementation of [OpenMAX](https://en.wikipedia.org/wiki/OpenMAX) engine, that supports sound playback via [OpenSL ES](https://en.wikipedia.org/wiki/OpenSL_ES) interface, which is not used in DX90. I've written a [small stub to replace the system library](https://github.com/Lurker00/DX80-firmware/blob/master/src/jni), which allowed me to remove even more files. After this, MangoPlayer also requires less RAM to work, because OpenGL ES related stuff is not loaded with the player.

System logging is turned off. In particular, it is achived by a [`liblog.so` stub that does nothing](https://github.com/Lurker00/DX80-firmware/blob/master/src/jni).

