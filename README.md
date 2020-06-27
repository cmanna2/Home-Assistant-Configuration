# Conceptual Smart Home Architecture / Integrations
![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/9B94BFD0-4A6F-4B91-969A-C0219C7BC23A.jpeg)

### Sample Screenshots
![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/045FFA9A-86DC-4A6A-8F9A-9E80E41EDC94.jpeg)

![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/B53AC856-4ED9-4EB1-BC4F-63E44AACDB03.jpeg)

# My Devices
All of the smarts and parts used in my home are posted on kit.co (https://kit.co/cmanna2) and listed below:

## Hubs (Hardware/Software)
* Intel Nuc (i3) with Aeotec Zwave Stick running Ubuntu 16.04 w/ Docker
  * Portainer
  * Home Assistant (HassIO) v0.101.3
  * Unifi Controller
  * Node-red
  * Grafana
  * InfluxDB
  * Tautulli
* Philips Hue Hub
* Logitech Harmony Hub

## Networking
* 2x Ubiquiti Networks Unifi 802.11AC Pro
* Unified Security Gateway
* TPLink PoE Switch
* RPi 2 running PiHole

## Security
* Amcrest IP2M-841EW PoE Camera
* Amcrest IP2M-844E
* Raspberry Pi Zero W w/ Camera Module
* NVR - tinyCam recording to Dropbox

## HVAC
* Ecobee 3 w/ remote sensors

## Voice Control / Assistant
* 5x Alexa Echo Dot
* 1 Echo Input
* Siri (Siri Shortcuts) via iOS devices

## Lighting
* Hue bulbs (color)
* Hue lightstrip
* Hue Play bar
* GE zwave light switches (motion sensing, paddle)
* Ikea Stromlinje (integrated to Hue hub)
* Aeotec Zwave LED Light
* WLED with WS2812B LED's and ESP8266

## Locks
* Schlage Connect Zwave

## Sensors
* Hue motion sensor
* Zooz zwave multisensor
* Monoprice zwave door sensor(s)
* Belkin Wemo motion sensor
* ESPHome (ESP8266) temp and humidity

## Switches
* GE zwave outlets
* GE zwave outdoor switch
* Belkin WemoMini switches
* TPLink switches
* Alexa switces

## Media
* Plex Media Server
* Apple TV 4k
* Chromecast
* Roku 3
* Xbox One S

## Audio
* Sonos Play 5
* Sonos Play 1
* Sonos Beam
* Sonos Amp (Outdoor Speakers)
* Sonos Move

## Notification
* Pushcuts (actionable notifications)

## Presence Detection
* Unifi Controller

## Garage
* GoControl Zwave Garage Relay
* Monoprice Zwave Tilt Sensor

## Smoke/CO Detection
* 2x First Alert 2-in-1 Zwave Smoke Detector & Carbon Monoxide Alarm
* 2x Nest Protect

## NFC Tags
Just for fun I use the following NFC tags from Amazon around the house for triggering automations: 

* Timeskey NFC 10PCS NTAG 215 NFC Stickers NXP NTAG215 NFC Tags 100% Compatible with TagMo and Amiibo, 504 Bytes Memory Fully Programmable https://www.amazon.com/dp/B075CFXY8V/ref=cm_sw_r_cp_tai_H9reEb9V0EZDS

* NFC tag on nightstand to trigger the Goodnight automation
* NFC tag on the garage door keypad to open the garage door
* NFC tag in car to trigger Away Mode before leaving

# My Automations 
When I first got into Home Assistant I set up all automations in default YAML.  Although YAML certainly works and writing most automations is pretty intuitive, I quickly adopted Node-RED when the add-on was released and migrated all automations over.  Node-RED is immensely more powerful and worth the learning curve.  Many of our key automations / “modes” are below:
* Guest Mode 
  * When a known wireless device (friend, relative, etc) connects to our home WiFi network, send a notification, play personalized song over Sonos, and enable Guest Mode.  Guest Mode disables certain automations related to lighting control and Away Mode triggering if we leave the house while someone else is still there (e.g. watching our girls).
  * When no known guest wireless devices are seen on the network then Guest Mode turns off
* Away Mode
		* Away mode is manually triggered through Shortcuts or automatically if our family WiFi devices are not seen on the network  
		* When Away Mode is enabled a lighting setback scene is called (during the day all lights turn off, after sunset an away lighting scene is set), garage door closes if it is open, front door locks, Ecobee sets back the temperature set point, and Alarm Mode enables
		* When we return home from being away from the house and our phones re-connect to the WiFi, Home Mode is turned on and the front door unlocks
* Alarm Mode (automatically triggered when certain modes are enabled)
		* Select motion sensors (e.g. ecobee remote sensors, Belkin wemo sensor, ESPHome motion sensors) will trigger a notification if motion is detected when away
* Time based lighting control
		* At sunset the outdoor lights are turned on
		* At sunrise all outdoor lights turn off and any indoor light or switch still on upstairs turns off
* Motion based lighting control
		* Office light turns on when motion is detected and light level (lux) is less than 50
		* Master bedroom light turns on when motion is detected and it is after sunset.  When Goodnight Mode is enabled then this motion automation is disabled so the light does not turn on if someone gets up in the middle of the night
		* Upstairs hallway light turns on to 10% (nightlight) when motion is detected after sunset
		* When no motion is detected in any room with a motion sensor for 10 mins then all lights in the room turn off (auto-off)
* Good morning (manually triggered via Shortcuts)
		* Sets a morning lighting scene on the first floor by calling a scene configured in the Home app
		* Turns off my Alarm and Goodnight modes
		* Wakes up the living room Apple TV, opens the Channels App and sets channel 9.1 (WGN)
* Vacation Mode
		* Enables Away Mode, sets back Ecobee, and disables key automations that are part of Home Mode
* Goodnight (manually triggered via Shortcuts or NFC tag on nightstand)
		* When triggered, turns on Alarm Mode, disables certain motion activated lighting automations, closes front door if open, closes garage if open, turns off main server (Plex), and turns off all lights in the house
		* When the girls go to sleep, telling Alexa the “girls are going to bed” turns on a Hue lamp as a nightlight, turns on a Wemo switch for their humidifier (turns on if home humidity is below 40%), and starts Alexa sleep sounds skill

# Siri Shortcuts
Shortcuts provides a great tool to round out automations that include smart home devices and iOS device automations.  Well, that, and its simply fun to mess around with.  Shortcuts also has a iOS widget that gives quick access to a few smart home automations that I use often.  I find this more convenient than accessing the Home app via the Control Center.

A few of my favorite Shortcuts are below including a screenshot of all the shortcuts I am currently using.
* Find my backpack/keys/AirPods (Tile Pros w/ replaceable batteries) - Although I don’t use it often, being able to ask Siri where my keys are and have the Tile ring in response is pretty great
* Good morning - Currently this shortcut is not automated due to the variable morning schedules across the family but I intend to try to find a way to automate it without too many edge cases in the future.  When triggered the shortcut:
  * Sets a morning lighting scene on the first floor by calling a scene configured in the Home app
  * Turns off my Alarm and Goodnight modes
  * Wakes up the living room Apple TV
  * Opens the Channels App
  * Sets channel 9.1 (WGN)
* Away Mode - We use this every day when we leave the house
  * Turns off any lights that are still on in the house
  * Turns off the Apple TV if its on
  * Closes the garage door if its open
  * Locks the front door
  * Enables notifications from certain motion sensors in the house 
* Girls Playlist Basement
  * Enables Sonos through Harmony Hub which also turns on the Denon receiver
  * Gets the “Girls Playlist” from Apple Music
  * Sets the AirPlay playback destination to the Denon receiver and starts playback

![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/4DAF0DD8-DCB0-4D2E-8A59-15A45D84B4B4.jpeg)
![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/F5C04056-B8B3-4B20-8853-B32185BB11ED.jpeg)
