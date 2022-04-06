# Firmware_Upgrade 

```diff
-For DI-2108, DI-2108P, DI-4108 and DI-4208 without standalone capability,  
-please find the firmware in firmware in the folder of NonStandAloneDevices
```

1. Download and install the flash program for Windows from https://www.ti.com/tool/LMFLASHPROGRAMMER

2. Remove the USB cable from your device and PC, and remove power supply to the device if it gets power from external power supply

3. Plug the USB cable to PC (the other end should NOT connect to the device at this point)

4. Force the device into firmware upgrade mode...
   - For device without external power supply, plug in the USB cable to the device while holding the button down. The LED should be solid WHITE, if not go back to step 2.
   - For device with external power supply, such as DI-4718B and DI-4730, push and hold the button while powering up the device.  The LED should be solid WHITE, if so, connect the USB cable to the device, if not go back to step 2. 

5. Start LMFlash.exe program installed in step 1. The startup page will be exactly as below <br/>
![alt text](https://www.dataq.com/resources/repository/lmflash1.png)

6. Choose the Program Tab. Navigate to your download directory, click on the appropriate bin file for your device<br/>
![alt text](https://www.dataq.com/resources/repository/lmflash2.png)

7. Press the Program Button at the lower left corner. When it finishes, the device should be FLASHING Green (Windaq compatible, or LibUSB) or Yellow (Virtual COM port, or CDC), based on the USB mode enabled. If the device doesn't flash any of the above color, please make sure you use the matching firmware for your device and go back to step 2)

8. Use Windaq softwar to confirm a channel is working as designed. If not, please make sure you use the matching firmware for your device and go back to step 2)
   - If a non-standalone device uses a standalone firmware, it will hang in looking for the real time clock and the LED is solid white
   - If A device use the firmware for B device, it will not have the correct gain/scale, or WinDaq won't run at all.
   
9. Starting firmware rev 1.35, if you use the original Windaq file, you can use a file hex editor such as https://mh-nexus.de/en/hxd/， to look into the area starting from offset of 0x3F2 to find out the reason the file was closed, and offset of 0x43A to find out the reason the file was started, see example below <br/>
![alt text](https://www.dataq.com/resources/repository/wdq_header.png)

Please note that if you extract part of the original file to a new file, the above info will not be saved to the new file

10. Firmware log

   -1.35 vs 1.34

    - Fixed leap year error in standalone mode

    - Use D5 and D6 as flag in standalone trigger mode (except DI-4730): D5 is low when file is open, D6 is low when trigger is detected. D5 & D6 back to high when file is closed

   -1.36 vs 1.35
   
    - Longer USB wait time before switching to Ethernet

    - Wait until power supply stable before recording in standalone

    - Fixed rate error in CDC mode

    - Fixed 2108P stand alone circular mode error

   -1.37 vs 1.36

    - Starts new files in standalone when buffer overran

    - Fixed timestamp error for 2108P

    - Fix sync error 

    - increase precision in ASCII output mode from .3e to .5e
