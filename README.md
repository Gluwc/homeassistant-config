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

# Front-End

## YATBI (Yet Another Tile Based Interface)

![screenshot](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/images/yatbi.PNG)

### Features
* Tile based interface using [Browser Mod](https://github.com/thomasloven/hass-browser_mod), [Button Card](https://github.com/custom-cards/button-card) and [Decluttering Card](https://github.com/custom-cards/decluttering-card).
* Entity based templating allows for nesting of tiles.

### Why YABTI?
The power of YABTI lies with templating of your entities on the front end and easy nesting of tiles within other tiles.

### Examples
* [View](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/views/01_home.yaml) > [Living Room](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/entities/input_select/area/living_room.yaml) > [Lights](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/entities/light/group_living_room.yaml) > [Desk Light](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/decluttering_card/entities/light/group_living_room.yaml#L14)

![example_01](https://github.com/Gluwc/homeassistant-config/blob/master/yatbi/images/example_01.gif)
