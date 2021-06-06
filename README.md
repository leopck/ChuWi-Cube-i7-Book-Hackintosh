# ChuWi-Cube-i7-Book-Hackintosh
Hackintosh with OpenCore, on ChuWi Cube i7 Book

It's currently work in progress.

## Hackintosh Config

- OpenCore 0.6.1
- Mac Catalina 10.15

## Getting Started with Catalina (gibMacOS) on Windows

Youtube tutorial: https://www.youtube.com/watch?v=6KGuINOyHh0

## BIOS
```
Press DEL to enter into BIOS
Chipset -> System Agent (SA) Configuration -> VT-d -> Disabled
Chipset -> System Agent (SA) Configuration -> Graphics Configuration -> DVMT Pre-Allocated -> 128M
Boot -> Bootup NumLock State -> Off
Boot > Fast Boot > Disabled
Security > Secure Boot Menu > Secure Boot > Disabled
Advanced > CPU Configuration > CFG lock > Disabled
Advanced > CPU Configuration > SGX > Disabled
Advanced > USB Configuration > XHCI Hand-off > Enabled
Save & Exit -> Save Changes and Reset

Total list of things:
https://dortania.github.io/OpenCore-Install-Guide/config.plist/skylake.html#intel-bios-settings.
Disable
Fast Boot
Secure Boot
Serial/COM Port
Parallel Port
VT-d (can be enabled if you set DisableIoMapper to YES)
CSM
Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
Intel SGX
Intel Platform Trust
CFG Lock (MSR 0xE2 write protection)(This must be off, if you can't find the option then enable AppleXcpmCfgLock under Kernel -> Quirks. Your hack will not boot with CFG-Lock enabled)
#Enable
VT-x
Above 4G decoding
Hyper-Threading
Execute Disable Bit
EHCI/XHCI Hand-off
OS type: Windows 8.1/10 UEFI Mode
DVMT Pre-Allocated(iGPU Memory): 64MB
SATA Mode: AHCI
```
## What works:
- Intel WiFi (Thanks to @zxystd!)
- Intel Bluetooth ~~(Fixed in latest itlwm)~~ (Broken after I brought the SSDT.aml and DPDT.aml)
- Built-in Display
- Intel Integrated GPU HD515
- micro USB 3.0 Type B
- USB type C
- Audio over Bluetooth
- Foresee 64GB SSD is detected
- Power Button is working
- Volume Rocker button is working for volume
- ChuWi Docking Station (Keyboard + USB 2.0 on the dock) [Worked after integrating the USBxHCIInjection kext]
- Built-in Audio Line out
- Battery Indicator ~~(Right now it detects it as AC powered not battery powered)~~ (Fixed with SSDT.aml and DPDT.aml and SMCBatteryManager.kext)
- Built-in motor for vibration
- The capacitive Home Button on the touchscreen (Windows logo)

## What does not work:
- Touchscreen
- ChuWi Docking Station (Touchpad)
- Built-in Speaker
- Built-in Front Camera
- Built-in Back Camera
- micro SD slot
- Built-in accelerometer for auto-rotation

## Performance
What's being evaluated right now:
```
- Youtube video playback on browser (namely Chrome since it's cross-platform so I can compare with Linux and Windows)
-- AV1
-- VP9
-- H264
- GUI screen tearing on rapid dragging left and right (to detect for screen tearing)
- Hardware acceleration for Video Playback
- GUI smooth-ness during scrolling on large websites
- I/O performance, namely USB gaming mouse
- Multiple apps launching and being used at the same time
- Temperature of device on high load and low load
- Battery performance on high load and low load
- WiFi performance
- BT performance
- Docker performance
- File transfer performance
- Loading multiple tabs on Chrome websites performance
Stress testing mainly.
```
# Release Note
```
## v0.1.2

Updated to OpenCore 0.6.1
Added Intel WiFi AirportItlwm_v1.0_Beta_Catalina.kext.zip v1.1.0 Stable: https://github.com/OpenIntelWireless/itlwm/releases/tag/v1.1.0
Fixed Battery indicator but broke Bluetooth
Intel Bluetooth is broken (regression)

## v0.1.1

Enabled Intel WiFi with HeliPort
Intel Bluetooth working
OpenCore 0.5.8
Catalina 10.15.x
```
