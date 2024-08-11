# USB Firmware Updating
- Last Updated 11/08/2026
- Maintained by KrauTech

## Which Method Should I Use?
- KATAPULT! Yes, this is the first point of call when you do a cartographer firmware update. Only if you have issues with this method, should you attempt the others.
- If you ordered a USB flashed cartographer, you use the [USB Katapult Method](USB_Updating.md)
- If you ordered a CAN flashed cartographer, you use the [CANBUS Katapult Method](Canbus_Updating.md)
- If you need to, use DFU Mode [DFU Mode Updating](DFU_Updating.md)

## Whats Required?
- Cartographer Probe
- USB-A to JST-PH Cable
![image-1](https://github.com/user-attachments/assets/1c082c5d-44ff-43e1-b1bf-f70b4249a490)

## Index
- [Canbus - Katapult Updating](Canbus_Updating.md)
- [USB - Katapult Updating](USB_Updating.md)
- [DFU Updating](DFU_Updating.md)
- [STLink Updating](#) - Coming Soon

> [!NOTE]
> Using the scripts below, you may need to use the **Install Prerequisites** option first to make sure everything is configured prior to flashing.

# USB Katapult Updating
## Step 1) Plug Cartographer in via USB

## Step 2) Run Script
- I've created a script that will quickly flash the correct firmware for your device. It simplifies the process so you dont have to worry about which firmware you need to download etc.
- SSH into your host device that cartographer is plugged into.
- Run command `bash <(wget -qO - apdm.tech/cartographer/scripts/beta/firmware_updater.sh)`

## Step 3) Choose Firmware to Flash
> [!NOTE]
> If you plan on using CANBUS, Your CANBUS bitrate (if configured on your host device) should be detected and displayed. You should flash your cartographer with MATCHING bitrate firmware.

You can pick any of these, however to remain detected you should match your bitrare. You can flash USB if youd like to use cartographer via USB however, as bitrate doesnt matter.
![Screenshot 2024-08-11 141443](https://github.com/user-attachments/assets/6ad85f9a-3aba-466b-b483-e2ff23550a71)

# Step 3) Done
![Screenshot 2024-08-11 141507](https://github.com/user-attachments/assets/0fb24c99-d36d-4ce2-9846-48c99d4eb952)
