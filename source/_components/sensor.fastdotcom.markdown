---
layout: page
title: "Fast.com"
description: "How to integrate Fast.com within Home Assistant."
date: 2016-08-10 17:30
sidebar: true
comments: false
sharing: true
footer: true
logo: fastdotcom.png
ha_category: System Monitor
featured: false
ha_release: 0.26
---

The `fastdotcom` sensor component uses the [Fast.com](https://fast.com/) web service to measure network bandwidth performance.

By default, it will run every hour.  The user can change the update frequency in the config by defining the minute, hour, and day for a speedtest to run.

To add a Fast.com sensor to your installation, add the following to your `configuration.yaml` file:

Once per hour, on the hour (default):

```yaml
sensor:
  - platform: fastdotcom 
```

More examples:

Every half hour of every day:

```yaml
sensor:
  - platform: fastdotcom
    minute:
      - 0
      - 30
```
Configuration variables:

- **minute** (*Optional*): Specify the minute(s) of the hour to schedule the speedtest. Use a list for multiple entries. Default is 0.
- **hour** (*Optional*): Specify the hour(s) of the day to schedule the speedtest. Use a list for multiple entries. Default is None.
- **day** (*Optional*): Specify the day(s) of the month to schedule the speedtest. Use a list for multiple entries. Default is None.

There is also a service named `sensor.update_fastdotcom` that you can use to run a fast.com speedtest on demand.
