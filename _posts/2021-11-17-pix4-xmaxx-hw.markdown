---
layout:     post
title:      "Pixhawk 4 rover hardware"
subtitle:   "Xmaxx assembly with Pixhawk 4 and Xavier"
date:       2021-11-17 12:00:00
author:     "bobd988"
header-img: "img/in-post/post-eleme-pwa/eleme-at-io.jpg"
header-mask: 0.3
catalog:    true
tags:
    - Robot
    - Self-driving 
---


> Steps to build Pixhawk 4 rover based on Traxxas xmaxx model with Jetson Xavier as Companion computer<br><br>
> 

## Goals
- Reference platform for multi-camera verification
- Reference platform for data driven verification 
- Reference platform for ML-Ops in real world
- Reference platform for creating training data   

## Parts List 

- Traxxas xmaxx Car platform 
- SparkFun FTDI Basic Breakout - 3.3V cable
- Trxxas 6700 Battery and 12A EZ Plus charger (6700)  
- Nvidia Jetson Xavier development board
- 25000 PC portable battery with 19V output 
- Delkin Devices Fat Gecko mini suction camera mount for 4 camera kit
- 55 mm spacers /standoffs
- 60 mm spacers /standoffs
- 35 mm spacers /standoffs
- Acrylic Plexiglas Sheet 1/4" x 12" x 24" 
- M3 screws x 10 mm
- M3 screws x 20 mm
- PIXHAWK 4 kit
- X8R receiver 
- Taranis QX7
- e-CAM20_CUXVR - Four Synchronized 4K Cameras
- Taranis X7 and X8R


### 1. Disassembly car 

xmaxx is a affordable platform to carry heavy equipment.   
![](/img/in-post/xmaxx.jpg)

We will install two layers of Plexiglas sheet to hold the pix4, xavier computer and camera kits.

The xmaxx ESC will be kept but the actual control wire will unplugged from original 2.4G receiver box and then connect to pix4 power board IO port pint 1 and 3.


### 2. Build bottom layer

Need standoffs to hold the PVC board. The holes will reuse existing one. However the front two holes will need to give thread.

![](/img/in-post/xmaxx-body-drill.jpg)



### 3. Build top layer

Create second platform to hold the camera set and also protect pix4 and computer. Here is how it looks like after finished

![](/img/in-post/xmaxx-body.jpg)

### 4. Wiring motor power

This is the standard wire diagram for pixhawk 4 to connect accessories.  

![](/img/in-post/pixhawk4.jpg)

The standard rover wire diagram is like this

![](/img/in-post/pix4-wire.png)

As xmaxx has two battery combined to provide high voltage. The wires needs to be designed to match the PM07 power board.

![](/img/in-post/xmaxx-wire.png)

The PM07 board to connect ESC actual wiring is like this. The connector is trx female connector.

![](/img/in-post/xmaxx-pm07.jpg)

The PM07 board to connect battery wiring is like this. The connector is trx male connector

![](/img/in-post/xmaxx-battery.jpg)


after completion the xmaxx is like this

![](/img/in-post/xmaxx-complete.jpg)

### 5. Wiring Xavier power

The battery for Xavier is Krionia 25000mAH battery which can output 19V voltage.
The power cable connect the output of battery directly to Xavier.

### 6. Wiring ECS and Steering cable

The xmaxx ESC and steering cables can be found by open the carrier box. 

![](/img/in-post/xmaxx-esc-cable.jpg)

The left side cable is the ESC and right side cable is the steering cable. We unplug these two cables from receiver and will connect them to PM07 GPIO pin 1 and 3. 

### 7. Xavier connect to pix4 

In order to make Xavier connect with PIX4 the UART is needed. From pix4 normally telem2 is used for this purpose.  A  cable is needed to be created for this purpose.


 From Xavier side the ports are:

Jetson Xavier GPIO Pin 6 (GND) → Cable GND (Black Wire)
Jetson Xavier GPIO Pin 8 (UART1_TX) → Cable RXD (White Wire)
Jetson Xavier GPIO Pin 10 (UART1-RX) → Cable TXD (Green Wire)

![](/img/in-post/xmaxx-uart.jpg)


