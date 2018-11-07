# Rodon2018 Documentation

The following sections define the different components of the robot.

## Electronics

The robot functions have been divided in two boards:

- A GNU/Linux one (i.e., an SBC)
- and a microcontroller one.

The former will be called CPUBoard from now on, and the latter, MicrocontrollerBoard.

Any Raspberry-like board and an Arduino/ESPxx board, respectively, will serve for the purpose. The CPUBoard code is cross-platform since it is Node.js based, and the Arduino code should be straightforward to run or port to other microcontrollers.

The CPUBoard will communicate with the MicrocontrollerBoard through a serial port.

### CPUBoard

This board will process high level functions and serve a web based interface.

The CPUBoard should have WiFi, and USB 2.0 support (to use a USB webcam, or alternatively, some other camera supported in Video4Linux). It should also have audio mic/output connectors, but it doesn't need video output. I2C and 2 x UART are also needed (UARTs can be USB dongle ones).

See [custom CPUBoard for a NanoPi-Duo](3_CPUBoard.md) for more info about the SBC used in the project and how to adapt your own one.

### MicrocontrollerBoard

The MicrocontrollerBoard controls most of the hardware in real time: it does servos and motors PWM control, read wheel encoders and control other things.

Besides the MicrocontrollerBoard, you will also need an H-Bridge dual motor driver board suited to control the power of the two motors (in voltage and wattage).

For this you can use:

- A standalone (or shield) H-Bridge driver module in combination with any generic Arduino/ESPxx/STM for the MicrocontrollerBoard, or
- A [custom MicrocontrollerBoard with integrated dual H-Bridge](2_MicrocontrollerBoard.md), which is used in the project. Read the previous link for more info on the board and how to use a generic one.


## Robot platform and motors

Any robot base with motors and wheel encoders can be used. In the project, an old robot platform is used (which parts were included in magazines) Wheel encoders obtained from an old matrix printer were added (they have 50 marks per revolution). Also was added to the platform a stronger free rotation third wheel. 3D printer parts will be added to enclosure the electronics and bring structural support for the actuators.

W.I.P

## Sensors

- [Wheel encoders](5_Sensors.md#wheel-encoders)
- [Camera](5_Sensors.md#camera)
- [Big lidar sensor](5_Sensors.md#big-lidar-sensor)
- [Small lidar sensor](5_Sensors.md#small-lidar-sensor)
 

## Actuators

- [Camera turret with two servos](6_Actuators.md#servo-turret)
- [Arm](6_Actuators.md#arm)


## Power supply

- [LiPo battery](7_PowerSupply.md#lipo-battery)
- [Step-down buck voltage converter](7_PowerSupply.md#step-down-buck-voltage-converter)
