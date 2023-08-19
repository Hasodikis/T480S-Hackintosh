## MacOS on Thinkpad T480s. Currently on Ventura 13.5.1

## Please note that this is a working project. I just got the laptop a few days ago. 

# My hardware configuration
| Name                | Specifications | Funtional or not |
| ------------------- | -----------------------------------------|---------------|
| Processor           | Intel Core i7-8650U Processor            |Fully|
| Memory              | 16GB-> 8GB on Bourd and 8GB on the slot  |Fully|
| Storage             | WD Blue SN570 500GB                      |Fully|
|                     | WDC PC SN520  256GB                      |Fully (installed in WWLAN m.2)| 
| Graphics            | Intel UHD Graphics 620                   |Fully with WhateverGreen.kext and properties inject|
| Display             | 14.0" FHD 1920x1080 LED IPS              |Fully|
| Touch Screen        | Raydium Touch Screen                     |Fully (with gestures)|
| Audio               | Realtek Audio ALC257 codec               |Fully with AppleALC.kext and layout-id 11|
| Ethernet            | Intel(R) Ethernet Connection (4) I219-V  |Fully with IntelMausi.kext|
| WLAN & Bluetooth    | Intel(R) Dual Band Wireless-AC 8265      |Fully 
| MicroSD Card Reader | Generic-SD/MMC CRW USB Device            |Fully|
| Keyboard & Trackpad | TrackPoint and multi-touch touchpad      |Fully
| Fingerprint         | On chip fingerprint reader               |Non-funtional|
| Camera              |UVC Camera VendorID_1266 ProductID_46596  |Fully||


|Ports |
|------|
|two USB 3.1 Gen 1|  Fully working|
|two USB 3.1 Type-C Gen 2/Thunderbolt 3|NoThunderbolt device to test.  When thunderbolt is disbaled in Bios, then the second type-C does not work, however it charges the battery|
|HDMI 1.4b|
|Ethernet extension connector|
|headphone/microphone jack|
|MircoSD card reader|

# BIOS
1. Config - USB - USB UEFI BIOS Support - Enabled
2. Keyboard/Mouse TrackPoint - Enabled
Trackpad - Enabled
F1-F12 as Primary Function - Disabled
Fn Sticky Key - Disabled
F1-F12 as Primary Function - Disabled
3. Display
Total Graphics Memory - 512MB
4. Power Lid Sensor - Enabled
5. Thunderbolt(TM) 3
Thunderbolt BIOS Assist Mode - Disabled
Security Level - No Security
6. Security
Security Chip
Security Chip - Disabled
7. Virtualization
Intel (R) Virtualization Technoloty - Enabled
Intel (R) VT-d Feature - Enabled
8. I/O Port Access
Ethernet LAN - Enabled
Wireless LAN - Enabled
Wireless WAN - Enabled if you have the module, Disabled otherwise
Bluetooth - Enabled
Memory Card Slot - Enabled
Integrated Camera - Enabled
Microphone - Enabled
Fingerprint Reader - Disabled (to save power)
Thunderbolt (TM) 3 - Enabled (I have disabled it since I don't have a Thunderbolt device and it SAVES A LOT OF Power.
9. Computrace
Current Setting - Disabled
10. Secure Boot Configuration
Secure Boot - Disabled
11. Intel (R) SGX
Intel (R) SGX Control - Disabled
12. Device Guard
Device Guard - Disabled

## NOTES
1. My EFI is heavily biased towards low energy consumption. 
2. With my EFI Thunderbolt should work. However I have desabled it since it saves a lot (I mean A LOT) of power. However since then I lost the use of the second type-c. It still charges the battery but it not working as a port for accessories. As of now, I don' t know if this problem is a usb map problem. I am still working on it.
3. If you want to disable Thunderbolt turn of the the relevant SSDT and the IOElectrify.kext. 
4. During the formation of this EFI I lost access to  some battery settings in the settings app (the panel that lets you put hard disks to sleep etc). I dont know how to bring it back and I would appriciate any help).
5. Use VoltageShift to create a lauch service. It helps a lot wit power consumption and heat.
6. Use ThinkPad Assistant for all the fkeys to work properly. 


## Screenshots    


![Screenshot 2023-08-19 at 12 36 57 PM](https://github.com/Hasodikis/T480S-Hackintosh/assets/61179177/baac1f7d-6028-4f55-86c4-78bdbe02c721)

