# Pi-hole Package for Home Assistant

Pre-configured Home Assistant package for Pi-hole via REST API. Adds sensors, control buttons, and groups them under one single file

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
