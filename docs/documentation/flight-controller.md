---
layout: default
title: Using Beagle as a Flight Controller
parent: Documentation
nav_order: 2
---
# Using Beagle as a Flight Controller
Beagle-Flap Flight Control System - Hardware and PCB Design

---

## Ardupilot on Beagle
[https://openbeagle.org/ardupilot-on-beagle](https://openbeagle.org/ardupilot-on-beagle)



- BeagleBoard.org mentored the original port of ArduPilot to Linux in 2014 as part of
Google Summer of Code
       
      - BeagleBone Black + Erle Cape or Pixhawk Fire Cape

- Mirko Denecke and ArduPilot community continued work

      - 2015: BBBmini Cape for BeagleBone Black and SeeedStudio BeagleBone Green
      - 2017: Support for BeagleBone Blue
      - 2018: PocketPilot PocketCape for PocketBeagle
      - 2022: BBBMINI V2 Juvinski

It was really intresting to see the BBBmini port which is on beagle bone black with a much much cheaper simpler sensor board on the top more of a sort of Do-it-yourself cape put together and the patch was really nicely structured the entire patch to add support for ardupilot within 43 lines tiny. It looking like it would be easy to throw together another one that's easier and cheaper for people to put together on top of the Beagle.


