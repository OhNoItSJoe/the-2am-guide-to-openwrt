# the-2am-guide-to-openwrt
This guide describes how to setup a pre-configured OpenWRT-Router to act as Router, WiFi-Accesspoint and Firewall.

## Introduction
### What the hell is OpenWRT?
In every router, there is a chip running linux and a custom interface of whatever manufacturer, AVM (Fritz!Box), Netgear, Asus, TP-Link, to just name a few of thousands.
OpenWRT is a completlty open source firmware and user interface that can do more than all of those together, because it can basically do whatever you want. If that's a good idea? That's something you have to decide.
Because Linux isn't free. You have to pay attention.

### Preconfiguration
- TP-Link Archer C7 v2 has been flashed with [OpenWRT](https://openwrt.org/) with the latest stable image  [/23.05.5/targets/ath79/generic/tplink_archer-c7-v2-squashfs-factory-eu.bin](https://downloads.openwrt.org/releases/23.05.5/targets/ath79/generic/openwrt-23.05.5-ath79-generic-tplink_archer-c7-v2-squashfs-factory-eu.bin) and upgraded to the latest development version [24.10.0](https://downloads.openwrt.org/releases/24.10.0/targets/ath79/generic/openwrt-24.10.0-ath79-generic-tplink_archer-c7-v2-squashfs-sysupgrade.bin)) (follow [this guide](https://openwrt.org/toh/tp-link/archer_c7) for more infos but it doesn't really matter)
- password for the root user has been set
- Timezone has been set to Europe/Berlin
- Hostname of the devices + Description etc have been set
- The Package [luci-app-statistics](https://openwrt.org/docs/guide-user/luci/luci_app_statistics) has been installed
- WiFi Networks BLAN-2.4 and BLAN-5 have been setup, Security set to WPA2/3 mixed mode.

## Physical Setup
### Connecting the Device
![TP-Link ArcherC7-v2](https://github.com/user-attachments/assets/5f21a207-6c9f-489b-9810-d0867bdd78c4)
4 Step Plan:
- Connect the Blue Port  (labeled "Internet") with a Router or a Modem, for example a Fritz!Box
- Connect the Router to the Power
- It really doesn't matter in which order you do it.
- Done and bamboozled, it was only a 2 Step plan!

The yellow Ports are LAN-Ports where you can attach devices to the router (and asign individual VLANs to each of them so you can have "fun" (to me it sadly is) to put your IoT Devices into an individual Network, because why not.

In theory you could connect a Soundcard (like the one from ASUS) and use it to play music via the Router, because welcome to OpenWRT. This box is full of limitless potential like yourself ;)

### Resetting the Device
Just hold the reset button lol.

It can be possible to "really" brick this router, mostly by installing to much packages (which I did earlier lol), but it's always recoverable. This might involve either setting up a TFTP Server or soldering some wires to a chip and flashing it. I'd strongly recommend the first route as documented [here](https://openwrt.org/toh/tp-link/archer_c7#installation_or_restore_with_tftp).

## Connecting to the WiFi
I set up 2 WiFi Networks named BLAN-2.4 and BLAN-5. For Credentials, check the Bitwarden Send.

## Configuring the Router
### LuCI - OpenWrt Configuration Interface
To access either try [https://openwrt](http://openwrt.lan/) or [http://192.168.1.1/](http://192.168.1.1/).
Credentials are also in the Bitwarden Send.



## COntent
- Reset von OWRT
- Werkszustand
- WLAN Settings + Renaming
- Firewall, VLAN anteasern
- upgrade/downgrade firmware (add link)
- log file
- changes and saves

