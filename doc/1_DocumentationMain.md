# Rodon2018 Documentation

The following sections define the different components of the robot.

## Electronics

The robot functions have been divided in two boards: A GNU/Linux one (i.e., an SBC) and a microcontroller one. Any Raspberry-like board and an Arduino/ESPxx board will do. The former will be called CPUBoard from now on, and the latter, MicrocontrollerBoard. The CPUBoard code is cross-platform since it is Node.js based, and the Arduino code should be straightforward to run or port to other microcontrollers.

The CPUBoard will communicate with the MicrocontrollerBoard through a serial port or SPI, still to be decided.

The CPUBoard should have WiFi, and USB 2.0 support (to use a USB webcam, or alternatively, some other camera connector accessible from Video4Linux). It should also have audio mic/output connectors, but it doesn't need video output. SPI, I2C and UART are also needed. In the project, a [custom CPUBoard for a NanoPi-Duo](3_CPUBoard.md) is used.

Besides the MicrocontrollerBoard, you will need a dual Full H-Bridge board suited to control the power of the two motors (in voltage and wattage). Some spare pins will be needed in the MicrocontrollerBoard for the motor PWM control, servos, to read wheel encoders and to control other things. In the project, a [custom MicrocontrollerBoard with integrated dual H-Bridge](2_MicrocontrollerBoard.md) is used.


## Robot platform and motors

Any robot base with motors and wheel encoders can be used. In the project, an old robot platform (which parts were included in magazines) is used with added wheel encoders obtained from an old matrix printer (50 marks per revolution). Also was added to the platform a stronger free rotation third wheel. 3D printer parts will be added to enclosure the electronics and bring structural support for the actuators.

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
