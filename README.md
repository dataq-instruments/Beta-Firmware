# Firmware_Upgrade 

All released versions of firmware can be found in https://www.dataq.com/support/firmware/. 

Firmware here are unreleased beta revision

```diff
+if a wrong firmware is flashed in, the device may not run at all,   
-in that case, choose the correct firmware and reflash it
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
   
9. Starting firmware rev 1.35, if you use the original Windaq file, you can use a file hex editor such as https://mh-nexus.de/en/hxd/， to look into the area starting from offset of 0x3F2 to find out the reason the file was closed, and offset of 0x43A to find out the reason the file was started, see example below (Please note that if you extract part of the original file to a new file, the above info will not be saved to the new file) <br/>
![alt text](https://www.dataq.com/resources/repository/wdq_header.png)


10. Firmware update log from latest released version
   - Expands circular file size from 2G to 4G
