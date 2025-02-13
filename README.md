# the-2am-guide-to-openwrt
This guide describes how to setup a pre-configured OpenWRT-Router to act as Router, WiFi-Accesspoint and Firewall.

## Introduction
### What the hell is OpenWRT?
In every router, there is a chip running **linux** and a custom interface of whatever manufacturer, AVM (Fritz!Box), Netgear, Asus, TP-Link, to just name a few of thousands.
**OpenWRT** is a completlty **open source firmware** and user interface for consumer routers and even professional grade devices that can do more than all of those together, because it can basically do whatever you want. If that's a good idea? That's something you have to decide.
Because Linux isn't free. You have to pay attention.

### Preconfiguration
- TP-Link Archer C7 v2 has been flashed with [OpenWRT](https://openwrt.org/) with the latest stable image  [/23.05.5/targets/ath79/generic/tplink_archer-c7-v2-squashfs-factory-eu.bin](https://downloads.openwrt.org/releases/23.05.5/targets/ath79/generic/openwrt-23.05.5-ath79-generic-tplink_archer-c7-v2-squashfs-factory-eu.bin) and upgraded to the latest development version [24.10.0](https://downloads.openwrt.org/releases/24.10.0/targets/ath79/generic/openwrt-24.10.0-ath79-generic-tplink_archer-c7-v2-squashfs-sysupgrade.bin)) (follow [this guide](https://openwrt.org/toh/tp-link/archer_c7) for more infos but it doesn't really matter)
- password for the root user has been set
- Timezone has been set to Europe/Berlin
- Hostname of the devices + Description etc have been set
- The Package [luci-app-statistics](https://openwrt.org/docs/guide-user/luci/luci_app_statistics) has been installed
- WiFi Networks BLAN-2.4 and BLAN-5 have been setup, Security set to WPA2/3 mixed mode.
- honestly too much other small shit, if you want to know 100% what, get the base config and compare my config to it :D

## Physical Setup
### Connecting the Device
![TP-Link ArcherC7-v2](https://github.com/user-attachments/assets/5f21a207-6c9f-489b-9810-d0867bdd78c4)
4 Step Plan:
- Connect the Blue Port  (labeled "Internet") with a Router or a Modem, for example a Fritz!Box
- Connect the Router to the Power
- It really doesn't matter in which order you do it.
- Done and bamboozled, it was only a 2 Step plan!

The yellow Ports are LAN-Ports where you can attach devices to the router (and asign individual VLANs to each of them so you can have "fun" (to me it sadly is) to put your IoT Devices into an individual Network, because why not.

In theory you could connect a Soundcard (like the one from ASUS you now have) to the USB Port of the Router and use it to play music via the Router, because welcome to OpenWRT. This box is full of limitless potential like yourself ;)

### Resetting the Device
Just hold the reset button lol.

It can be possible to "really" brick this router, mostly by installing to much packages (which I did earlier lol), but it's always recoverable. This might involve either setting up a TFTP Server or soldering some wires to a chip and flashing it. I'd strongly recommend the first route as documented [here](https://openwrt.org/toh/tp-link/archer_c7#installation_or_restore_with_tftp).

## Connecting to the WiFi
I set up 2 WiFi Networks named BLAN-2.4 and BLAN-5. For Credentials, check the Bitwarden Send.

## Configuring the Router
### LuCI - OpenWrt Configuration Interface
To access either try [http://emmanzipiert](http://emmanzipiert.lan/) or [http://192.168.1.1/](http://192.168.1.1/).
Credentials are also in the Bitwarden Send.

### Change the WiFi Name
To change the Name of the WiFi Radios, do the following:
![image](https://github.com/user-attachments/assets/dc2e24ae-bfde-4694-9be3-38d228c77d45)
1. Go to **Network**
2. **Wireless**
3. **Edit** (for the 5 GHz Radio)
4. **Edit** (for the 2.4 GHz Radio)

![image](https://github.com/user-attachments/assets/8a64bf41-1e71-4da4-8463-8f5d8f173bb5)

In the Tab **General Setup (1)** you can select a different **(E)SSID (2)** (Service Set Identifier, the Name of your WiFi Network).

![image](https://github.com/user-attachments/assets/7a477453-1711-4d11-8060-abd2aa3d7765)
Go to **Wireless Security (1)** to set a new **PSK (2)** (Pre-Shared Key, the password to your WiFi) or press the **(3)** Button to reveal the PSK. 






### Changing the Hostname of the device
Currently the [Hostname](https://en.wikipedia.org/wiki/Hostname) of the device, the "Adress" in the Network is emmanzipiert.lan. The default is openwrt.lan.
To change that do the following:
![image](https://github.com/user-attachments/assets/65257e8d-9997-42f2-ac9e-ab05a7a65765)
1. Go to System
2. System
3. Enter the desired hostname and press save

If you accessed the router via the link http://emanzipiert.lan, you have to now go to http://whatevernameyouset.lan, because you changed the adress of the device. If you used the IP, nothing will change.

Why use hostnames? Servers can change, but hostnames act as an alias, which you can use to swap the server behind the scenes and your app still will work.


## To Write
- Reset von OWRT
- Werkszustand
- WLAN Settings + Renaming
- Firewall, VLAN anteasern
- upgrade/downgrade firmware (add link)
- log file
- changes and saves
- how to create a backup
- stats

