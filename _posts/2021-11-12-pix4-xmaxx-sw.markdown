---
layout:     post
title:      "pixhawk 4 rover software"
subtitle:   ""
date:       2021-11-12 12:00:00
author:     "gary ding"
header-img: "img/in-post/post-eleme-pwa/eleme-at-io.jpg"
header-mask: 0.3
catalog:    true
tags:
    - Robot 
    - Self-driving 
---

> pixhawk 4 rover software setup
> 

## Assumptions

- Assuming the rover and pix 4 wire has been completed.

- QGroundControl firmware update completed

- power is up 

### 1. 

QGroundControl desktop versions can install PX4 Pro or ArduPilot firmware onto controller boards. By default QGC will install the current stable version of the selected autopilot, but you can also choose to install beta builds, daily builds, or custom firmware files

First select the Gear icon (Vehicle Setup) in the top toolbar and then Firmware in the sidebar.

![](/img/in-post/qc_firmware_1.jpg)

For a Pixhawk-compatible board choose PIX4 Flight Stack radio buttons to download the current stable release.

![](/img/in-post/qc_firmware_2.jpg)

For rover purpose choose ArduRover xxx 

![](/img/in-post/qc_firmware_3.jpg)

Click the OK button to start the update.

The firmware will then proceed through a number of upgrade steps (downloading new firmware, erasing old firmware etc.). Each step is printed to the screen and overall progress is displayed on a progress bar

### 2. pixhawk 4 Airframe selection

QGroundControl allows rover-specific configuration by choosing the correct airframe. Select the Airframe tab.
Scroll down the list to find the Rover icon. 


![](/img/in-post/qc_firmware_4.jpg)


### 3. pixhawk 4 calibration

Please follow the official guide to complete the GPS, compass and remote control calibration.

### 4. Test X7 control for steering and throttle

Disable the preAlarm check for all and safety check turn on. As this point the GPS light should be solid red. 

Once the power is up for pix4 change the X7 joystick and you should see the xmaxx steering and throttle works.


## Common issues
### 1. QX7 not able to bind X8R. 
If the binding process is correct the X8R lef light should be green. However sometimes the light is solid red which means the bind failed.  check another article for this issue.

### 2. QX7 not able to control motor or steering.
If the binding between X7 and X8R is successful (green led) but motor or steering not working, check another article for this issue.

