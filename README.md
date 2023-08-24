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

#### Kexts Required:
1. [Apple ALC](https://github.com/acidanthera/AppleALC) - for sound
2. [IntelMausi](https://github.com/acidanthera/IntelMausi) - for ethernet
3. [Brightness keys](https://github.com/acidanthera/BrightnessKeys)
4. [USBInjectAll](https://github.com/acidanthera/USBInjectAll) - for all the usb mapping and devices Stock works fine
5. [Lilu](https://github.com/acidanthera/Lilu)
6. [Virtualsmc](https://github.com/acidanthera/VirtualSMC) - for spoofing the device
7. [Voodoops2controller](https://github.com/acidanthera/VoodooPS2Controller) - for keyboard and mouse controls
8. [WhateverGreen](https://github.com/acidanthera/WhateverGreen) - for graphics

#### Drivers Required:
1. [HfsPlus](https://github.com/acidanthera/OcBinaryData/blob/master/Drivers/HfsPlus.efi)
2. [OpenRuntime](https://github.com/acidanthera/OpenCorePkg/releases)
3. [OpenCanopy](https://github.com/acidanthera/OpenCorePkg/releases)
4. ResetNvramEntry
   
#### SSDT
1. [SSDT-EC_LAPTOP](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-EC-LAPTOP.aml)
2. [SSDT-PLUG-DRTNIA](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-PLUG-DRTNIA.aml)
3. [SSDT-XOSI](https://github.com/dortania/Getting-Started-With-ACPI/blob/master/extra-files/compiled/SSDT-XOSI.aml)
4. [SSDT-OLAEC](https://github.com/adi2003prasad/Hp-elitebook-840-g2-Hackintosh/blob/main/SSDT-OLAEC.aml)

### Making the installation USB
- Pretty simple and to the point guides are already availble just make sure to have all the files that i have talked above and make the changes permanent with the help of proper tree
- [GUIDE to usb installer guide youtube](https://www.youtube.com/watch?v=wC8Qi5SxeNk)
- [Or the real one from Dortania](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/windows-install.html#making-the-installer)
- After this you should just try to merge the files I have talked above and just add them and use the below guide to use proper tree to permanently save the changes
- [Proper tree guide](https://dortania.github.io/OpenCore-Install-Guide/config.plist/#creating-your-config-plist)

### After the install the config.plist file should look like [this file](https://github.com/adi2003prasad/Hp-elitebook-840-g2-Hackintosh/blob/main/config.plist)

### Setting up the BIOS
GOT FROM AN ALREADY UP REPOSITORY [CHECK IT OUT](https://github.com/AktasC/Hackintosh-Elitebook-Broadwell/blob/master/one.md)

- [Enter BIOS menu](#ø---enter-bios-menu)
- **Advanced tab**
- Boot Options
  - Startup Menu Delay (Sec.) : **05**
  - [ ] Fast Boot
  - [x] USB Device boot
  - [x] PCIe/M.2 SSD boot
  - Boot Mode : UEFI Hybrid (With CSM)
- Device Configurations
  - [x] USB legacy support
  - [x] USB 3.0 (HXCI)
  - Video Memory Size : **64MB**
  - [ ] Wake on USB
  - [ ] Virtualization (VTx / VTd)
  - [ ] Trusted Execution Technology (TXT)
  - [ ] Hybrid Graphics
  - [x] Deep sleep
- Built-in Device Options
  - Wake on LAN : **Disable**
  - [x] Wake unit from sleep when lid is opened
  - [x] Power on unit when lid is opened
  - [x] PCIe/M.2 SSD
- Port Options
  - [x] USB port
  - [ ] Smart Card
- **Main Tab**
- Save Changes and Exit
- Poweroff your laptop.

### Congrats!! you have done everything right , now just boot to the usb drive you will see the opencore bootloader then just follow the installation steps.
[Installation steps](https://dortania.github.io/OpenCore-Install-Guide/installation/installation-process.html#booting-the-opencore-usb)
or just continue from the above youtube guide or any other guide on youtube

## `IMPORTANT`
### Dont miss this step 
On booting after the install you may not be able to have sound and microphone 
Follow this guide [You will have to fix it through ssdt](https://dortania.github.io/Getting-Started-With-ACPI/Universal/irq.html)

Layout-id 4 works for this laptop 
Boot argument should have this - alcid=4

You can also see it in the config.plist file i have uploaded above

### For fixing the sleep 
- [Hibernationfixup](https://github.com/acidanthera/HibernationFixup/releases/tag/1.4.9)

- Download this kext and add it to the efi folder and update the config.plist as necessary for both the steps.

- Change your hibernation mode (from usually 0) to 3, which is the standard sleep mode on laptops referred to as „safe sleep“, with this command 
```sh
sudo pmset -a hibernatemode 3
```
## Thats it Now enjoy the hackintosh life
If any other thing shows up than use google to your help.
