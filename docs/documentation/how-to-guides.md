---
layout: default
title: How-To Guides
parent: Documentation
nav_order: 3
---
---
# How-To Guides
We are using various tools, electronic components, and building material. These guides are how to use them.

---------------------------------------------------------------------------------------------------
## Table of Contents


- [Compiling and Loading Device Tree Overlay for BBBMini - BeagleBone ArduPilot DIY Cape](#compiling-loading-DTO-for-BBBMini)

 --------------------------------------------------------------------------
 
###  **Compiling and Loading Device Tree Overlay for BBBMini - BeagleBone ArduPilot DIY Cape** <a name="compiling-loading-DTO-for-BBBMini"></a>
---

1. Clone and compile the dtc - device tree compiler `git clone git://git.kernel.org/pub/scm/utils/dtc/dtc.git`
2. Change the directory `cd dtc`
3. Make `make`
4. Install `make install`
5. Check the version `dtc --version`
	The return shoud be `version 1.6.1`
6. Change Directory `cd ~`
7. Clone BeagleBoard's device tree `https://git.beagleboard.org/beagleboard/BeagleBoard-DeviceTrees.git`
8. Change the directory `cd BeagleBoard-DeviceTrees`
9. Checkout the v5.10.x-ti-unified `git checkout v5.10.x-ti-unified`
10. Get the dts updated `https://raw.githubusercontent.com/juvinski/BBBMINI_V2/main/DeviceTreeOverlay/am335x-boneblack-bbbmini.dts -O src/arm/am335x-boneblack-bbbmini.dts`
11. Make `make`
12. Install `sudo make install_arm`
13. Check the new dtb file `ls /boot/dtbs/5.10.109-bone-rt-r63/am335x-boneblack-bbbmini.dtb` - should return file path and name
14. Change the uEnv file ` vi /boot/uEnv.txt`
15. Change the lines:
	Add the dtb file: `dtb=am335x-boneblack-bbbmini.dtb`
	Comment the uboot_overlay: `#enable_uboot_overlays=1`
	Uncomment the PRU overlay: `uboot_overlay_pru=AM335X-PRU-UIO-00A0.dtbo` - all other dtbo for PRU must be commented
16. Save the file `esc + :x!`
17. Reboot
18. After the boot, to ensure the dtb was loaded run a `ls /dev/spidev*` 
	The return should be `/dev/spidev* /dev/spidev0.0  /dev/spidev1.0  /dev/spidev1.1`
19. Proceed to ardupilot compilation
