# PCS4
Parental Control System on openwrt

This is the 4th version of an old hobby of mine, to develop an openwrt-based system to control the webaccess for minors.
First of all, it is mainly DNS-based, with some special firewall rules to prevent bypassing.
Second, it is using a database for the storage of the access policies.
The very special (unique ?) feature, so far, is the mapping of policy to the clients device:
It happens automatically, and permanently, during _first_ successful wifi connection to the web, using one of four available SSIDs of the router.
By default, 4 SSIDs available: PCS4 (unfiltered), PCS4_noads, PCS4_kids, PCS4_nosocial.
Of course, multiple devices can share the same SSID/policy.
So, feel free to define different policies for your Kids Tom and Mary, and their SSIDs to use 'PCS4_Tom' or 'PCS4_Mary'.

For configuration, there is a simple UI, which can be reached via 'manage.pcs4/' in a browser, the host of which is connected to the openwrt device. LAN connection preferred.
Credentials: root/PCS4_passwd

This repo does not contain a standard 'package' for openwrt, but the complete directory 'files', which you need to build a custom image (no LuCI) for PCS4.
As a prototype, you also find .config_we826 for my workhorse running openwrt, a WE826 from ZBT.
Thus, you need to set up the standard build environment (recent, TRUNK), and copy 'files' from here into it.
Then do a standard 'make menuconfig', select your hardware platform, and exit. Then do a diff for the .config_we826 from here and your .config.
Redo 'make menuconfig' and select/unselect the differences found.
You can contact me to help for your device type.
Because of multiple reboots, initial flash+auto config of the system might take about 20 min. 
Keep the openwrt-device connected to the web all the time.

Interested parties are invited to provide here .config for other hardware.

Required RAM: 128MB
Flash: 16MB

Initial root password: PCS4_passwd
(Can be changed only via ssh)
Router has LAN-IP 192.168.20.1
IP4 only !

Please, check sources here:
https://github.com/reinerotto/PCS4/releases/tag/v0.9
