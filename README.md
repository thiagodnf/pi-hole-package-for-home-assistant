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

**Step 2.** Create a folder named "packages" and place `pihole.yaml` inside it, following the structure below.

```
custom_components/
packages/
    pihole.yaml         # Add the package file here
secrets.yaml            # Required secrets
configuration.yaml      # Must include the package
```

**Step 3.** Update the `configuration.yaml` file adding the following:

```yaml
homeassistant:
  packages: !include_dir_named packages
```

**Step 3.** Open `pihole.yaml`, locate all instances of `<PIHOLE_SERVER_URL>`, and replace them with the actual IP address or hostname of your Pi-hole server. For example:

From:

```yaml
url: "<PIHOLE_SERVER_URL>/api/action/gravity"
```

To:

```yaml
url: "192.168.1.72/api/action/gravity"
```

