## MacOS on Thinkpad T480s. Currently on Ventura 13.5.1

## Please note that this is a working project. It' s stable but not finished yet. 

# My hardware configuration
| Name                | Specifications | Funtional or not |
| ------------------- | -----------------------------------------|---------------|
| Processor           | Intel Core i7-8650U Processor            |Fully|
| Memory              | 16GB-> 8GB on Bourd and 8GB on the slot  |Fully|
| Storage             | WD Blue SN570 500GB                      |Fully|
| Storage  n2         | WDC PC SN520  256GB                      |Fully (installed in WWLAN m.2)| 
| Graphics            | Intel UHD Graphics 620                   |Fully|
| Display             | 14.0" FHD 1920x1080 LED IPS              |Fully|
| Touch Screen        | Raydium Touch Screen                     |Fully (with gestures)|
| Audio               | Realtek Audio ALC257 codec               |Fully |
| Ethernet            | Intel(R) Ethernet Connection (4) I219-V  |Fully|
| WLAN & Bluetooth    | Intel(R) Dual Band Wireless-AC 8265      |Fully 
| MicroSD Card Reader | Generic-SD/MMC CRW USB Device            |Fully|
| Keyboard & Trackpad | TrackPoint and multi-touch touchpad      |Fully
| Fingerprint         | On chip fingerprint reader               |Non-funtional Disabled in Bios|
| Camera              |UVC Camera VendorID_1266 ProductID_46596  |Fully||


|Ports |
|------|
|two USB 3.1 Gen 1|  Fully working|
|two USB 3.1 Type-C Gen 2/Thunderbolt 3|
NoThunderbolt device to test.  When thunderbolt is disabled in Bios, then the second type-C does not work, however it charges the battery
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
2. With my EFI, Thunderbolt should work. However I have desabled it in BIOS, because it saves a lot (I mean A LOT) of power.Since then I lost the use of the second type-c. It still charges the battery but its not working as a port for accessories. As of now, I don' t know if this problem is a usb mapping issue. I am still working on it.
3. If you want to disable Thunderbolt turn off in config.plist  the relevant SSDT and the IOElectrify.kext. 
4. During the formation of this EFI I lost access to some battery settings in the settings app (the panel that lets you put hard disks to sleep etc). I dont know how to bring it back and I would appriciate any help.
5. Use VoltageShift to create a launch service for undervolitng. It helps a lot with power consumption and heat.
6. Use ThinkPad Assistant for all the f-keys to work properly.
7. I think my OC/ACPI folder is a mess. I copied it from other succesfull installations. It creates some minor ACPI errors at boot. It needs to be cleaned up.
8. The ACPI Errors are detailed here: https://www.tonymacx86.com/threads/partially-solved-thinkpad-t480s-macos13-5-1-oc-0-9-4-2-acpi-errors.326911/. It seems that I have corrected the _OINI error (SSDT-INIT) by ammending the SSDT-INIT.aml, but the _TTS error (SSDT-LED and SSDT-SLEEP) goes away only when I disable SSDT-SLEEP in config.plist. Up to now I don' t see any differences in the way the T480S works. Further testing is necessary and then I will merge the differences in a new release.  


## Screenshot   


![Screenshot 2023-08-19 at 12 36 57 PM](https://github.com/Hasodikis/T480S-Hackintosh/assets/61179177/baac1f7d-6028-4f55-86c4-78bdbe02c721)

## With Second (low power) EFI
With my second EFI I get the best results to date with 
1. Thunderbolt off in Bios and with the relevant Thunderbolt settings also disabled.
2. WWlan and card reader disabled in BIOS,
but with everything else on, including two nvme drives and the touchscreen
3. With voltageshift undervolting (with CPU turbo Disabled). For my laptop i am stable with: sudo ./voltageshift buildlaunchd  -80 -80 -50 0 0 0 0 0 0 1 0 0 1 10 . Test your laptop first before you bulid a launch service
![Screenshot 2023-08-23 at 15 54 30](https://github.com/Hasodikis/T480S-Hackintosh/assets/61179177/1576e859-c198-4ca9-bb0e-8bac7beb0385)

