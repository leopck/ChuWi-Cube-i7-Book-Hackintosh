# Documention log for all the notes and links that I've took all the materials from

## Intel WiFi

In this github issue, they provide a link and steps to start the Intel WiFi and place the SSID and PWD into the NVRAM
https://github.com/daliansky/XiaoMi-Pro-Hackintosh/issues/330

To download the kext,
https://ww.lanzous.com/b01bfh3zi
password: gejq

That is actually from AppleIntelWiFi kext and an installation script to help load the kext properly. It's pretty good.

I loaded the SSID and PWD using NVRAM method via Hackintool.

Use scenario 1: Connect only 1 wifi:
Use the NVRAM tab in the Hackintool tool, click the "+" icon below, add two values ​​WiFi-SSID and WiFi-PW fill in the wireless network name and password respectively. Restart after executing install.command to realize automatic connection.

Use scenario 2: Connect a limited number of wifi, select different OC configuration files to start through the startup menu:
Add the following configuration to each OC configuration file, add WiFi-SSID and WiFi-PW to ADD to correspond to the wireless network name and password, and add WiFi-SSID and WiFi-PW to Block. Add or delete by searching boot-args.
NVRAM

Add

7C436110-AB2A-4BBB-A880-FE41995C9F82

WiFi-SSID
My-WiFi-SSID
WiFi-PW
MyPassword
boot-args
-cdfon -igfxmlr


Block

7C436110-AB2A-4BBB-A880-FE41995C9F82

boot-args
WiFi-SSID
WiFi-PW
