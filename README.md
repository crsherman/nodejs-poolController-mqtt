# nodejs-poolController-mqtt  Version 1.0

[![Join the chat at https://gitter.im/nodejs-poolController/Lobby](https://badges.gitter.im/nodejs-poolController/Lobby.svg)](https://gitter.im/nodejs-poolController/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) 

 A MQTT integration for the application nodejs-poolController written by tagyoureit.


# License

nodejs-poolController-mqtt.  A mqtt integration for the nodejs-poolcontroller application to control pool equipment.

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU Affero General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU Affero General Public License for more details.

You should have received a copy of the GNU Affero General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

Requries Russell Goldin (tagyoureit) nodejs-poolController be running on your network.  For details please visit [here](https://github.com/tagyoureit/nodejs-poolController)

## What is nodejs-poolController

nodejs-poolController is an application to communicate and control your Pentair compatible pool equipment.  [nodejs-poolController](https://github.com/tagyoureit/nodejs-poolController) by tagyoureit.

## What is nodejs-poolController-mqtt

nodejs-poolController-mqtt is an integration for the nodejs-poolController app.  It allows the utilization of the mqtt protocol.  For more details on mqtt vist [here](http://mqtt.org)

This allows easy integration with other home automation softwares such as [node-red](https://nodered.org) and allows the development of a dashboard for use on a mobile phone such as the following:

<img src="https://github.com/crsherman/nodejs-poolController-mqtt/blob/master/images/IMG_0600.PNG" height="400"> 
<img src="https://github.com/crsherman/nodejs-poolController-mqtt/blob/master/images/IMG_0601.PNG" height="400"> 

## Installation Instructions

#1.  Add the following to the package.json file in the nodejs-poolController folder 
"jsonata": "^1.5.3",
"mqtt": "^2.17.0",
#2.  Add the following to the config.json file in the nodejs-poolController folder 
"integrations": {
        "outputSocketToMQTT": 1
    },
"outputSocketToMQTT": {
        "level": "debug"
    },

Precaution:  make a backup copy of your config.json or customized configuration file.  

#3.  Add the outputSocketToMQTT.js file to the nodejs-poolController/src/inegrations folder on your rapsberry pi

#4.  Run npm install in the nodejs-poolController folder where package.json exists

## Requirements

A mqtt broker must be available on your network.  I utilize the Eclipse Mosquitto MQTT broker [here](https://mosquitto.org).

Of course the nodejs-poolController running on your system.

Node-red if you are planning on integrating into a home automation system or such.

## Credits

[Scargill's Tech Blog](https://tech.scargill.net).  A wealth of information on node-red, iot, home automation and such.  I cannot say enought good things about this website.  The LCD panel utilized on my node-red flow is directly from his blog (among other things).

[nodejs-poolController](https://github.com/tagyoureit/nodejs-poolController).  Tagyoureit's incredible app that provides connection to our Pentair pool controllers.

If I have missed anyone or group that my integration code utilizes I apologize.  Please let me know and I will add the appropriate credits.  