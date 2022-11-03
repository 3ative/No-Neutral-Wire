# No-Neutral-Wire
 A guide to adding Home Assistant control to ANY Light switch (No need for extra Neutral wires OR special bulbs)

Watch the YouTube video here: https://youtu.be/KWMDE-plRAY


> :warning: Working domestic wiring IS DANGEROUS - Do not attempt if you're not confident or qualified. Always seek advice from a qualified electrician.

ESPHome Code:
```yaml
esphome:
  name: bathroom_light
  platform: ESP8266
  board: esp01_1m

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

# Enable logging
logger:

# Enable Home Assistant API
api:

ota:

# ** Internal sensing of Wall Switch - Don't show in HA **
binary_sensor:
  - platform: gpio
    pin:
      number: GPIO13
      mode: INPUT_PULLUP
    name: "Bathroom Light Switch"
    internal: true
    on_state:
      - switch.toggle: relay

switch:
  - platform: gpio
    name: "Bathroom Light"
    pin: GPIO12
    icon: mdi:ceiling-light
    id: relay
```

💖 Found this useful or want to say 'thanks' and support my efforts 💖
| Buy me a Coffee | PATREON |
|-----------------|---------|
| https://www.buymeacoffee.com/3ative | https://www.patreon.com/3ative |

🍺 CHEERS! 👍

