# CPUBoard

CPUBoard is the one used as the main robot CPU.

As with other components of the robot, you can use any Raspberry-like board you've got around, the code is compatible. Just keep in mind:
 
- Check the voltage between the CPUBoard and the MicrocontrollerBoard. If both are 3.3V, everything is fine, but if one of them is 5V, you'll have to convert the voltages for the communication lines from 5V to 3V. This is done in the [custom MicrocontrollerBoard](2_MicrocontrollerBoard.md)

## Features of CPUBoard

The needed features on the CPUBoard are:

- UART to communicate with the MicrocontrollerBoard.
- UART to communicate with the [big LIDAR Sensor](5_Sensors.md#big-lidar-sensor).
- I2C to communicate with the [small LIDAR Sensor](5_Sensors.md#small-lidar-sensor).
- Microphone input and audio output mini-jacks.
- A video camera compatible with Video4Linux.

## Preparation of CPUBoard OS environment

The CPUBoard must have a compatible GNU/Linux system.

### Prerequisites instalation

W.I.P

- Node.js is required. Read [Node.js docs](https://nodejs.org/) on how to install for your OS.
- Clone [Rodon2018 repository](https://github.com/yomboprime/Rodon2018.git) into the CPUBoard file system (`Rodon2018/` from now on)
- Install library dependecies by issuing these commands:
  - `cd Rodon2018/CPUBrain/`
  - `npm install`

### WiFi configuration

Please refer to your OS documentation on how to set up a WiFi network. You can either:

- Use a common WiFi network accessible by CPUBoard and the client system/s, or
- Configure CPUBoard to create an adhoc WiFi network, accessible by the client/s.

It is recommended to set a static IP so you won't have to find CPUBoard in the network each time.

## Project board
 
The custom board used and designed for this project uses a [FriendlyArm NanoPi-Duo SBC](https://www.friendlyarm.com/index.php?route=product/product&path=69&product_id=197), which is a SBC in very small factor with only pin headers broken out.

The second version of this SBC, the [NanoPi Duo 2](https://www.friendlyarm.com/index.php?route=product/product&path=69&product_id=244) is pin compatible, exposes a camera connector (OV5640) and has 1080p@30fps YUV hardware decompression (though without support in the latest mainline kernel 4.11.2 at the moment) Both versions are interchangeable to use in this project mother board, the only difference being that the first one will require an USB 2.0 camera, while the second one can use a 1080p OV5640 camera. Oh, and also has better WiFi chip and has Bluetooth 4.1.

The features of the mother board are:

- Supply voltage is 5V through micro-USB
- 2 x USB 2.0 connectors
- Microphone input minijack
- Stereo output minijack
- Composite video output exposed in pin headers (not used in this project)
- 2 x UART, I2C exposed in pin headers

The Kicad design of this board is located [here](https://github.com/yomboprime/CPUBoard).

## The software: CPUBrain

The code for this board is W.I.P. and is not completed yet.

The robot server software which runs in CPUBoard is called CPUBrain and it is written in js. It runs in Node.js, which is a multi-platform runtime for the js language.

### Running CPUBrain in CPUBoard

#### Executing to test it

To simply do a run test of the software, do just:

- `cd Rodon2018/CPUBrain/`
- `npm start`

Press (ctrl-c) to exit at any time.

#### Run at system startup

To execute CPUBrain at system startup automatically, usually adding these lines at the end of the `/etc.rc.local` file will suffice:

- `cd /absolute_path_to_Rodon2018/CPUBrain/`
- `npm start || exit 1`
- `exit 0`

The system will have to be shutdown by the client web interface or from a ssh terminal.

#### Running the web interface in a client

Any browser-capable device can be a client. Just:

- Connect to the same network the CPUBoard is connected to.
- Navigate with a modern browser to `http://<ip>:<port>/public`

Where:

- `<ip>` is the static IP address of CPUBoard in the network.
- `<port>` is the application TCP port as defined in the CPUBrain configuration file (TODO link file doc).

Example: `http://192.168.1.189:8090/public`
