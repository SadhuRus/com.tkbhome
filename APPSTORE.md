# TKB Home
This app adds support for TKB Home devices in Homey.

## Supported devices:
+ TSM02 - 4-in-1 Multi Sensor
+ TSP01 - 3-in-1 Multi Sensor
+ TZ35 - Single & Double Wall Dimmer
+ TZ36 - Single & Double Wall Switch
+ TZ37 - Double Relay Wall Switch
+ TZ55 - Single & Double Wall Dimmer
+ TZ56 - Single & Double Wall Switch
+ TZ57 - Double Relay Wall Switch
+ TZ65 - Single & Double Wall Dimmer
+ TZ66 - Single & Double Wall Switch
+ TZ67 - Wallplug Dimmer (all types)
+ TZ67-PLUS - Wallplug Dimmer (Z-Wave Plus) (all types)
+ TZ68 - Wallplug Switch (all types)
+ TZ68-PLUS - Wallplug Switch (Z-Wave Plus) (all types)
+ TZ69 - Smart Energy Wallplug (Z-Wave Plus) (all types)
+ TZ88 - Smart Energy Wallplug (Z-Wave Plus) (all types)

## Supported Languages:
* English
* Dutch (Nederlands)

### Notes:
**TZ35/TZ55/TZ65**
The Wall Dimmers need to be polled to get the correct dim state when you dim it with the switch itself.  
The interval is by default on 300 seconds (5 minutes).  
It is not recommended to put this below 60 seconds (1 minute), it might cause too much traffic.  
You can also "immediately" update its state in homey, by just pressing any of the switches once.  
The dim level takes about 2.5 seconds to update when switching on, since the dimmer dims up to its set brightness.  

**TZ67(-PLUS)/TZ68(-PLUS)/TZ69**
The wallplugs only use the polling interval if you use the button on the wallplug itself.  
It is not recommended to put this below 60 seconds (1 minute), it might cause too much traffic.

**TZ88**
It sends the wattage value when the load changes (more then) 5%.  
This can't be edited and could cause a lot of data if the load changes the power usage a lot.  
All other manufacturers have this on at least 20% for this reason, so do keep this in mind.  
The voltage and amperage don't get reported on intervals, added polling for this (by default poll is off to save traffic).

## Change Log:
**2.0.1:**
- Fixed a crash caused by a typo in the TSP01/TSM02 setting parsers

**2.0.0:**
- Full rewrite to SDKv2;
- Fixed Meter Reset flow cards (TZ69 & TZ88);
- Added (bad) manufacturer ID TZ67;
- Added flow cards TZ37/TZ55

Rest of the change log can be found [here](https://github.com/caseda/com.tkbhome/blob/master/README.md).