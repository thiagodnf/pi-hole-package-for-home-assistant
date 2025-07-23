# Pi-hole Package for Home Assistant

Pre-configured Home Assistant package for Pi-hole via REST API. Adds sensors, control buttons, and groups them under one single file

[![GitHub Release](https://img.shields.io/github/release/thiagodnf/pi-hole-package-for-home-assistant.svg)](https://github.com/thiagodnf/pi-hole-package-for-home-assistant/releases/latest)
[![GitHub contributors](https://img.shields.io/github/contributors/thiagodnf/pi-hole-package-for-home-assistant.svg)](https://github.com/thiagodnf/pi-hole-package-for-home-assistant/graphs/contributors)
[![GitHub stars](https://img.shields.io/github/stars/thiagodnf/pi-hole-package-for-home-assistant.svg)](https://github.com/almende/thiagodnf/pi-hole-package-for-home-assistant)
[![MIT Licence](https://badges.frapsoft.com/os/mit/mit.svg?v=103)](https://opensource.org/licenses/mit-license.php)
[![Open Source Love](https://badges.frapsoft.com/os/v1/open-source.svg?v=103)](https://github.com/ellerbrock/open-source-badges/)


## 📦 Features

This projects contains the following features:

- Sensors for:
  - Total queries
  - Blocked queries
  - % blocked
  - Active clients
  - Domains being blocked
  - Last gravity update (timestamp)
- Switch Buttons for:
  - Enable/disable blocking 
- Scripts for:
  - Update gravity

## 📁 File Structure

```
custom_components/
packages/
    pihole.yaml         # Main package file
secrets.yaml            # Required secrets
configuration.yaml      # Must include the package
```

## Setting it up

Step 1. Create a secret value and replace by the correct `sid` and `csrf` values.

```yaml
pihole_sid: "yourSid="
pihole_csrf: "yourCsrf="
```

Step 1. Create a new file using the file structure 

Step 3. Change the IP address for your pi-hole server


S
