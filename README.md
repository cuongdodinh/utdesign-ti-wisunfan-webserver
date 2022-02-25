# Description

The utdesign-ti-wisunfan-webserver provides a configuration and realtime
monitoring solution for TI's WiSUN offerings.

# Getting Started

- Install [wfantund](https://github.com/TexasInstruments/ti-wisunfantund)

- Download latest [release](https://github.com/Stephen-Campbell-UTD/utdesign-ti-wisunfan-webserver/releases)

# Usage
1. Open your shell directory where the release executable, `utdesign-ti-wisunfan-webserver.out`, was downloaded
2. Ensure `./utdesign-ti-wisunfan-webserver.out` has the executable file permission. If not, run `chmod +x ./utdesign-ti-wisunfan-webserver.out`
3. Run `./utdesign-ti-wisunfan-webserver.out`. This requires root priviledges.
This will start a webserver on port 80 (port can be configured with `--port <port-number>` flag)
4. Connect Border Router turn on network nodes. Make sure device will appears  `/dev/ttyACM0` if not possible this can be configured with the `--serial-port <filepath>` flag. 
5. The network configuration tab will appear. This allows you to configure
  the values of ncp properties. The explanation behind these properties can be
  found
  [here](https://dev.ti.com/tirex/explore/content/simplelink_cc13x2_26x2_sdk_5_20_00_52/docs/ti_wisunfan/html/wisun-guide/NWP_interface.html#:~:text=TI%20Wi%2DSUN%20FAN%20NWP%20Properties).

  ![Configuration Tab](./resources/configScreenshot.png)

6. After the border router has started its network, the network nodes should be
  given a few minutes to connect. Once the nodes connect, they will appear in the
  monitor tab. This tab allows this network to be monitored for latency, success rate, and topology.

  ![Successfuly Monitor](./resources/monitoringScreenshot.png)

**Tips**

- Run `./utdesign-ti-wisunfan-webserver.out --help` to get in-depth server
  configuration options.

- Logs generated by wfantund and server iteself are dumped in the `/tmp/utdesign-ti-wisunfan-webserver/logs/` directory.

# Developing

**Prerequisites**

- Install [wfantund](https://github.com/TexasInstruments/ti-wisunfantund)

- Install [Node.js](https://nodejs.org/en/) v16.13.2

  - **Important** If using sudo, Node v16.13.2 must be in the sudo path e.g. in /usr/bin/

- Install each client/server dependences
  For Client:
  ```bash
  cd <project-root>/client
  npm install
  ```
  For Server:
  ```bash
  cd <project-root>/server
  npm install
  ```

# Notes

This project is a part of UTDesign capstone project.
