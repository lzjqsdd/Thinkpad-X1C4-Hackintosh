# Thinkpad-X1C4-Hackintosh
Thinpad X1 Carbon 4th(2016) Hackintosh EFI
- OpenCore: 0.6.2
- SystemInfo: MacOS Catalina 10.15.7 (19H2)
- HardwareInfo: https://psref.lenovo.com/syspool/Sys/PDF/ThinkPad/ThinkPad_X1_Carbon_4th_Gen/ThinkPad_X1_Carbon_4th_Gen_Spec.PDF
 - IGPU: HD Graphics 520
 - CPU: Skylake, Intel Core i5-6200U
 - Audio: Conexant CX20753/4

# Summary
- [x] Audio (AppleALC alc-layout-id: 14)
- [x] Trackpad\RedPoint multi gestures
- [x] Native IntelWifi (itlwm)
- [x] Native Buletooth
- [x] Battery status
- [X] HDMI output works fine
- [ ] mini DP may cause build-in display black screen

# Update
## 2020-10-27
- Change ACPIBatteryManager to SMCBatteryManager(Both kext works, but SMCBatteryManager more situable for VirtualSMC)
- Change itlwm to Airportitlwm, now can use native wifi manager and position service.(no need use Heiport), need Enable AppleSecureBoot in opencore config


## 2020-10-26
- Add CPUFriend Kext to keep cpu in low frequency 800Hz, and high frequency keep normal

## 2020-10-25
- Fix battery status by SSDT patch (https://github.com/RehabMan/Laptop-DSDT-Patch/blob/master/battery/battery_Lenovo-X230i.txt)
- Trackpad settings in SystemSettings works when battery fix. Before fix, the trackpad setting only try to find bluetooth trackpad devices, i guess it may think this is not a laptop when battey status broken
- Fix tunning backlight using keyborad shortcut, without DSDT patch

# Thanks
- https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html, most of this EFI configuration come from OpenCore Install Guide
- https://github.com/corpnewt/gibMacOS, help download os image and make boot usb
- https://github.com/acidanthera/AppleALC, help drive audio 
- https://github.com/RehabMan/Laptop-DSDT-Patch, help fix battery status
- https://github.com/acidanthera/BrightnessKeys, help fix backlight tunning
- https://github.com/xzhih/one-key-hidpi, help fix hidpi for build-in retina display
- https://github.com/OpenIntelWireless/itlwm, help fix intel wifi. Note: Download itlwm.kext(not airportitlwm.kext)
- https://github.com/OpenIntelWireless/IntelBluetoothFirmware, help fix buletooth
- https://github.com/OpenIntelWireless/HeliPort, help choose wifi, client for itlwm
- https://github.com/stevezhengshiqi/one-key-cpufriend, add cpu frequency control, current setting keep low frequency to 800hz (
suitable for me that condider more about battery life for laptop),  can use [Inter Power Gadget Tool](https://software.intel.com/content/www/us/en/develop/articles/intel-power-gadget.html) to monitor if your settings works