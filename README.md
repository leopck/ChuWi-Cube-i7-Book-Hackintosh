# ChuWi-Cube-i7-Book-Hackintosh
Hackintosh with OpenCore, on ChuWi Cube i7 Book

It's currently work in progress.

## What works:
- Intel WiFi (Thanks to @zxystd!)
- Intel Bluetooth (After adding the Intel WiFi, audio over BT became stuttery https://github.com/zxystd/itlwm/issues/85)
- Display
- Intel Integrated GPU HD515
- micro USB 3.0 Type B
- USB type C
- Audio over Bluetooth
- Foresee 64GB SSD is detected
- Power Button is working
- Volume Rocker button is working for volume
- ChuWi Docking Station (Keyboard + USB 2.0 on the dock) [Worked after integrating the USBxHCIInjection kext]
- Built-in Audio Line out

## What does not work:
- Touchscreen
- ChuWi Docking Station (Touchpad)
- Built-in Speaker
- Power management for battery detection (Right now it detects it as AC powered not battery powered)
- Built-in Front Camera
- Built-in Back Camera
- The capacitive Home Button on the touchscreen (Windows logo)
- micro SD slot
- Built-in motor for vibration
- Built-in accelerometer for auto-rotation

## Performance
What's being evaluated right now:
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
