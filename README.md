# nodejs-poolController-mqtt  Version 1.0

[![License: AGPL v3](https://img.shields.io/badge/License-AGPL%20v3-blue.svg)](https://www.gnu.org/licenses/agpl-3.0)

[![Join the chat at https://gitter.im/nodejs-poolController/Lobby](https://badges.gitter.im/nodejs-poolController/Lobby.svg)](https://gitter.im/nodejs-poolController/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) 

MQTT integration for the [nodejs-poolController](https://github.com/tagyoureit/nodejs-poolController) pool equipment controller written by tagyoureit. This allows communication and control of Pentair (and other supported model) pool equipment via [MQTT](http://mqtt.org), allowing for integration with any home automation systems which can interact with MQTT messages.

This allows easy integration with other home automation softwares such as [Node-RED](https://nodered.org) and allows the development of a dashboard for use on a mobile phone such as the following:

<img src="https://github.com/crsherman/nodejs-poolController-mqtt/blob/master/images/IMG_0600.PNG" height="400"> 
<img src="https://github.com/crsherman/nodejs-poolController-mqtt/blob/master/images/IMG_0601.PNG" height="400"> 

### Changelog

* Version 1.1: added support for temperature values (Pool, Spa and Air) to be submitted via mqtt.

## Requirements

* A mqtt broker must be available on your network; this has been tested with the [Eclipse Mosquitto MQTT broker](https://mosquitto.org).

* An instance of [nodejs-poolController](https://github.com/tagyoureit/nodejs-poolController) running on your system. **PLEASE NOTE: THIS INTEGRATION ONLY WORKS FOR VERSION 5.3.1 AND LOWER.  IT HAS NOT BEEN UPDATED FOR THE NEWER VERSION 6.0.**

#### Optional

* [Node-RED](https://nodered.org/) for integrating into a home automation system.

## Installation Instructions

1. Add the following to the `package.json` file in the `nodejs-poolController` folder 

```json
"jsonata": "^1.5.3",
"mqtt": "^2.17.0",
```

2. Add the following to the `config.json` file in the `nodejs-poolController` folder (**precaution: make a backup copy of your `config.json` or customized configuration file.**)

```json
"integrations": {
        "outputSocketToMQTT": 1
    },
"outputSocketToMQTT": {
        "level": "debug"
    },
``` 

3. Modify `outputSocketToMQTT.js` (line 46) to specify the IP address of YOUR MQTT server on your network. ALTERNATIVELY, you can set environment variables where you start npm:

```bash
export MQTT_BROKER_ADDRESS="http://192.168.1.179:1883"
```

...and optionally a username and password (if required):

```bash
export MQTT_USERNAME=your-mqtt-username
export MQTT_PASSWORD=your-mqtt-password
```

4. Add the `outputSocketToMQTT.js` file to the `nodejs-poolController/src/integrations` folder on your Rapsberry Pi

5. Run npm install in the `nodejs-poolController` folder where package.json exists

## Credits

* [Scargill's Tech Blog](https://tech.scargill.net).  A wealth of information on node-red, iot, home automation and such.  I cannot say enough good things about this website.  The LCD panel utilized on my node-red flow is directly from his blog (among other things).

* [nodejs-poolController](https://github.com/tagyoureit/nodejs-poolController).  Tagyoureit's incredible app that provides connection to our Pentair pool controllers.

If I have missed anyone or group that my integration code utilizes I apologize.  Please let me know and I will add the appropriate credits.  
