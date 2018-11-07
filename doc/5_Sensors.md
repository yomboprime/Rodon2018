# Sensors

## Wheel encoders

Simple on/off encoders are used, to provide speed/relative movement between readings for each wheel. You can set the number of marks per revolution in the code. The left and right wheel encoders are attached to two pins on the [MicrocontrollerBoard](2_MicrocontrollerBoard.md)

## Camera

A USB webcam or integrated camera which can support Video4Linux will be needed, attached to the [CPUBoard](3_CPUBoard.md)

## Big LIDAR Sensor

The TF-Mini LIDAR sensor is used for long range finding. This is a 30 to 2000 cm range LIDAR sensor with 1 cm precision and UART interface. Only RX line (reading from sensor) is needed, attached to the [CPUBoard](3_CPUBoard.md)

## Small LIDAR Sensor

The V53L0X LIDAR sensor is used. This is a 5 to 120 cm range LIDAR sensor with 1 mm precision. I has I2C interface, connected to the [CPUBoard](3_CPUBoard.md)
