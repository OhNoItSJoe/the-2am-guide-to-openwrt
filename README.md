# the-2am-guide-to-openwrt
This guide describes how to setup a pre-configured OpenWRT-Router to act as Router, WiFi-Accesspoint and Firewall.

## What the hell is OpenWRT?
In every router, there is a chip running linux and a custom interface of whatever manufacturer, AVM (Fritz!Box), Netgear, Asus, TP-Link, to just name a few of thousands.
OpenWRT is a completlty open source firmware and user interface that can do more than all of those together, because it can basically do whatever you want. If that's a good idea? That's something you have to decide.
Because Linux isn't free. You have to pay attention.

## Preconfiguration
- TP-Link Archer C7 v2 has been flashed with [OpenWRT](https://openwrt.org/) (follow [this guide](https://openwrt.org/toh/tp-link/archer_c7) for more infos but it doesn't really matter)
- password for the root user has been set
- Timezone has been set to Europe/Berlin
- Hostname of the devices + Description etc have been set
- The Package [luci-app-statistics](https://openwrt.org/docs/guide-user/luci/luci_app_statistics) has been installed

## Connecting the Device
![TP-Link ArcherC7-v2](https://github.com/user-attachments/assets/5f21a207-6c9f-489b-9810-d0867bdd78c4)
4 Step Plan:
- Connect the Blue Port  (labeled "Internet") with a Router or a Modem, for example a Fritz!Box
- Connect the Router to the Power
- It really doesn't matter in which order you do it.
- Done and bamboozled, it was only a 2 Step plan!



## COntent
- Reset von OWRT
- Werkszustand
- WLAN Settings + Renaming
- Firewall, VLAN anteasern
- 

