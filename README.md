# Hp-elitebook-840-g2-Hackintosh-Opencore


<!-- ABOUT THE PROJECT -->
## About The Project

Here's the complete documentation of my `Hackintosh` journey and all the kexts and drivers that actually worked throughtout this `experimentation process`.

<!-- GETTING STARTED -->
## Getting Started

So getting started we are currently bottlenecked by the version of mac os we can use because apple has reduced support for intel based macs from macos ventura and above so the latest one will be montery which I am currently using.

### Prerequisites

First things first you should get a hang of reading a lot of reddit posts and most of the dortania documentation as well.

Things that dont work:
1. Wifi - unfortunately this laptop has an realtek wifi card hence cant get it to work.
2. Bluetooth - same issue.
3. For some wierd reason the Apple id is signed in but the icloud drive doesn't work.

Things that Work:
1. Ethernet
2. Usb tethering
3. All usb
4. Trackpad - `With all apple trackpad gestures`
5. Inbuilt speakers and Inbuild Microphones.
6. Sleep is also fixed.

### Gathering files
#### First Download the main opencore sample file
[OpenCore sample file or base file](https://github.com/acidanthera/OpenCorePkg/releases)
First Go through the getting started file of the dortania guide 
Still You want to go with my file 
[My File]()
#### Kexts Required:
1. Apple Alc - for sound - [Apple ALC](https://github.com/acidanthera/AppleALC)
2. IntelMausi - for ethernet - [IntelMausi](https://github.com/acidanthera/IntelMausi)
3. Brightness keys - [brightness keys](https://github.com/acidanthera/BrightnessKeys)
4. USB inject all - for all the usb mapping and devices Stock works fine - [USBInjectAll](https://github.com/acidanthera/USBInjectAll)
5. Lilu - [lilu](https://github.com/acidanthera/Lilu)
6. VirtualSMC - for mocking the correct version of mac to the os - [virtualsmc](https://github.com/acidanthera/VirtualSMC)
7. VoodooPS2Controller - for keyboard and trackpad - [voodoops2controller](https://github.com/acidanthera/VoodooPS2Controller)
8. WhateverGreen - for graphics - [WhateverGreen](https://github.com/acidanthera/WhateverGreen)

#### Drivers Required:
1. HfsPlus - [HfsPlus]([https://github.com/acidanthera/HfsPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
2. OpenRuntime - [OpenRuntime](https://github.com/acidanthera/OpenCorePkg/releases)
3. OpenCanopy - For the beautiful opencore gui - [OpenCanopy](https://github.com/acidanthera/OpenCorePkg/releases)
4. ResetNvramEntry 

