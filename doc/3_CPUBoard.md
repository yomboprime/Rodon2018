# CPUBoard

CPUBoard is the board used as the main robot CPU. As with other components of the robot, you can use any Raspberry-like board you've got around, the code is compatible. The robot server software that runs in CPUBoard is called Neocortex and is written in js. It runs in Node.js, which is a multi-platform runtime for the js language. When using your CPUBoard just keep in mind:
 
- Check the voltage between the CPUBoard and the MicrocontrollerBoard. If both are 3.3V, everything is fine, but if one of them is 5V, you'll have to convert the voltages for the communication lines from 5V to 3V. This is done in the [custom MicrocontrollerBoard](2_MicrocontrollerBoard.md)

## Features of CPUBoard

The needed features on the CPUBoard are:

- Compatible GNU/Linux operating system.
- WiFi
- 2x UART to communicate with the two MicrocontrollerBoards (or only one if you use only one MicrocontrollerBoard, like an ESP32)
- A video camera compatible with Video4Linux.
- Analogue audio output (mono, or stereo if you want)
- Analogue microphone input.

## Project board

The CPUBoard used in this project is a [FriendlyArm NanoPi-Duo 2 SBC](http://wiki.friendlyarm.com/wiki/index.php/NanoPi_Duo2), which is a SBC in very small factor with only pin headers broken out, a OV5640 video camera connector, microUSB and microSD.

The pins corresponding to the SPI port are used here as the alternate function (a second UART) So SCK corresponds to RX2, and CS to TX2.

## The software: Neocortex

**The code for this board is W.I.P. and is not completed yet.**

### Prerequisites instalation

- Node.js is required. Read [Node.js docs](https://nodejs.org/) on how to install for your OS.

### Instalation

W.I.P

- Clone [Rodon2018 repository](https://github.com/yomboprime/Rodon2018.git) into the CPUBoard file system (`Rodon2018/` from now on)
- Install Node.js library dependecies by issuing these commands:
  - `cd Rodon2018/software/Neocortex/`
  - `npm install`

### WiFi configuration

Please refer to your OS documentation on how to set up a WiFi network. You can either:

- Use a common WiFi network accessible by CPUBoard and the client system/s, or
- Configure CPUBoard to create an adhoc WiFi network, accessible by the client/s.

It is recommended to set a static IP so you won't have to find CPUBoard in the network each time.

### Running Neocortex in CPUBoard

#### Executing to test it

To simply do a run test of the software, do just:

- `cd Rodon2018/software/Neocortex/`
- `npm start`

Press (ctrl-c) to exit at any time.

#### Run at system startup

To execute Neocortex at system startup automatically, usually adding these lines at the end of the `/etc.rc.local` file will suffice:

- `cd /absolute_path_to_Rodon2018/software/Neocortex/`
- `npm start || exit 1`
- `exit 0`

In this configuration, the system will have to be shutdown by the client web interface or from a ssh terminal.

#### Running the web interface in a client

Any browser-capable device can be a client. Just:

- Connect to the same network the CPUBoard is connected to.
- Navigate with a modern browser to `http://<ip>:<port>/public`

Where:

- `<ip>` is the static IP address of CPUBoard in the network.
- `<port>` is the application TCP port as defined in the Neocortex configuration file (TODO link file doc).

Example: `http://192.168.1.189:8090/public`
