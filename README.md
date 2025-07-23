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

## 🔧 Setup Instructions

**Step 1.** Add your Pi-hole credentials to `secrets.yaml`:

```yaml
pihole_sid: "yourSid="
pihole_csrf: "yourCsrf="
```

**Step 2.** Create the package file following the project file structure.

## 📁 File Structure

```
custom_components/
packages/
    pihole.yaml         # The the package file here
secrets.yaml            # Required secrets
configuration.yaml      # Must include the package
```

**Step 3.** Update the `configuration.yaml` file adding the following:

```yaml
homeassistant:
  packages: !include_dir_named packages
```

**Step 3.** Update the Pi-hole server IP address in the package configuration. For instance:

From:

```yaml
rest_command:
  update_gravity:
    url: "<PIHOLE_SERVER_URL>/api/action/gravity"
    method: POST
    headers:
      "X-FTL-SID": !secret pihole_sid
      "X-FTL-CSRF": !secret pihole_csrf
    timeout: 120
```

To:

```yaml
rest_command:
  update_gravity:
    url: "192.168.1.72/api/action/gravity"
    method: POST
    headers:
      "X-FTL-SID": !secret pihole_sid
      "X-FTL-CSRF": !secret pihole_csrf
    timeout: 120
```

