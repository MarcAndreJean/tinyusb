# tinyusb #

## What Is tinyusb ##

tinyusb is an open-source (BSD-licensed) USB Host/Device/OTG stack for embedded micro-controller. It is developed using [Test-Driven Development (TDD)](tests/readme.md) approach to eliminate bugs as soon as possible.

![tinyusb diagram](/docs/images/what_is_tinyusb.png)

## Features ##

designed to be simple and run out-of-the-box provided the configuration is correct.

### Host ###

- HID Mouse
- HID Keyboard
- HID Generic (comming soon)
- Communication Device Class (CDC)
- Mass Storage Class (MSC)
- Hub
    - Only support 1 level of hub (due to my laziness)

### Device ###

- HID Mouse
- HID Keyboard
- HID Generic (comming soon)
- Communication Class (CDC)
- Mass Storage Class (MSC)

### RTOS ###

tinyusb is designed to be OS-ware and run across RTOS vendors, thanks to its OS Abstraction Layer (OSAL). However, it can also run without an RTOS (OSAL will be expanded to be a state machine in this case). Currently the following OS can be run with tinyusb (out of the box).

- **None OS**
- **FreeRTOS**
- **CMSIS RTX**

## Getting Started ##

coming soon ...

## Supported MCUs ##

- NXP 
  - LPC11uxx
  - LPC13uxx (12 bit ADC)
  - LPC175x_6x
  - LPC43xx

## Supported Toolchains ##

The following toolchain is supported

- *lpcxpresso/redsuite*
- *Keil MDK*
- *IAR Workbench*

## Supported Boards ##

this code base can run out of the box with the following boards

### NXP LPC43xx ###

- [Embedded Artists LPC4357 OEM & Base board](http://www.embeddedartists.com/products/kits/lpc4357_kit.php)
- [NGX Technologies LPC4330 Explorer](http://shop.ngxtechnologies.com/product_info.php?products_id=104)
- [Keil MCB4357 Evaluation Board](http://www.keil.com/mcb4300)

## Known Issues ##

- LPC11uxx & LPC13uxx cannot able to STALL Control OUT endpoint !!! --> unsupported with data out request may cause host stuck with control transfer forever. (reproduce: enable keyboard + mouse, return error in set report of hid_device)

## How Can I Help ##

If you find my little USB stack is useful, please take some time to file any issues that you encountered. It is not necessary to be a software bug, it can be a question, request, suggestion etc. We can consider each github's issue as a forum's topic. Alternatively, you can buy me a cup of coffee if you happen to be in Hochiminh city.

## License ##

BSD license for most of the code base, but each file is individually licensed especially those in /vendor folder. Please make sure you understand all the license term for files you use in your project.
