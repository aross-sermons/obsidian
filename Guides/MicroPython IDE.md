---
title: MicroPython IDE
parent:
  - "[[Guide]]"
aliases: 
tags:
  - vs-code
---
### Prerequisites - Windows 11
**Applications**
- Python
- VSCode
**VSCode**
- Install Python extension
- Install Pymakr extension
- Edit Pymakr config with `Ctrl+Shift+P`, Pymakr > Extra > Global Settings
- Specify the desired serial port
**Python**
- (Optional) Create a virtual environment
- Install esptool with `pip install esptool`
### Micropython Firmware
**Installation**
- Download from https://micropython.org/download/ESP32_GENERIC/
- Erase ESP32 flash memory with `esptool.py --port [COM#] erase_flash`
- Write firmware with `esptool.py --port [COM#] --baud 460800 write_flash -z 0x1000 path_to_your_micropython_firmware.bin`
**Evaluation**
- Open REPL (serial output) with `Ctrl+Shift+P`, Pymakr > Open REPL
- Enter the following commands to check that the necessary packages are available:
- `import sys`
- `print(sys.version)`
- `help('modules')`