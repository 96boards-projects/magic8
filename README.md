---
# Front Matter
# Title of your project used for the breadcrumb title and meta title.
title:  Magic 8 Ball

# Permalink your project will reside under on the 96boards.org website.
# separate your title's words with dashes for SEO purposes.
permalink: /projects/magic8/
author: 96Boards

# Add a description of your project
description: The Digital Hourglass project implements a count up timer which takes in user input for the time to be measured and prints a character on the display at certain intervals till the time is up. The project goes through some of the basic concepts like connecting the Sensors Mezzanine board with the DragonBoard, interfacing an LCD with the board and installing the necessary libraries.

# Add the names of your images which are stored in the sub folders here.
# The first image is always used in the table at /projects/
# This section is used to add a social media share image to your project.
# Place the image you'd like to use when sharing on social media in the /assets/images/projects/
# folder and adjust the following YAML accordingly.
# High Res 1920 x 1080
# regenerated on site build
image: 
    path: /assets/images/projects/placeholder.png
#    list:
#        - thumb.png
#        - share.png
#social:
#  name: 96Boards
#  links:
#    - https://twitter.com/96boards
#    - https://www.facebook.com/96Boards/
#    - https://www.linkedin.com/company/96boards/
#    - https://plus.google.com/+96Boards
#    - https://github.com/96boards
project:
    # Difficulty level for your project <Beginner, Intermediate, Experienced>
    #difficulty_level:
    # - Beginner
    # Boards that you have used in this project. For a full list of boards see 
    # this file in the 96boards/website repo - _data/boards.yml
    boards_used: 
        - dragonboard410c
        - sensors-mezzanine
    # Verticals are catagories that your project belongs to. For a full list of verticals see 
    # this file in the 96boards/website repo - _data/verticles.yml
    verticals:
        - Maker
#Optional tags for your projects: meta-key words
tags:
- dragonboard410c
- sensors-mezzanine
---

# Magic 8 Ball
The Magic 8 Ball application displays messages on the LCD when the touch sensor module is tapped.
There are 20 statements out of which any one can appear randomly at each tap on the sensor. So ask away!


# Table of Contents
- [1) Hardware](#1-hardware)
   - [1.1) Hardware Requirements](#11-hardware-requirements)
   - [1.2) Hardware Setup](#12-hardware-setup)
- [2) Software](#2-software) 
   - [2.1) Operating System](#21-operating-system)
   - [2.2) Package Dependencies](#22-package-dependencies)
- [3) Building and Running](#3-building-and-running)
- [4) Conclusion](#4-conclusion)

# 1. Hardware
   
## 1.1 Hardware requirements:

1. [DragonBoard 410c](http://www.96boards.org/product/dragonboard410c/)
2. [Power Supply](https://www.amazon.com/Adapter-Regulated-Supply-Copper-String/dp/B015G8DZK2)
3. [Sensors Mezzanine](http://www.96boards.org/product/sensors-mezzanine/)
4. [Micro USB Cable](https://www.amazon.com/AmazonBasics-USB-Male-Micro-Cable/dp/B01EK87A82/ref=sr_1_3?ie=UTF8&qid=1497618343&sr=8-3&keywords=micro%2Busb&th=1)
5. [Grove-LCD 16x2 RGB Backlight](https://www.seeedstudio.com/Grove-LCD-RGB-Backlight-p-1643.html)
6. [Grove Touch Sensor Module](https://www.seeedstudio.com/Grove-Touch-Sensor-p-747.html)

## 1.2 Hardware Setup:
To begin, connect the Sensors Mezzanine board onto the DragonBoard via the low-speed expansion connector on both boards. Use the Grove Universal 4 pin cables to connect the LCD to I2C0 and the Touch sensor module onto GPIO G3. You can find an image of the setup in the images folder. That’s it! We’re all set to run our application.

# 2. Software

## 2.1 Operating System

- [Linaro Debian based OS (latest)](https://github.com/96boards/documentation/blob/master/ConsumerEdition/DragonBoard-410c/Downloads/Debian.md)

## 2.2 Package Dependencies

1. MRAA Library
```
$ sudo apt-get install libupm-dev
```
2. UPM Library
```
$ sudo apt-get install libmraa-dev
```

# 3. Building and Running:

```shell
$ git clone https://github.com/96boards-projects/magic8.git
$ cd projects
$ cd magic8
$ make
$ ./magic8
```

# 4. Conclusion:

When the executable is run, the application displays an initial message on the LCD and waits for the sensor to be tapped.
With each tap, a new statement is displayed. These statements can be modified by the user in the code.
