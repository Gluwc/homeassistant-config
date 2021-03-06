# Home Assistant Configuration

[Home Assistant](https://hub.docker.com/r/homeassistant/home-assistant) running in docker on [Intel® NUC Kit NUC8i7BEH](https://ark.intel.com/content/www/us/en/ark/products/126140/intel-nuc-kit-nuc8i7beh.html) (Ubuntu 18.04.3 LTS).

## Server Docker Applications
* [AppDaemon](https://hub.docker.com/r/acockburn/appdaemon) ([config](https://github.com/Gluwc/appdaemon-config/))
* [BIND](https://hub.docker.com/r/sameersbn/bind)
* [deCONZ](https://hub.docker.com/r/marthoc/deconz)
* [ESPHome](https://hub.docker.com/r/esphome/esphome)
* [Glances](https://hub.docker.com/r/nicolargo/glances)
* [Mosquitto](https://hub.docker.com/_/eclipse-mosquitto)
* [Nginx-Proxy-Manager](https://hub.docker.com/r/jc21/nginx-proxy-manager)
* [Portainer](https://hub.docker.com/r/portainer/portainer-ce)
* [Samba](https://hub.docker.com/r/dperson/samba)
* [Unifi Controller](https://hub.docker.com/r/jacobalberty/unifi)
* [zwavejs2mqtt](https://hub.docker.com/r/zwavejs/zwavejs2mqtt)

## Devices

### USB
|Manufacturer|Model|Amount|
|---|---|---|
|Dresden Elektronik|Conbee II|1|
|Schelte Bron|OpenTherm Gateway|1|
|Z-Wave.Me|UZB|1|


### ZWave
|Manufacturer|Model|Amount|
|---|---|---|
|AEON Labs|ZW099|1|
|Everspring|AD147|2|

### Zigbee
|Manufacturer|Model|Amount|
|---|---|---|
|IKEA of Sweden|TRADFRI control outlet|3|
|IKEA of Sweden|TRADFRI Driver 10W|1|
|IKEA of Sweden|TRADFRI motion sensor|1|
|IKEA of Sweden|TRADFRI transformer 10W|2|
|LUMI|lumi.curtain|2|
|LUMI|lumi.sensor_magnet.aq2|5|
|LUMI|lumi.sensor_motion|2|
|LUMI|lumi.sensor_switch.aq2|4|
|LUMI|lumi.weather|5|
|OSRAM|Plug 01|1|
|Philips|HML006|2|
|Philips|LLC020|1|
|Philips|LST002|1|
|Philips|LTW001|3|
|Philips|LTW012|2|
|Philips|LTW013|8|
|Philips|LWB010|2|
|Philips|PHDL00|1|
|Philips|RWL021|5|
|Philips|SML001|6|

### Wifi
|Manufacturer|Model|Amount|
|---|---|---|
|Allterco|Shelly 1|1|
|Dyson|438|1|
|espressif|Espressif ESP-WROVER-KIT|1|
|Google Inc.|Chromecast Audio|1|
|Google Inc.|Chromecast|1|
|Google Inc.|Google Home Mini|1|
|Google Inc.|Google Home|1|
|Google Inc.|Google Nest Mini|1|
|Google|Pixel 4|1|
|Logitech|Harmony Hub|1|
|Neato|BotVacD7Connected|1|
|Samsung|SM-T720|1|
|Sony|H8324|1|
|Sony|KD-55XF8096|1|

## YATBI (Yet Another Tile Based Interface)

![screenshot](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/images/yatbi.PNG)

### Features
* Tile based interface using [Browser Mod](https://github.com/thomasloven/hass-browser_mod), [Button Card](https://github.com/custom-cards/button-card) and [Decluttering Card](https://github.com/custom-cards/decluttering-card).
* Entity based templating allows for nesting of tiles.
* State based tile [styles](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/button_card/includes/states.yaml) (color, icon, etc).

### Why YATBI?
The power of YATBI lies with templating of your entities and easy nesting of tiles on the front end.

### Examples
* [View](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/views/01_home.yaml#L61-L63) > [Living Room](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/entities/input_select/area/living_room.yaml#L10-L12) > [Lights](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/entities/light/group_living_room.yaml#L14-L16) > Desk Light

![example_01](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/images/example_01.gif)

### Required Components
These components are all available on [HACS](https://hacs.xyz/).
* [Browser Mod](https://github.com/thomasloven/hass-browser_mod)
* [Button Card](https://github.com/custom-cards/button-card)
* [Decluttering Card](https://github.com/custom-cards/decluttering-card)
* [Card Mod](https://github.com/thomasloven/lovelace-card-mod)

### Button Card Tile Templates

| Template | Requires | Description
| ---- | ----------- | -------
| tile | entity | On tap shows HA more-info.
| popup | entity | On tap shows default YATBI popup of entity including State and Logbook/History.
| popup_entity | entity | On tap shows `popup` template with embedded entity template.
| popup_hold | entity |On tap does toggle. On hold shows `popup` template.
| popup_hold_entity | entity | On tap does toggle. On hold shows `popup_entity` template.
| popup_light | entity | On tap does toggle. On hold shows `popup` with embedded [light controls](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/yatbi_templates/controls_light.yaml).
| popup_cover | entity | On tap shows `popup` with embedded [cover controls](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/yatbi_templates/controls_cover.yaml).
| popup_custom | variables (`name`, `template`) | On tap shows [custom template](https://github.com/Gluwc/homeassistant-config/tree/master/yatbi/decluttering_card/custom).
| popup_task | entity | On tap sets current time of [Input Datetime](https://www.home-assistant.io/integrations/input_datetime/) entity. Requires custom [entity attribute](https://github.com/Gluwc/homeassistant-config/blob/master/customize.yaml#L28) (`task_seconds`, `task_hours`,`task_days`,`task_months`) to display correct state.
