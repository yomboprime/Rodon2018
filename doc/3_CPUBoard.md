# CPUBoard

This board will process high level functions and serve a web based interface.

The code for this board is W.I.P. It is based in Node.js (which is multi-platform)

As with other components of the robot, you can use any Raspberry-like board you've got around, the code is compatible. Just keep in mind:
 
- Check the voltage between the CPUBoard and the MicrocontrollerBoard. If both are 3.3V, everything is fine, but if one of them is 5V, you'll have to convert the voltages for the communication lines from 5V to 3V. This is done in the [custom MicrocontrollerBoard](2_MicrocontrollerBoard.md)


## Features

The needed features on the CPUBoard are:

- SPI or UART for communications with the MicrocontrollerBoard, to be decided.
- UART to communicate with the [big LIDAR Sensor](5_Sensors.md#big-lidar-sensor).
- I2C to communicate with the [small LIDAR Sensor](5_Sensors.md#small-lidar-sensor).
- Microphone input and audio output mini-jacks.
- Camera compatible with Video4Linux.


## Preparation of OS environment

The CPUBoard must have a compatible GNU/Linux system.

### Prerequisites instalation

- Node.js is required. Read [Node.js docs](https://nodejs.org/) on how to install for your OS.
- Clone [Rodon2018 repository](https://github.com/yomboprime/Rodon2018.git) into the CPUBoard file system (`Rodon2018/` from now on)
- Install library dependecies by issuing these commands:
  - `cd Rodon2018/`
  - `npm install`

### WiFi configuration

Please refer to your OS documentation on how to set up a WiFi network. You can either:

- Use a common WiFi network accessible by CPUBoard and the client system/s (any browser-capable device can be a client), or
- Configure CPUBoard to create an adhoc WiFi network, accessible by the clients.

### Using the robot software

To simply do a test execute, do just:

- `cd Rodon2018/`
- `npm start`

(ctrl-c to exit)

To execute the robot js code at system startup automatically, usually adding these lines at the end of the `/etc.rc.local` file will suffice:

- `cd /absolute_path_to_Rodon2018/`
- `npm start || exit 1`
- `exit 0`

The system will have to be shutdown by the client web interface or from a ssh terminal.
