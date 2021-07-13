# ASUS Republic Of Gamers MAXIMUS VIII HERO – Hackintosh

## System Details

| Model            | ASUS ROG MAXIMUS VIII HERO                                 |
| :--------------- | :--------------------------------------------------------- |
| CPU              | Intel® Core(TM) i5-6500 CPU @ 3.20GHz QuadCore SkyLake-S   |
| iGPU             | Intel® UHD Graphics 530 (FHD)                              |
| dGPU             | ASUS ROG STRIX RX460 (4GB)                                 |
| RAM              | Corsair Vengeance LPX CMK16GX4M2A2800C16 2x8GB DDR4 2800MHz|
| SSD              | Asgard AN256NVMe-M.2/80                                    |
| HDD              | WDC WD10EZEX-08WN4A0 (1 TB, 7200 RPM, SATA-III)            |
| Ethernet         | Intel® Ethernet Connection I219-V                          |
| WiFi             | TP-Link TL-WN725N N150 V3                                  |
| Audio            | Intel® Sunrise Point PCH @ Realtek ALC1150 [alcid=11]      |
| Display          | HP 24es (HDMI) [23.8" IPS LCD] (3CM6330635)                |
| BIOS Version     | 3802 (2.17.1246)                                           |
| OpenCore Version | 0.7.1                                                      |

## What's not working:

- AirDrop && Handoff. It's need a native module


## BIOS Setup:

1. Open BIOS
2. Exit --> Load Optimized Defaults                                                                                     
3. Advanced \ CPU Configuration \ Intel Virtualisation Technology … Enabled
4. Advanced \ Platform Misc Configuration … Disable all
5. Advanced \ System Agent (SA) Configuration \ VT-d Enabled
6. Advanced \ System Agent (SA) Configuration \ Graphics Configuration \ Primary Display … Auto
7. Advanced \ System Agent (SA) Configuration \ Graphics Configuration \ iGPU Multi-Monitor … Enabled
8. Advanced \ System Agent (SA) Configuration \ Graphics Configuration \ RC6(Render Standby) … Enabled
9. Advanced \ System Agent (SA) Configuration \ Graphics Configuration \ DVMT Pre-Allocated … 64M
10. Advanced \ PCH Storage Configuration \ Hyper kit1 Mode … Disabled
11. Advanced \ PCH Storage Configuration \ SATA Controller(s) … Enabled
12. Advanced \ PCH Storage Configuration \ SATA Mode Selection … AHCI
13. Advanced \ PCH Storage Configuration \ Aggressive LPM Support … Disabled
14. Advanced \ PCH Configuration \ IOAPIC 24-119 Entries … Enabled
15. Advanced \ Thunderbolt(TM) Configuration \ … Disable all
16. Boot \ Fast Boot … Disabled
17. Boot \ Boot Logo Display … Auto
18. Boot \ Boot up NumLock State … Enabled
19. Boot \ Above 4G Decoding … Enabled
20. Boot \ Interrupt 19 Capture … Enabled
21. Boot \ CSM (Compatibility Module) \ Launch CSM … Disabled
22. Boot \ Secure Boot \ OS Type … Other OS
23. Exit -> Save Changes & Reset


## Installation Steps

1. Download macOS Big Sur image for Intel CPUs: [Link](https://rutracker.org/forum/viewtopic.php?t=5928524)
2. Write macOS image to a USB drive using R-Drive Image (inside ISO)
3. Write CLOVER and Big Sur Partition.
4. After writing, remove `EFI/clover` and insert `EFI/OC` from this repo
4. Generate a new SMBIOS with [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS)
5. Update to the `config.plist` in the USB drive's `EFI/OC` folder with new SMBIOS
6. Boot with USB drive
7. Follow the installer instructions

macOS Big Sur 11.4 (20F71) worked with this release
