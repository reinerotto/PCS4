# PCS4
Parental Control System on openwrt

This is the 4th version of an old hobby of mine, to develop an openwrt-based system to control the webaccess for minors.
First of all, it is mainly DNS-based, with some special firewall rules to prevent bypassing.
Second, it is using a database for the storage of the access policies.
The very special feature, so far, is the mapping of policy to the clients device:
It happens automatically, and permanently, during _first_ successful wifi connection to the web, using one of four available SSIDs of the router.
By default, 4 SSIDs available: PCS4 (unfiltered), PCS4_noads, PCS4_kids, PCS4_nosocial.
Of course, multiple devices can share the same SSID/policy.
So, feel free to define different policies for your Kids Tom and Mary, and their SSIDs to use 'PCS4_Tom' or 'PCS4_Mary'.

For configuration, there is a simple UI, which can be reached via 'manage.pcs4/' in a browser, the host of which is connected to the openwrt device. LAN connection preferred.
Credentials: manager/PCS4_passwd

This repo does not contain a standard 'package' for openwrt, but the complete directory 'files', which you need to build a custom image (no LuCI) for PCS4.
As a prototype, you also find .config for my workhorse running openwrt, a WE826 from ZBT.
Interested parties are invited to provide .config for other hardware.
To build the image, you need to use current openwrt (TRUNK). May be, version 20.x.x will allow a stable base.

Required RAM: 128MB
Flash: 16MB


