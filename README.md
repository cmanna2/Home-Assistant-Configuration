# Conceptual Smart Home Architecture / Integrations
![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/9B94BFD0-4A6F-4B91-969A-C0219C7BC23A.jpeg)

### Sample Screenshots
![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/045FFA9A-86DC-4A6A-8F9A-9E80E41EDC94.jpeg)

![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/B53AC856-4ED9-4EB1-BC4F-63E44AACDB03.jpeg)

# Home Assistant Config (0.90.1)
Home Assistant Configuration on Intel Nuc

## Hubs (Hardware/Software)
* Intel Nuc (i3) with Aeotec Zwave Stick running Ubuntu 16.04 w/ Docker
  * Portainer
  * Home Assistant (HassIO)
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

## Lighting
* Hue bulbs (color)
* Hue lightstrip
* Hue Play bar
* GE zwave light switches (motion sensing, paddle)
* Ikea Stromlinje (integrated to Hue hub)
* Aeotec Zwave LED Light

## Locks
* Schlage Connect Zwave

## Sensors
* Hue motion sensor
* Zooz zwave multisensor
* Monoprice zwave door sensor(s)
* Belkin Wemo motion sensor

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
* Sonos Connect
* Sonos Amp (Outdoor Speakers)

## Notification
* Pushbullet

## Presence Detection
* Unifi Controller

## Garage
* GoControl Zwave Garage Relay
* Monoprice Zwave Tilt Sensor

## Smoke/CO Detection
* 2x First Alert 2-in-1 Zwave Smoke Detector & Carbon Monoxide Alarm
* 2x Nest Protect

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
