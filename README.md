# Hackintosh Guide for **Lenovo-Ideapad-Flex-5-14IlL05** and similar models

This summer this will be a working hackintosh laptop running macOS, Stay tunned for that...



############

############

############

########################

############

############

############

########################

############

############

############

**This guide it's updated to OpenCore 0.7.1 and tested on my main device.**

![Asus FX504GE running macOS Big Sur](/Images/Asus-FX504-macOS.png)

[Amazon Page](https://www.amazon.es/dp/B07D4W2CY6/ref=cm_sw_em_r_mt_dp_gUF8FbYQW48NV) 1.199€ *purchased 18/09/2018*


## Specs:
| Component | Name |
|:--- |:---:|
| Motherboard:  | FX504GE **HM370** |
| CPU: | Intel i7-8750H |
| RAM: | 16GB **SK Hyinix** HMA82GS6CJR8N-VK 2666Mhz |
| iGPU: | Intel UHD 630 (Mobile) |
| dGPU: | NVIDIA GeForce GTX 1050 Ti (DISABLED) |
| SSD: | Samsung 970 EVO Plus |
| HDD: | HGST HTS721010A9E630 |
| Wifi/BT: | Intel(R) Wireless-AC 9560 160MHz (Type CNVi) |
| Audio: | Realtek ALC255 |
| Ethernet: | Realtek RTL8111 |
| Trackpad: | ELAN1200 Precision TouchPad (Type HID) |
| Keyboard: | Standard PS/2 Keyboard |

![Asus FX504GE Layout](/Images/Guide/Asus-FX504GE-layout.png)
These are all the external ports of the laptop. (**They all work**)

### Working
- [x] **Tested with macOS High Sierra, Mojave, Catalina, Big Sur, and Monterrey**
- [x] **Wifi** (Thanks to [AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm/releases) and loading from system the kext: `IO80211Family.kext`)
- [x] **Bluetooth:** (Thanks to [IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware/releases))
- [x] **Audio:** Realtek ALC255 (Thanks to AppleALC.kext with layout-id=3 setted in Device Properties)
- [x] **USB:** All internal and external ports (Thanks to SSDT-EC-USBX-LAPTOP.aml)
- [x] **Ethernet:** Realtek RTL8111 (Thanks to RealtekRTL8111.kext)
- [x] **Trackpad:** (Working thanks to VoodooI2C.kext, VoodooI2CHID.kext and SSDT-XOSI.aml)
- [x] **HDMI:** Works almost perfect. 
- [x] **Shutdown:** Yes
- [x] **Restart:** Yes
- [x] **Sleep/Wake:** Yes

### Not working
- dGPU (Any support in Mojave and up).
- Continuity Features (not working for now, waiting on https://openintelwireless.github.io/).


```bash
```

# INSTALLATION GUIDE

---

## Making the Booteable USB

### From macOS:
[**Link to Apple's Guide**](https://support.apple.com/en-us/HT201372)

**Download installers:** [Monterrey Beta 2](http://swcdn.apple.com/content/downloads/54/23/071-59953-A_U9D4NB05NR/nqzt71pnylsuux326a4vqexb33oz0auhas/InstallAssistant.pkg)(Execute de .pkg to extract the installer) - [Big Sur](https://itunes.apple.com/us/app/macos-big-sur/id1526878132) - [Catalina](https://itunes.apple.com/us/app/macos-catalina/id1466841314) - [Mojave](https://itunes.apple.com/us/app/macos-mojave/id1398502828) - [High Sierra](https://itunes.apple.com/us/app/macos-high-sierra/id1246284741)

1. Connect a >=16 GB pendrive.
2. Open *Disk Utility* and Erase the USB with the name: *MyVolume*.
3. Open *Terminal* and use the proper commands for your macOS installer:
- Monterrey: `sudo /Applications/Install\ macOS\ 12\ Beta.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Big Sur: `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Catalina: `sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Mojave: `sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- High Sierra: `sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

![Terminal](Images/Guide/BootableUSB.png)

### From Windows:

[**Link to Dortania's Guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html)

### From Linux:

[**Link to Dortania's Guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/linux-install.html)


---

# BIOS Settings:
- Make Sure you have [Latest BIOS v320](https://www.asus.com/supportonly/ASUS%20TUF%20GAMING%20FX504/HelpDesk_Download/)
- After Updating the BIOS, stock configuration works, so don't worry about this part.

---

# OpenCore Configuration

## [Here it's my config.plist and the explanation:](/config.plist.md)
#### [ACPI](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#acpi)
#### [Booter](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#booter)
#### [DeviceProperties](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#deviceproperties)
#### [Kernel](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#kernel)
#### [Misc](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#misc)
#### [NVRAM](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#nvram)
#### [PlatformInfo](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#platforminfo)
#### [UEFI](https://github.com/RobyRew/ASUS-FX504GE-Hackintosh_Updated_OpenCore/blob/master/config.plist.md#uefi)

---

# Post Install (Important!!)
Open Terminal.app and run those commands:
```bash
sudo rm /Library/Preferences/SystemConfiguration/NetworkInterfaces.plist
sudo rm /Library/Preferences/SystemConfiguration/preferences.plist
```
---

# BenchMarks:
#### Cinebench R23:
![Cinebench R23](/Images/Benchmarks/Cinebench_R23.png)

#### GeekBench 5:
![GeekBench 5_CPU Score](/Images/Benchmarks/GeekBench5_CPU.png)
![GeekBench 5_GPU Score](/Images/Benchmarks/GeekBench5_GPU.png)
https://browser.geekbench.com/v5/cpu/5707123

---

# Credits

[Apple](https://apple.com) (macOS)

[OpenCore Team](https://github.com/acidanthera/OpenCorePkg) (Bootloader)

[Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake.html#starting-point) (Guide)

[PoomSmart](https://github.com/PoomSmart/ASUS-FX504GE-Hackintosh) (Some ideas for my build)

[MegaStood](https://github.com/MegaStood/Hackintosh-FX504GE-ES72) (Properties and boot argument for HDMI output)
