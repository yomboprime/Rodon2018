# Rodon2018
Open source wheeled robot.

This project will hold schematics, designs and code for a complete robot.

The robot electronics consist of an SBC (Raspberry-like board) and a Arduino/ESP/STM32-like board.

The main goal of the project is to create software for a wheeled robot suited for a diversity of common controller boards and hardware, i.e. Raspberry-like boards, microcontroller boards, and "Arduino modules". The particular hardware used in the project may differ from yours.

The libre tools used are: Kicad for the electronics, Freecad and Blender for the 3D designs, Inkscape for 2D artwork, and your favourite manner of editing code.

## Documentation

Please read the [project documentation](doc/1_DocumentationMain.md)

## Project phases history

- ✔️ Design MicrocontrollerBoard: Kicad design for the microcontroller board (Atmega1284P-PU)
- ➡️ Ordering and waiting for PCB arrival.
- Test MicrocontrollerBoard with motors.
- Do code a basic software & firmware.
- Keep growing functionality

## Acknowledgements

The small Lidar sensor code is based on the Adafruit VL53L0X Library, which is also MIT Licensed:

### Adafruit VL53L0X Library [![Build Status](https://travis-ci.org/adafruit/Adafruit_VL53L0X.svg?branch=master)](https://travis-ci.org/adafruit/Adafruit_VL53L0X)

This is a library for the Adafruit VL53L0X time-of-flight breakout:
  * https://www.adafruit.com/products/3317
 
Check out the links above for our tutorials and wiring diagrams. This chip uses I2C to communicate

Adafruit invests time and resources providing this open source code, please support Adafruit and open-source hardware by purchasing products from Adafruit!

Written by Limor Fried/Ladyada for Adafruit Industries.
MIT license, all text above must be included in any redistribution

## License

MIT Licensed, see LICENSE file.

![MicrocontrollerBoard](./MicrocontrollerBoard/Screenshot.jpeg)
