#iBasso DX90 firmware modified by Lurker

**DISCLAIMER:** No changes were made to the basic player functionality and behavior! Expect the same bugs and misbehavior found in the base stock firmware! **No warranty at all: use the modified firmware at your own risk and responsibility!**

**NOTE:** starting with v2.1.5, to tell which version is running, go to _Settings_->_Advanced_->_System Info_ and check the _Model number_. The modification version number (L0, L1 etc) is right after the actual model number (DX90).

- `DX90FirmwareV2.1.5-L0.7z` - unused services are disabled.
- `DX90FirmwareV2.1.5-L1.7z` - unused services are disabled, fonts replaced with Roboto Condensed and Arial Unicode MS.

Firmware images (`update.img`) are compressed with [7-Zip](http://www.7-zip.org/) for it produces significantly smaller archives compared to ZIP.

#Detailed description of the changes

##Introduction for those who seeks the sound quality
All firmware versions for iBasso DX90, stock or with my modifications, are bit perfect. It means, with EQ turned off, the *sound data is not affected by the software, and is transferred to the DAC exactly as it is*. Any difference in sound signatures between versions are resulted from different conditions under which the hardware is running.

##1. Fonts replaced.

iBasso uses `Microsoft YaHei` for Latin-based and Chinese characters, and `Nimbus Sans Global Bold` for the rest (Cyrillic, Japanese, Korean, Thai etc). It also uses pre-calculated character width tables, which (confirmed by calculations!) do not correspond to any, or any combination, of those fonts. Regardless of the reason iBasso went this way, the resulting texts look awful for me, and it was the primary reason for the firmware modification.

The two fonts used by iBasso are replaced with one, which is `Roboto Condensed`, with the missing characters merged from `Arial Unicode MS`. Character width tables were calculated from the actual font metrics.

**Note:** still sometimes character spacing may look odd, but this is due to character widths are rounded to integer number of pixels, and because iBasso does not use kerning in text rendering.

##2. Unused services disabled.

The full list is:
* `netd (internet servers and services).
* `debuggerd` (gdb debugger interface, also creates crash logs of native applications).
* `rild` (controls wireless hardware).
* `rild3` (controls wireless hardware).
* `mediaserver` (indexes media files, provides access to them for Android applications).
* `installd` (required to install Android applications from APK).
* `servicemanager` (Android applications interface to hardware and resources).

It is obvious that none of them have any use in DX90. Note for the last two items: DX90 has removed Dalvik JVM, so there is no a way to install and run Android apps!

##3. CPU is always working at the highest performance.

**Note:** iBasso has incorporated this modification into stock firmware version 2.1.5.

Changes in the CPU working frequency during audio playback affects the stability of the power source and temperature, probably, also the stability of the sound stream from CPU to DAC. So, stable CPU speed also means stable power and temperature of other components: DAC, clock generator, op-amps. Stability of the environment parameters of the DAC and clock generator also leads to lower jitter.

The OS kernel supports the following CPU performance governors:
* `performance` (highest frequency)
* `ondemand` (frequency depends on CPU load; fast raise, fast scale down)
* `interactive` (frequency depends on CPU load; fast raise, slow scale down)
* `powersave` (lowest frequency)

The CPU in DX90 supports only two frequencies: 312 and 504MHz. It means, it only can be switched between these two frequencies. The power consumptions at these frequencies differ in around 2 times, and power dissipation at the high speed is notably more than at the low speed. But CPU in DX90 is not the main power consumer: display, flash, RAM, DAC and analog part (including headphone amplifier) in total consume much more. It means, the overall power consumption is not much increased when CPU is running in performance mode. Increased power consumption is more noticable for those who listen mostly MP3s, and much less for those who prefer high-resolution flacs and DSD.

Obviously, the firmware with this change is influenced by warming-up effect: from the cold start, it takes some minutes to achieve the working stable conditions. Then, it works in the most clean sound playback conditions that can be reached now.
