# Firmware_Upgrade

1) Download the flash programmer installation program for Windows from https://www.ti.com/tool/LMFLASHPROGRAMMER and run it.

2) Unplug the USB cable from your DI-???? device and remove power supply to the device if it gets power from external power supply

3) Plug the USB cable to PC

4a) For device without external power supply, plug in the USB cable to the device while holding the button down. The LED should be solid WHITE, if not repeat step 2.

4b) For device with external power supply, such as DI-4718B and DI-4730, push and hold the button while powering up the device.  The LED should be solid WHITE, if so, connect the USB to the device, if not repeat step 2. 

5) Start LMFlash.exe program installed in 1). The startup Page will be exactly as below. 

![alt text](https://www.dataq.com/resources/repository/lmflash1.png)

6) Choose the Program Tab. Navigate to your download directory, click on the appropriate bin file for your device. 

![alt text](https://www.dataq.com/resources/repository/lmflash2.png)

6) Press the Program Button at the lower left corner. When it finishes, it should return to FLASHING Green or Yellow, based on the USB mode enabled.
