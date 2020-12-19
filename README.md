# Firmware_Upgrade

**For DI-2xxx and 4xxx users: These firmware are for the latest rev of the device with standalone capability**

For older ones without standalone capability, please go to https://github.com/dataq-instruments/Firmware_Upgrade/tree/main/OlderVersionWithOutStandAloneOption

1. Download and install the flash program for Windows from https://www.ti.com/tool/LMFLASHPROGRAMMER

2. Remove the USB cable from your device and PC, and remove power supply to the device if it gets power from external power supply

3. Plug the USB cable to PC (the other end should NOT connect to the device at this point)

4. For device without external power supply, plug in the USB cable to the device while holding the button down. The LED should be solid WHITE, if not go back to step 2.

5. For device with external power supply, such as DI-4718B and DI-4730, push and hold the button while powering up the device.  The LED should be solid WHITE, if so, connect the USB cable to the device, if not go back to step 2. 

6. Start LMFlash.exe program installed in step 1. The startup Page will be exactly as below. 

![alt text](https://www.dataq.com/resources/repository/lmflash1.png)

7. Choose the Program Tab. Navigate to your download directory, click on the appropriate bin file for your device. 

![alt text](https://www.dataq.com/resources/repository/lmflash2.png)

8. Press the Program Button at the lower left corner. When it finishes, the device should be FLASHING Green or Yellow, based on the USB mode enabled.
