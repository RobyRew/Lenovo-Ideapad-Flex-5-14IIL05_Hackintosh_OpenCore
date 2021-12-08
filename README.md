# Hackintosh Guide for **Lenovo Ideapad Flex 5-14IlL05** and maybe similar models

**This guide it's updated to OpenCore 0.7.6 but not tested yet.**
Is not a finished product, if you want to test go for it, from my experience I think It should boot on to the recovery at least, during next days I hope to bring all functions working.
Tell me your experience on discussions releases.
<!-- shields -->
<div>
    <!-- downloads -->
    <a href="https://github.com/RobyRew/Lenovo-Ideapad-Flex-5-14IlL05_Hackintosh_OpenCore/releases">
        <img src="https://img.shields.io/github/downloads/RobyRew/Lenovo-Ideapad-Flex-5-14IlL05_Hackintosh_OpenCore/total" alt="downloads"/>
    </a>
    <!-- version -->
    <a href="https://github.com/RobyRew/Lenovo-Ideapad-Flex-5-14IlL05_Hackintosh_OpenCore/releases/latest">
        <img src="https://img.shields.io/github/release/RobyRew/Lenovo-Ideapad-Flex-5-14IlL05_Hackintosh_OpenCore.svg" alt="latest version"/>
    </a>
    <!-- platform -->
    <a href="https://github.com/RobyRew/Lenovo-Ideapad-Flex-5-14IlL05_Hackintosh_OpenCore">
        <img src="https://img.shields.io/badge/platform-macOS-lightgrey.svg" alt="platform"/>
    </a>
</div>
</br></br>

![Lenovo Ideapad Flex 5 14IlL05 running macOS Big Sur](/Docs/Images/Lenovo-Ideapad-Flex-5-14IlL05-Hackintosh-macOS.png)

[Amazon Page]( https://www.amazon.es/dp/B08D9H3LX5/ref=cm_sw_em_r_mt_dp_D2GHPB9EMDQV4ZX28W90?_encoding=UTF8&psc=1) 849,99€ *purchased 16/09/2020*


## Specs:
| Component | Name |
|:--- |:---:|
| Motherboard:  | LNVNB161216 (U3E1) |
| CPU: | Intel i5-1035G1 |
| RAM: | 8GB don't find the brand lol |
| iGPU: | Intel G1 (Mobile) |
| NVMe: | SKHynix HFM512GDHTNI-87A0B |
| Wifi/BT: | Intel(R) Wireless-AC 9560 160MHz |
| Audio: | RealTek |
| Trackpad: | HID Device |
| Keyboard: | Standard PS/2 Keyboard |

![Lenovo Ideapad Flex 5 14IlL05 Layout](/Docs/Images/Guide/Lenovo-Ideapad-Flex-5-14IlL05-layout.png)
These are all the external ports of the laptop. (**They all work**)

### Working
- [x]

```bash
```

# INSTALLATION GUIDE

---

## Making the Booteable USB

### From macOS:
[**Link to Apple's Guide**](https://support.apple.com/en-us/HT201372)

**Download installers:** [Monterrey](https://apps.apple.com/es/app/macos-monterey/id1576738294?mt=12) - [Big Sur](https://itunes.apple.com/us/app/macos-big-sur/id1526878132) - [Catalina](https://itunes.apple.com/us/app/macos-catalina/id1466841314) - [Mojave](https://itunes.apple.com/us/app/macos-mojave/id1398502828) - [High Sierra](https://itunes.apple.com/us/app/macos-high-sierra/id1246284741)

1. Connect a >=16 GB pendrive.
2. Open *Disk Utility* and Erase the USB with the name: *MyVolume*.
3. Open *Terminal* and use the proper commands for your macOS installer:
- Monterrey: `sudo /Applications/Install\ macOS\ Monterrey.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Big Sur: `sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Catalina: `sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- Mojave: `sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`
- High Sierra: `sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume`

![Terminal](/Docs/Images/Guide/BootableUSB.png)

### From Windows:

[**Link to Dortania's Guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/winblows-install.html)

### From Linux:

[**Link to Dortania's Guide**](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/linux-install.html)


---

# BIOS Settings:
- Make Sure you have [Latest BIOS]()

---

Only 2 posibilities for SMBIOS:
SMBIOS | CPU Type | GPU Type | Display Size
|:--- |:---:|:---:|:---:|
MacBookAir9,1	| Dual/Quad Core 12W | iGPU: G4/G7 | 13"
MacBookPro16,2 | Quad Core 28W | iGPU: G4/G7 | 13"

# Credits

[Apple](https://apple.com) (macOS)

[OpenCore Team](https://github.com/acidanthera/OpenCorePkg) (Bootloader)

[Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/coffee-lake.html#starting-point) (Guide)

[Olarilla](https://www.olarila.com/topic/9918-olarila-hackintosh-hackbook-lenovo-ideapad-s145-10th-gen-catalina-big-sur-monterey-full-dsdt-patches-clover-and-opencore/?tab=comments#comment-118083) (Some ideas for my build)

If this guide has been useful for you, don't forget to give me a star ⭐️❤️
