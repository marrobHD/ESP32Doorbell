# ESP32Doorbell
🔔 A ESPHome ESP32 Doorbell with OLED display 🔔

[![GitHub Release][releases-shield]][releases]
[![License][license-shield]](LICENSE.md)

![Project Maintenance][maintenance-shield]
[![GitHub Activity][commits-shield]][commits]
[![Discord][discord-shield]][discord]
![Community Forum][forum-shield]

[![Twitter][twitter]][twitter]
[![Github][github]][github]

<!-- 🎉 Release of ESP32 Doorbell 0.0.1 -->

## About

This is the code for a ESP32 doorbell with a display and camera that works with ESPHome and HomeAssistant.
Example:
https://youtu.be/QuBe9cWIcqs
<!-- also includes... -->


## Features

The code for the ESP32 doorbell, of course, provides the code for ESPHome and the configuration for HomeAssistant. Additionally, it comes also with these features:

- ...
- Easy to change the configuration
  - Only have to change the definitions at the top in the ESPHome config.
  - Comes with all needed configurations.
- Integrated camera module.
- Ring to three different locations.
- One button control design.
- GUI displayed with a SH1106 128x64 OLED display.
- Touch & push button compatibility.
- HTML5 notifications with captured image from the camera module.
- alarm state displayed.
- Temperature and humidity text_sensor.
- DarkSky weather displayed on the screen. (later with symbols and animations)
- Ringtone on media_player device.


## Installation & Configuration

### Step 1
Install [ESPHome][esphome] by following this guide: https://esphome.io/guides/getting_started_hassio.html.

### Step 2
Copy the Folder `ESPHome` into `/config/` from HomeAssistant. Next you have to add the code in the following files into your HomeAssistant configuration: `automations.yaml`, `scripts.yaml`, `input_boolean.yaml`, `input_select.yaml` and `input_text.yaml`.

### Step 3
Now adjust the `esp32 doorbell.yaml` via the ESPHome editor. Do that also with your other configuration files.

### Step 4
Now you´re ready to flash. Now you have to click on `validate` and if you got "esp32 doorbell.yaml is valid 👍" you can flash the ESP32 camera module via an FTDI USB flash adapter. If your configuration fails, check it again, fix the error and flash it.

### Step 5
Now check the serial console of the ESPHome flasher tool and wait for the module to successfully connect to the wifi. Next you have to go to the integrations page in HomeAssistand and add the ESPHome flashed chip via its ip address you saw in the serial console of the `ESPHome flasher`.

### Step 6
Restart HomeAssistant and you´re ready to test it.

FEEL FREE TO POST ISSUES


## Authors & contributors

The original setup of this repository is by [Marlon][marrobHD].

For a full list of all authors and contributors,
check [the contributor's page][contributors].



[Troubleshooting]()

[commits-shield]: https://img.shields.io/github/commit-activity/y/marrobHD/ESP32Doorbell.svg?style=for-the-badge
[commits]: https://github.com/marrobHD/ESP32Doorbell/commits/master
[discord]: https://discord.gg/ND4emRS
[discord-shield]: https://img.shields.io/discord/579704220970909717.svg?style=for-the-badge
[contributors]: https://github.com/marrobHD/ESP32Doorbell/graphs/contributors
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[license-shield]: https://img.shields.io/github/license/marrobHD/ESP32Doorbell.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-marrobHD-blue.svg?style=for-the-badge
[marrobHD]: https://github.com/marrobHD
[releases-shield]: https://img.shields.io/github/release/marrobHD/ESP32Doorbell.svg?style=for-the-badge
[releases]: https://github.com/marrobHD/ESP32Doorbell/releases
[esphome]: https://esphome.io
[contributors]: https://github.com/hassio-addons/addon-ssh/graphs/contributors
[forum-shield]: https://img.shields.io/badge/community-forum-brightgreen.svg?style=for-the-badge
[license-shield]: https://img.shields.io/github/license/marrobHD/ESP32Doorbell.svg?style=for-the-badge
[maintenance-shield]: https://img.shields.io/badge/maintainer-Marlon-blue.svg?style=for-the-badge
[releases-shield]: https://img.shields.io/github/release/marrobHD/ESP32Doorbell.svg?style=for-the-badge
[releases]: https://github.com/marrobHD/ESP32Doorbell/releases
[twitter]: https://img.shields.io/twitter/follow/TechxHome.svg?style=social
[github]: https://img.shields.io/github/followers/marrobHD.svg?style=social
