# CANBUS Firmware Updating
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
- Canbus to JST-PH Cable (For Katapult Canbus Flashing)

## Index
- [Canbus - Katapult Updating](Canbus_Updating.md)
- [USB - Katapult Updating](USB_Updating.md)
- [DFU Updating](DFU_Updating.md)
- [STLink Updating](#) - Coming Soon

> [!NOTE]
> Using the scripts below, you may need to use the **Install Prerequisites** option first to make sure everything is configured prior to flashing.

# CANBus Katapult Updating
## Step 1) Plug Cartographer in via CANBUS

## Step 2) Run Script
- I've created a script that will quickly flash the correct firmware for your device. It simplifies the process so you dont have to worry about which firmware you need to download etc.
- SSH into your host device that cartographer is plugged into.
- Run command `bash <(wget -qO - apdm.tech/cartographer/scripts/beta/firmware_updater.sh)`

## Step 3) Get Your UUID
This method requires prior knowledge of your **CANBUS UUID**. 

This should have been supplied to you in your hardware box if purchased (insert date).

If you do not have your UUID. Visit (HERE) to get it.

The script will detect your UUID if your UUID is inside your **printer.cfg** somewhere under `[scanner]` if it doesnt detect, you can manually enter it.

![Screenshot 2024-08-11 141421](https://github.com/user-attachments/assets/612dec98-50ab-4ab6-9d61-bc465a7cf411)

## Step 2) Choose Firmware to Flash
> [!NOTE]
> Your CANBUS bitrare (if configured on your host device) should be detected and displayed. You should flash your cartographer with MATCHING bitrate firmware.

You can pick any of these, however to remain detected you should match your bitrare. You can flash USB if youd like to use cartographer via USB however, as bitrate doesnt matter.
![Screenshot 2024-08-11 141443](https://github.com/user-attachments/assets/6ad85f9a-3aba-466b-b483-e2ff23550a71)

# Step 3) Done
![Screenshot 2024-08-11 141507](https://github.com/user-attachments/assets/0fb24c99-d36d-4ce2-9846-48c99d4eb952)
