# ESP32Doorbell
🔔 ESPHome ESP32 Doorbell with OLED display 🔔
<!-- 🎉 Release of ESP32 Doorbell 0.0.0 -->

## About

With the MqTT RFID Music Player you can play music(Spotify) with an RFID tag.

## Installation

1. Download this Repository, import it in Platformio, change the mqtt and wifi settings and click on upload(ALT+CMD+U)
```txt
https://github.com/marrobHD/Mqtt-RFID-Player/releases
```
2. Open Files\EspEasy\FlashESP8266 select your COM port and sonoff.bin and click flash

3. Open Files\EspEasy\Termite.exe to use it to configure your devboard. Replace your WIFI and MqTT Info, paste and hit enter
```txt
Backlog ssid1 YOURSSID; password1 YOURPASSWORD; MqttHost YOURMQTT; MqttUser YOURMQTTTUSER; MqttPassword YOURMQTTPASSWORD; MqttPort 1883
```
4. Conntect 3 Buttons eg: Wire1 D1 Wire2 GND. Setup your buttos in Tasmota.
![](Files/Tasmota_config.png)
5. Setup this rules in Console. Hit after paste "Enter".
```txt
rule1 on switch1#state=3 do publish stat/button_1/TYPE {"type":hold_2sec} endon on switch1#state=2 do publish stat/button_1/TYPE {"type":single_press} endon on switch1#state=2 do event setvar1=+1 endon on event#setvar1 do counter %value% endon on event#getvar1 do counter endon on event#setvar1 do publish stat/button_1/log %value% endon on switch1#state=2 do event toggling1=%var1% endon on event#toggling1<1 do event setvar1=0 endon on event#toggling1>0 do event setvar1=0 endon
```
```txt
rule2 on switch2#state=3 do publish stat/button_2/TYPE {"type":hold_2sec} endon on switch2#state=2 do publish stat/button_2/TYPE {"type":single_press} endon on switch2#state=2 do event setvar2=+1 endon on event#setvar2 do counter2 %value% endon on event#getvar2 do counter2 endon on event#setvar2 do publish stat/button_2/log %value% endon on switch2#state=2 do event toggling2=%var2% endon on event#toggling2<1 do event setvar2=0 endon on event#toggling2>0 do event setvar2=0 endon
```
```txt
rule3 on switch3#state=3 do publish stat/button_3/TYPE {"type":hold_2sec} endon on switch3#state=2 do publish stat/button_3/TYPE {"type":single_press} endon on switch3#state=2 do event setvar3=+1 endon on event#setvar3 do counter3 %value% endon on event#getvar3 do counter3 endon on event#setvar3 do publish stat/button_3/log %value% endon on switch3#state=2 do event toggling3=%var3% endon on event#toggling3<1 do event setvar3=0 endon on event#toggling3>0 do event setvar3=0 endon
```
```txt
rule1 on
```
```txt
rule2 on
```
```txt
rule3 on
```
2. Copy the "Files\HomeAssistant\automations.yaml" text into your automations.

3. Copy the "Files\HomeAssistant\scripts.yaml" text into your scripts.

4. Copy the "Files\HomeAssistant\input_number.yaml" text into your input_number.

5. Copy the "Files\HomeAssistant\input_select.yaml" text into your input_select.

6. paste this into your lovelace configuration file:

⮡ Lovelace yaml mode: paste it easy in your ui-lovelace.yaml

⮡ Lovelace UI edit mode:

![](Files/lovelace_edit_ui.gif)
```txt
- input_select.musikbox_rfid
- entity: automation.mqtt_rfid_music_player_tag1
  name: Tag 1
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_tag2
  name: Tag 2
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_zuruck
  name: Zurück
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_pause
  name: Pause
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_uberspringen
  name: Skip
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_button3_help
  name: Help Button
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_led_ausschaten
  name: Led turn off
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_button1_hold_2sec
  name: Button 1 2sec
  tap_action: toggle
- entity: automation.mqtt_rfid_music_player_button2_hold_2sec
  name: Button 2 2sec
  tap_action: toggle
- type: divider
  style:
    height: 1px
    width: 80%
    margin-left: auto
    margin-right: auto
    background: '#0000FF'
- entity: script.mqtt_rfid_player_tag1_play
  name: Tag 1 abspielen
- entity: script.mqtt_rfid_player_tag2_play
  name: Tag 2 abspielen
- entity: script.mqtt_rfid_player_back
  name: Back
- entity: script.mqtt_rfid_player_next_track
  name: Nächster Track
- entity: script.mqtt_rfid_player_pause
  name: Pause
- entity: script.mqtt_rfid_player_led_off
  name: Led off
- entity: script.mqtt_rfid_player_reset
  name: Reset resume
```

7. Restart homeassistant and have fun 🤖
