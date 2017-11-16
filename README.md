# MQTT Dasher
***Emits events to MQTT when an Amazon Dash button is pressed.***

[![GitHub tag](https://img.shields.io/github/tag/stjohnjohnson/mqtt-dasher.svg)](https://github.com/stjohnjohnson/mqtt-dasher/releases)
[![Build Status](https://travis-ci.org/nolte/mqtt-dasher.svg?branch=master)](https://travis-ci.org/nolte/mqtt-dasher)

# Configuration

The dash bridge has one yaml file for configuration:

```
---
mqtt:
    # Specify your MQTT Broker's hostname or IP address here
    host: mqtt
    # Preface for the topics $PREFACE/$TOPIC
    preface: dash

buttons:
    44:65:0d:dc:51:50:
        name: nerf_supplies
        interface: eth0     # optional
        timeout: 5000   # optional (time in ms)
        protocol: arp   # optional (one of {udp, arp, all})

```

# Usage

_note: follow [this setup](https://github.com/hortinstein/node-dash-button#installation-instructions) first

1. Install the Node module globally

    ```
    $ npm install -g mqtt-dasher
    ```

2. Configure your buttons

    ```
    $ vi /opt/mqtt-dasher/config.yml
    ```

3. Run the server

    ```
    $ CONFIG_DIR=/opt/mqtt-dasher mqtt-dasher
    ```

4. Configured dash events now feed into MQTT

## use as Docker

**build amd64**   
[![Docker Pulls](https://img.shields.io/docker/pulls/nolte/mqtt-dasher.svg)](https://hub.docker.com/r/nolte/mqtt-dasher/) [![Docker Build Statu](https://img.shields.io/docker/build/nolte/mqtt-dasher.svg)](https://hub.docker.com/r/nolte/mqtt-dasher/) [![](https://images.microbadger.com/badges/image/nolte/mqtt-dasher.svg)](https://microbadger.com/images/nolte/mqtt-dasher "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/nolte/mqtt-dasher.svg)](https://microbadger.com/images/nolte/mqtt-dasher "Get your own version badge on microbadger.com")

```
docker-compose -f docker-compose.yml up
```

**build armhf**  

[![Docker Pulls](https://img.shields.io/docker/pulls/nolte/rpi-mqtt-dasher.svg)](https://hub.docker.com/r/nolte/rpi-mqtt-dasher/) [![](https://images.microbadger.com/badges/image/nolte/rpi-mqtt-dasher.svg)](https://microbadger.com/images/nolte/rpi-mqtt-dasher "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/nolte/rpi-mqtt-dasher.svg)](https://microbadger.com/images/nolte/rpi-mqtt-dasher "Get your own version badge on microbadger.com")

```
docker-compose -f docker-compose-rpi.yml up
```
