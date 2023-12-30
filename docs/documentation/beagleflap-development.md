---
layout: default
title: Beagle Flap Development
parent: Documentation
nav_order: 1
---
# Developing the flapping wing aerial robot
This page follows the development of the Beagle Flap.

---

## Flapping Mechanism

Flapping mechanism is to convert the rotary motion of motor into the reciprocating motion of flapping wings. The basis for this mechanisms is the “crank-rocker” type of four-bar linkage. Here, the motor drives a rotating crank. The crank has a connecting rod attached to it, and the other end of the connecting rod is attached to the wing. As the crank goes around, the connecting rod pushes the wing spar to flap up and down at the hinge point.

![Crank-Rocker Four Bar Link Mechanism](https://upload.wikimedia.org/wikipedia/commons/5/5d/Crank-Rocker_4-bar_Linkage.gif)

A type of four bar link mechanism which from a side rotates a complete rotation and from the other rotates by a limited rotation.


This system is complex to design and fabricate because it must withstand vast forces which reverse direction several times a second while at the same time being extremely light, durable and also provide a fairly symmetrical wing motion so the flapping wing UAV flies straight.

There are many kinds of [flapping mechanisms](https://ornithopter.org/how.flap.shtml). Here, I chooses to design a variation of the dual crank mechanism `Transverse drive shaft` with cranks at either ends and this mechanism allows for symmetric wing motion. The rotating gears and the flapping wings are not on the same plane thus the connector rod has to be able to rotate. The connector rod has a ball bearing inside, and this adds weight to just the component itself. The number of gears used in this design is more than any other design. The transverse shaft design is usually used for large ornithopters where weight could be overcome by large wings.

## Flapping Gear System

Developing a Flapping Gear system for Eagle-Inspired motion.

The gear system is to convert the rotary motion of the motor into flapping motion. Here this is accomplished by using crank-rocker type of four-bar linkage mechanism along with a gear reduction.

The core of the flapping mechanism design is a variation of the dual crank mechanism Transverse drive shaft with cranks at either ends and the gear box consists of three Acrylic plates/frames of 3mm thickness cut to the shape required to house the motor, gears, linkage and flapping arms. Here set of plates, together with bridging 5mm spacer,that creates a protected space that fully encompasses the transmission with the brush less out-runner motor slightly protruding on one side.

There is small pinion gear for the motor, an intermediate gear that increases the gear ratio, and a large output gear that further increases the total gear ratio of the mechanism. The gear reduction between the driving motor and flapping mechanism is necessary because the motor operating revolutions per minute(RPM) are much higher than the desired flapping frequency. To achieve the eagle's flapping frequency of 5Hz.

Here I explain the design. Since I use a transverse shaft design. To achieve the desired rotational speed (i.e, flapping frequency) I used 2 pair of gears (gear **A** + gear **B** and gear **C** + gear **D**). So it is a gear system with two stages of reduction.

       (A + B)(C + D)

       It is a reduction ratio gear design.

          Gears:
          
               A = 12T (Driver Gear)
               B = 83T
               C = 12T
               D = 64T (Driven, end gear)

       Here we using 1850KV motor powered by 7.4V

              1500KV = 1500*7.4(2s)
                     = 11100 revolutions per minute 
          or 11100/60 = 185 revolutions per second

So, In order to achieve desired rotational speed (i.e, flapping frequency) two stage of reduction ratio applied.

**Calculation**: Total reduction ratio

       The total reduction ratio is the product of the first stage of reduction and the second stage of reduction.

              B:A - 1st stage reduction
              D:C - 2nd stage reduction

       (B/A)*(D/C) = (83/12)*(64/12) = 36.5

       It means that the total reduction ratio is 1 : 36.5

       To find the speed of end gear D (Driven Gear)

       Speed of end-gear (driven D gear) = Speed of Driver gear A in sec * 1/Total reduction ratio

       185 * 1/ 36.5 = 5.06 revolutions per second

Here, revolutions per second = flap's per second (i.e, flapping frequency)



