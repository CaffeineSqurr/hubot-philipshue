# hubot-philipshue

This is a hubot plugin that will control your philips hue lights

[![Build Status](https://travis-ci.org/hubot-scripts/hubot-example.png)](https://travis-ci.org/kingbin/hubot-philipshue)


## Installation

Add the package `hubot-philipshue` as a dependency in your Hubot `package.json` file.

    "dependencies": {
      "hubot-philipshue": "*"
    }

Run the following command to make sure the module is installed.

    $ npm install hubot-philipshue

To enable the script, add the `hubot-philipshue` entry to the `external-scripts.json` file (you may need to create this file).

    ["hubot-philipshue"]



## Dependencies:

## Configuration:
 This script is dependent on environment variables:
   PHILIPS_HUE_HASH : export PHILIPS_HUE_HASH="secrets"
   PHILIPS_HUE_IP : export PHILIPS_HUE_IP="xxx.xxx.xxx.xxx"

 Setting your Hue Hash

 This needs to be done once, it seems older versions of the Hue bridge used an md5 hash as a 'username' but now you can use anything.

 Make an HTTP POST request of the following to http://YourHueHub/api

 {"username": "YourHash", "devicetype": "YourAppName"}
 If you have not pressed the button on the Hue Hub you will receive an error like this;

 {"error":{"type":101,"address":"/","description":"link button not pressed"}}
 Press the link button on the hub and try again and you should receive;

 {"success":{"username":"YourHash"}}
 The key above will be the username you sent, remember this, you'll need it in all future requests

 ie: curl -v -H "Content-Type: application/json" -X POST 'http://YourHueHub/api' -d '{"username": "YourHash", "devicetype": "YourAppName"}'


## Commands:
-   hubot hue lights - list all lights
-   hubot hue light <light number>  - shows light status
-   hubot hue turn light <light number> <on|off> - flips the switch
-   hubot hue groups - groups lights together to control with one API call
-   hubot hue config - reads bridge config
-   hubot hue hash - get a hash code (press the link button)
-   hubot hue set config (name|linkbutton) <value>- change the name or programatically press the link button
-   hubot hue (alert|alerts) light <light number> - blink once or blink for 10 seconds specific light

## Notes:

## Author:
   kingbin - chris.blazek@gmail.com
