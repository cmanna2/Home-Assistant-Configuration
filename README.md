# Home Assistant Config (0.73)
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
* 4x Alexa Echo Dot

## Lighting
* Hue color changing bulbs
* Hue lightstrip
* GE zwave light switches (motion sensing, paddle)
* Aeotec Zwave LED Light

## Sensors
* Hue motion sensor
* Zooz zwave multisensor

## Switches
* GE zwave outlets
* GE zwave outdoor switch
* Belkin Wemo switch + motion sensor
* TPLink Switch

## Media
* Plex Media Server
* Chromecast
* Roku 3
* Xbox 360

## Audio
* Sonos Play 5
* Sonos Play 1
* Sonos Connect

## Notification
* Pushbullet

## Presence Detection
* Unifi Controller
* Nmap

## Garage
* GoControl Zwave Garage Relay

## Smoke/CO Detection
* 2x First Alert 2-in-1 Z-Wave Smoke Detector & Carbon Monoxide Alarm
* 2x Nest Protect


## Automations

### Media
* Turn on ‘movie’ scene when Harmony hub is on

### Lighting
* Turn on kitchen lights to dimmed level when first person wakes up and comes downstairs in the morning
* Turn off basement lights after the ecobee remote sensor goes unoccupied and the harmony hub is off and at least one basement light is on
* Turn off office lights after ecobee remote sensor goes unoccupied
* Turn on outdoor lights and select indoor lights when sun sets
* Turn on play light in basement when ecobee remote sensor goes occupied
* Turn off outside lights and upstairs lights when the sun rises
* Turn off all lights when we go to bed

### Away Modes
* When ecobee is set to away mode before sunset, turn off all lights
* When ecobee is set to away mode after sunset, turn on away lighting scene
* Check at sunset the status of the ecobee to determine if lighting away scene needs to be set or not

### Zwave
* Heal the zwave network at 2:30am

### Sample Screenshots
![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/Main.PNG)

![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/1st%20floor.PNG)

![alt text](https://github.com/cmanna2/Home-Assistant-Configuration/blob/master/2nd%20floor.PNG)
