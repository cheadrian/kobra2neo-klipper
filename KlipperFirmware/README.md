# Kobra 2 Neo Klipper Firmware

There are two versions of Klipper firmware:

	- klipper_usart.bin - if you want connect to printer PCB using UART interface of the Raspberry Pi, baud rate 115200
	- klipper_usart_250000.bin - same as above but with baud rate 115200
	- klipper_usb.bin - if you want to use the USB connection between Raspberry Pi and the printer, baud rate 250000

---

## Installation
Put the firmware to the micro SDCard and rename it to `firmware.bin`, power up the printer, wait 1 minute, power off the printer and pull out the micro SDCard, enjoy.