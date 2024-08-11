# Firmware Updating
- Last Updated 11/08/2026
- Maintained by KrauTech

## Which Method Should I Use?
- KATAPULT! Yes, this is the first point of call when you do a cartographer firmware update. Only if you have issues with this method, should you attempt the others.
- If you ordered a USB flashed cartographer, you use the [USB Katapult Method](#)
- If you ordered a CAN flashed cartographer, you use the [CANBUS Katapult Method](#)

## Whats Required?
- Cartographer Probe
- Ferrous Tweezers
- USB-A to JST-PH Cable (For USB or DFU Mode Flashing)
![image](https://github.com/user-attachments/assets/a81270bc-889d-40b3-a41a-4b7c5886b552)

  or
- Canbus to JST-PH Cable (For Katapult Canbus Flashing)

## Index
- [Canbus - Katapult Updating](#) - Coming Soon
- [USB - Katapult Updating](#d) - Coming Soon
- [DFU Updating](#dfu-updating)
- [STLink Updating](#) - Coming Soon

  
# DFU Updating
## What is DFU 
- This should be seen as a last resort and should only be neccasary when Katapult flashing is unavailable for whatever reason.
- DFU Mode (Device Firmware Upgrade Mode) is STM's bootloader thats apart of the STM32 chip included on cartographer probes. Its next to impossible to make this mode fail. However getting the chip into DFU mode can be a challenge as it requires touching the **boot0** and **reset** pads on the cartographer PCB in the correct manner.

![image](https://github.com/user-attachments/assets/c154160b-941e-4243-aa10-da344a3baadc)


## Whats Required?
- USB-A to JST-PH Cable
- Cartographer Probe
- Ferrous Tweezers
  
## Step 1) Enter DFU Mode
- DFU mode is relatively simple to enter, but harder in practice. With cartographer plugged in via USB, touch the **boot0** (1) and **reset** (2) pads. This will put the device in DFU mode.
- This can be quite fiddly and take some time, so listed below is 2 convenient ways to make this more simple.
> [!WARNING]
> No LEDs will be on when in DFU mode. If the blue LED is lit, the device is in runtime mode and this isnt what we want. Continue touching those pads till it works!

> [!NOTE]
> via SSH use command `lsusb | grep "DFU"` to find if the device is in **DFU Mode**
> ![image](https://github.com/user-attachments/assets/33e4a0b5-a635-4dc3-95a4-bbb866f91882)


### PCB Cover
- Use the new PCB cover made by [MakerMylo](https://www.youtube.com/@makermylo) to clip onto the PCB, it will help align tweezers for touching the pads.
- [PadPusher3000](/STL/PadPusher3000.stl) - PCB Cover

### Solder Boot0 Method
- Soldering a bridge on the **boot0** pads can make this process, much easier. All you need to then do is plug in the USB cable and the probe will enter DFU mode.
- Once youve flashed via DFU mode, remember to de-solder the bridge.

## Step 2) Run Updater Script
- I've created a script that will quickly flash the correct firmware for your device. It simplifies the process so you dont have to worry about which firmware you need to download etc.
- SSH into your host device that cartographer is plugged into and in DFU mode from step #1.
- Run command `bash <(wget -qO - apdm.tech/cartographer/scripts/beta/firmware_updater.sh)`

![image](https://github.com/user-attachments/assets/aabfb78b-6bc5-46a0-8306-c0d31f37d9ff)
![image](https://github.com/user-attachments/assets/1b1754df-2ede-46d4-8982-aea4168be415)
> [!NOTE]
> Choose #1 if faced with the image below to use cartographer via canbus at 1M bitrate.
> 
> Choose #2 if you will be using cartographer via USB

![image](https://github.com/user-attachments/assets/55c93214-0013-46bc-914e-b172774baa33)

Once flashed, you will see the image below. This is a successful flash and youre all finished.
![image](https://github.com/user-attachments/assets/d79d77cc-fef5-4042-9f5f-9a2f04cec547)

## Step 3) Done
- If you flashed for canbus, unplug cartographer and plug in via canbus
- If you flashed for usb, power cycle your device.
