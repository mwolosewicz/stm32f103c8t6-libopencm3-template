# BluePill STM32F103c8 board template
This repository contains simple template for [STM32F103C8T6 BluePill](https://stm32-base.org/boards/STM32F103C8T6-Blue-Pill.html "BluePill") board. This template contains simple LED blink using the FreeRTOS system. Don't hasitate to use it to build your own project on top.

## Software prerequisites
Before build of the project you need some tools:

* *Cross compiler* - this project use `gcc-arm-none-eabi` for building software. *(For Ubuntu call: `sudo apt install gcc-arm-none-eabi`)*.
* *ST-Link* - you need [ST-Link](https://github.com/stlink-org/stlink "ST-Link") tools for flashing the device. *(For Ubuntu call: `sudo apt install st-util`)*

Make sure that in `/etc/udev/rules.d/` there are the *stlink* rules. If not - the rules can be found at [ST-Link](https://github.com/stlink-org/stlink "ST-Link") library page.

### FreeRTOS
The FreeRTOS files are commited into the repository. If you wish - you can update FreeRTOS version for yourself.

# Building
The building process consists of following steps:

* Initialize submodules: `git submodule init`.
* Update submodules: `git submodule update`.
* Build *libopencm3* - to do so call `make libs`.
* Build project: `make`.
* Flash the project to the board: `make flash`.

## Cleaning
There are two options for cleaning:

* `make clean` - clean all object, binary files, etc but not *libopencm3*.
* `make distclean` - clean all, including libopencm3 build. After this call, the *libopencm3* library must be rebuild using `make libs`.

# Credits
This project was build based on the [Warren's Gay](https://github.com/ve3wwg/stm32f103c8t6 "Warren's Gay repo") repository. It's stripped to create the lightest option possible.
