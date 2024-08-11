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
![Screenshot 2024-08-11 144859](https://github.com/user-attachments/assets/b06e734b-d335-4073-9407-be60ec8bd17b)


## Step 3) Choose Firmware to Flash
> [!NOTE]
> If you plan on using CANBUS, Your CANBUS bitrate (if configured on your host device) should be detected and displayed. You should flash your cartographer with MATCHING bitrate firmware.

You can pick any of these, however to remain detected you should match your bitrare. You can flash USB if youd like to use cartographer via USB however, as bitrate doesnt matter.
![Screenshot 2024-08-11 144910](https://github.com/user-attachments/assets/dfb64682-28c7-4a4c-a9fe-67649d70bfff)


# Step 3) Done
![Screenshot 2024-08-11 144929](https://github.com/user-attachments/assets/6920bdbd-2ee7-4947-97f1-c5a623471898)

