Requirements
USB to UART adapter (if your board doesn’t have native USB)

The latest firmware .bin file from RTL8720dn-Deauther Releases

esptool.py installed on your PC

USB cable

Steps
Connect your Black Hole V1.0 board to your computer via USB or UART adapter.

Put the board into bootloader mode:

Press and hold the Boot button.

While holding Boot, press and release the Reset button.

Release the Boot button.

Open a terminal or command prompt.

Erase existing flash:

bash
Copy
Edit
esptool.py --port [YOUR_SERIAL_PORT] erase_flash
Replace [YOUR_SERIAL_PORT] with your serial port (e.g., COM3 on Windows or /dev/ttyUSB0 on Linux/macOS).

Flash the firmware:

bash
Copy
Edit
esptool.py --chip rtl8720dn --port [YOUR_SERIAL_PORT] write_flash 0x0 path/to/firmware.bin
Make sure to replace path/to/firmware.bin with the actual path to your downloaded firmware file.

Once flashing completes, reset your board by pressing the Reset button.

Your Black Hole V1.0 board should now boot with the new RTL8720dn-Deauther firmware!
