# Home-Assistant-Configuration
Home Assistant Configuration on RPi3

## Hubs
* Raspberry Pi 3 running Home Assistant, Mosquitto (MQTT), Openzwave Control Panel, Razberry GPIO zwave daughter card
* Raspberry Pi Model B running Homebridge with HomeAssistant plugin
* Philips Hue Hub
* Logitech Harmony Hub

## Devices
* GE zwave light switches
* GE zwave outlets
* Belkin Wemo switch + motion sensor
* Hue color bulbs
* Hue motion sensor

## Media
* Plex Media Server
* Chromecast
* Roku 3
* Sonos Play 5, Play 1, Connect

## Automations

### Media
* Turn on ‘movie’ scene when Harmony hub is on

### Lighting
* Turn on kitchen lights to dimmed level when first person wakes up and comes downstairs in the morning
* Turn off basement lights after the ecobee remote sensor goes unoccupied and the harmony hub is off and at least one basement light is on
* Turn off office lights after ecobee remote sensor goes unoccupied
* Turn on outdoor lights and select indoor lights when sun sets
* Turn on Maya’s play light in basement when ecobee remote sensor goes occupied
* Turn off outside lights and upstairs lights when the sun rises
* Turn off all lights when we go to bed

### Away Modes
* When ecobee is set to away mode before sunset, turn off all lights
* When ecobee is set to away mode after sunset, turn on away lighting scene
* Check at sunset the status of the ecobee to determine if lighting away scene needs to be set or not

### Zwave
* Heal the zwave network at 2:30am

### User Interface
* Display the outdoor lighting tile after sunset
* Display the chromecast media tile when playing
* Display Roku media tile when playing
