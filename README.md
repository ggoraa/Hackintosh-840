![](https://img.shields.io/badge/Working-yes-green)
![](https://img.shields.io/badge/Latest%20supported-Monterey%2011.2-purple)
![](https://img.shields.io/github/issues-raw/GGorAA/Hackintosh-840?color=yellow)
![](https://img.shields.io/github/issues-pr/GGorAA/Hackintosh-840)

# Hackintosh 840
This repo contains EFI configuration, kext and many more for HP ElteBook 840 G3 laptop. This EFI might be compatible with other laptops from EliteBook 840 lineup(not tested).

## Contents

  - [Working components](#working-components)
  - [Known bugs](#known-bugs)
  - [Installation](#installation)
     - [Step one: create bootable USB of macOS](#step-one-create-bootable-usb-of-macos)
     - [Step two: install Hackintosh](#step-two-install-hackintosh)
     - [Step three: postinstall](#step-three-postinstall)
        - [Step three.one: fix display colors](#step-threeone-fix-display-colors)
        - [Step three.two: install serial number and UUID to fix Apple ID, iCloud, App Store, iMessage and more](#step-threetwo-install-serial-number-and-uuid-to-fix-apple-id-icloud-app-store-imessage-and-more)
        - [Step three.three: make boot look nice](#step-threethree-make-boot-look-nice)
     - [Step four: enjoy!](#step-four-enjoy)

## Working components

| Component | Component model | State |
| --- | --- | --- |
| Wifi | Intel Wireless AC 8260 | Buggy(sometimes work, sometimes don't) |
| Bluetooth | Intel Wireless AC 8260 | Working |
| Graphics | Intel HD Graphics 520 | Working |
| Sound | Bang&Olufsen | Working|
| Battery | N\A(Stock) | Working |
| Trackpad | Synaptics | Working(gestures too) |

## Known bugs

 - Apple TV/TV+ doesn't work
 - Wi-Fi analyzer shows wrong info about a network(like «Hidden network», even when it is not hidden)
 - The "Charger connected" sound plays only in headphones
 
 ## Installation
 ### Step one: create bootable USB of macOS
 
 You need a flash drive with size of 16 GB. Then make a bootable USB of macOS on another Mac machine. Borrow a real Mac, or use a Hackintosh.
 
 ### Step two: install Hackintosh
 
 Then, you need to install macOS on your EliteBook 840 G3. Just run macOS Installation, clear drive with Disk Utility, and install macOS using Install macOS option.
 
 
### Step three: postinstall

Download [Hackintool](https://github.com/headkaze/hackintool/releases), and place the downloaded app in `Applications`.

### Step three.one: fix display colors

Go to Apple > System Preferences > Display > Color, then select P3(display). This fixes blue color represented like purple color.

### Step three.two: install serial number and UUID to fix Apple ID, iCloud, App Store, iMessage and more

First, open Hackintool from Launchpad or Spotlight. Go to `System` tab, and in that tab, click `Serial Generator`. At the bottom, select `MacBookPro13,1`, and click at the refresh icon. Now, mount your EFI. Go to `Disks` tab, right-click the EFI partition, and click `Mount`. Then, right-click again, and click `Open`.

Next, navigate to `EFI > OC` and open  `config.plist` in Xcode. Now, expand `Plaforminfo`, and in it `Generic`. In row `SystemProductName` write `MacBookPro13,1`, in row `SystemSerialNumber` paste the Serial Number from Hackintool. The same applies to `SystemUUID`: paste there SmUUID from Hackintool.

### Step three.three: make boot look nice

If you haven't closed your `config.plist` in Xcode, good. If closed, open it again. In the menu bar select `Find`, and then `Find in Workspace` or press Shift+Command+F. Now, type in search box `-v`, and click first result. (If nothing appears, proceed to next step.) Then, scroll a little bit down to reveal the selected result. Now, select the text box and delect `-v` part from it (if you're curious what does it do, basically it replaces normal graphical boot with console-like boot. Typically used when debugging).

Restart your Hackintosh to apply all changes made now.

### Step four: enjoy!

Now you can enjoy your fresh installation of macOS!

## If you want to contribute, feel free to create issues and pull requests! I always appreciate any help!

