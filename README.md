# OpenCore EFI

![About This Mac](./images/AboutThisMac.jpg "About This Mac")


 OpenCore EFI for Intel Alder Lake

- Intel i9-12900K
- Gigabyte Z690 Aorus Elite DDR4 AX
- AMD Radeon RX 580 dGPU
- 64 GB DDR4-3000
- Wifi/BT via BRCM20702

- [OC Version 0.8.8](https://github.com/acidanthera/OpenCorePkg/releases/tag/0.8.8)

# What is working?

Almost everything:
- MacOS Ventura 13.1 Update (set up the hack on 13.0.1)
- Audio
- DP and HDMI via dGPU
- DRM Content (Netflix, Amazon Prime, Apple TV+)
- Wifi/BT out of the box
- all iServices (iMessage, iCloud, AirDrop, unlock with Apple Watch)
- CPU temperature and fan speeds in iStats and/or Intel Power Gadget
- USB Ports mapped: 15 in use out of 21 possibly available
  - 2x USB 2.0 on the front panel via internal USB header (one port in USB mapping)
  - 4x USB 2.0 on the back (one port in USB mapping)
  - 1x RGB Fusion 2.0
  - 2x USB 3.2 Gen 1 on the front via internal USB header
  - 2x USB 3.2 Gen 2 on the back
  - 3x USB 3.2 Gen 1 on the back   
	- 3x with USB 2.0 personality
  - 2x USB-C (one back and front with up to 10 Gbps)
- Continuity Camera with iPhone 14 Pro

# Used Kexts?

| **Kext**  | **Version**  |
|:----------|:----------|
| [Lilu](https://github.com/acidanthera/Lilu/releases/tag/1.6.3)    | 1.6.3   |
| [AppleALC](https://github.com/acidanthera/AppleALC/releases/tag/1.7.8)| 1.7.8 |
| [WhateverGreen](https://github.com/acidanthera/WhateverGreen/releases/tag/1.6.3)    | 1.6.3    
| [VirtualSCM](https://github.com/acidanthera/VirtualSMC/releases/tag/1.3.0)    | 1.3.0    |
| [SMCProcessor](https://github.com/acidanthera/VirtualSMC/releases/tag/1.3.0)    | 1.3.0    |
| [SMCSuperIO](https://github.com/acidanthera/VirtualSMC/releases/tag/1.3.0)    | 1.3.0    |
| [CpuTopologyRebuild](https://github.com/b00t0x/CpuTopologyRebuild/releases/tag/1.1.0)    | 1.1.0    |
| [CpuTTscSync](https://github.com/acidanthera/CpuTscSync/releases/tag/1.0.9)    | 1.0.9    |
| [NVMEfix](https://github.com/acidanthera/NVMeFix/releases/tag/1.1.0)    | 1.1.0    |
| [LucyRTL8125Ethernet](https://www.insanelymac.com/forum/files/file/1004-lucyrtl8125ethernet/)    | 1.1.0    |
| [RadeonSensor](https://github.com/aluveitie/RadeonSensor/releases/tag/0.3.1) | 0.3.1 |
| [RestrictEvents](https://github.com/acidanthera/RestrictEvents/releases/tag/1.0.9) | 1.0.9 | 

# What doesn't work well?

~~Usually the hack boots as expected, but sometimes it stucks at the apple logo w/o any progress bar. So rebooting via Reset button is needed. Currently I've no clue why that is happening.~~ 

Sleep at all. Don't have the change to get into sleep yet.

# Current State?

~~ACPI Patches introduced according to guide 2 for Gigabyte Z690 mainboards since neither mouse nor keyboard were working and restart of the whole system was needed. Has to be observed further if Sleep has killed USB functionality.~~ 

Currently booting is possible w/ just a small issue: ~~the additionally connected USB-Keyboard~~ USB 2.0 (USB legacy mode is enabled in BIOS) seems not to be working, unless USB-C is disconnected before boot, so I guess it's not OC related but more a generell issue.

At the moment I'm being quite satisfied with the system. Added GPRW renaming to improve S3 handling. Needs some more testing.

# Followed Guides?

1. Followed the Comet Lake guide provided by Dorania:  
[Dortania Team](https://dortania.github.io/OpenCore-Install-Guide/config.plist/comet-lake.html)

2. Alder Lake adaptations done according to:  
[ChrisWayg](https://chriswayg.gitbook.io/opencore-visual-beginners-guide/advanced-topics/using-alder-lake)

Before just copying a config.plist from the internet go through the guids and start from skratch with the sample.plist provided by Dortania by your own.

# Disclaimer

I don't take guarantee for any hack based on that config. You do that on your own risk!

# Thanks/Credits

Since I've followed the two guides mentioned above, thanks to these guys!