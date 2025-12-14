# No Neutral Wire Smart Bulb
 A guide to adding Home Assistant control to ANY Light switch (No need for extra Neutral wires OR special bulbs)
Watch the YouTube video here: https://youtu.be/KWMDE-plRAY
> :warning: Working domestic wiring IS DANGEROUS - Do not attempt if you're not confident or qualified. Always seek advice from a qualified electrician.

ESPHome Code:
```yaml
esphome:
  name: bathroom_light

esp8266:
  board: esp01_1m

wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password

# Enable logging
logger:

# Enable Home Assistant API
api:
ota:
  platform: esphome

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

---

<div align="center">

### 💖 Support This Project

Found this useful? Want to say thanks and fuel future creations?

**Your support keeps the creativity flowing!** 🍺✨

<table>
  <tr>
    <td align="center">
      <a href="https://www.buymeacoffee.com/3ative">
        <img src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-Support-yellow.svg?style=for-the-badge&logo=buy-me-a-coffee&logoColor=white" alt="Buy Me A Coffee"/>
        <br/>
        <b>☕ Buy me a Coffee</b>
      </a>
    </td>
    <td align="center">
      <a href="https://www.patreon.com/3ative">
        <img src="https://img.shields.io/badge/Patreon-Become%20a%20Patron-red.svg?style=for-the-badge&logo=patreon&logoColor=white" alt="Patreon"/>
        <br/>
        <b>💖 Join on Patreon</b>
      </a>
    </td>
  </tr>
</table>

**Every contribution helps bring more awesome projects to life!** 🚀

</div>

---
