# OpenCore EFI for Asus X540UB
OpenCore EFI for Asus X540UB. Based on OpenCore 1.0.1, works with MacOS Sonoma and newer. 

# Specs 
| CPU | Intel i5 7200U |
| --- | --- |
| GPU | Intel HD Graphics 620 1500 MB VRAM |
| dGPU | nVidia GeForce MX110 (disabled) |
| Audio | Realtek ALC256 (alcid=7) |
| RAM | 8 GB 2133 MHz |
| OpenCore Version | OC 1.0.1 Release |
| WiFI & Bluetooth | Intel AC Wireless 3165 |

# Notes
This EFI works best with the laptop model given above. I do not guarantee it will run (**or even boot**) on other laptops from other manufacturers, even with the same GPU/CPU specs. To do so, it would require some adjustments in **config.plist** and **kexts**. Do your own research about **kexts** and do your own USB mapping using USBToolBox [tool](https://github.com/USBToolBox/tool) and [kext](https://github.com/USBToolBox/kext). **Remember, put UTBMap.kext into the kexts folder in EFI!** 

Check your hardware, follow OpenCore guide and make proper adjustments! 

# Supported macOS versions
Tested with macOS Sonoma, currently supports up to Sequoia (15.0). 

# Supported features
|Feature | YES/NO |
| --- | --- |
| Audio | YES |
| WiFi | YES* |
| Bluetooth | YES* |
| iServices | YES* |
| Screen Brightness | YES |
| Brightness keys | YES |
| AirDrop | NO* |
| External Displays | YES |
| Boot chime | YES |
| Touchpad, multitouch | I2C, YES** |
| Sleep | It's a bit tricky.*** |

Basically speaking, everything works, *except AirDrop and other Continuity features (Handoff works). It requires **Airportitlwm.kext**, which works in Sonoma, but not on Sequoia. Also, with this kext, you will lose iServices. Use **itlwm.kext** and **Heliport** instead. The kext is in EFI. 
**Touchpad sometimes stops working, it requires pluging an external mouse in order to fix the problem. I do not know if there is other workaround for this problem.
*** It seems that sleep mode does not work properly when charging. I do not know if there is workaround. 


