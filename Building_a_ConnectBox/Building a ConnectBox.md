#Building a ConnectBox

## Making Your Own ConnectBox

The easiest way to build a ConnectBox is to simply download a prepared image of the ConnectBox software for the flavor of your device (*NanoPi NEO* or *RPi*), burn that image to a uSD card, put the card in your device, add an antenna and power up. There are currently both NEO ([v20201007a](https://github.com/ConnectBox/connectbox-pi/releases/tag/v20201007a)) and RPi ([RPi_v20210301](https://github.com/ConnectBox/connectbox-pi/releases/tag/RPi_v20210301)) versions available on this website. If you have an interest in compiling your own image, see the document *making_an_image.md* document ([Making an Image](https://github.com/ConnectBox/connectbox-pi/blob/master/docs/making_an_image.md)) for detailed instructions. 

###The following articles explain how to build the firmware for a ConnectBox. This can be done on a Windows or Mac machine with VirtualBox running Linux or on a Raspberry Pi 3+ or 4.


## Building a ConnectBox image

The *making_an_image.md* document (see [Making an Image](https://github.com/ConnectBox/connectbox-pi/blob/master/docs/making_an_image.md)) is a detailed update of the process used to build an image from the source codes residing on GitHub/ConnectBox. It covers all aspects of the task from describing an overview of the process, to step by step instructions for creation of the *workstation* (both Mac and RPi flavors), and building both NEO and RPi images of the ConnectBox. 

## Connectbox setup and administration

The *administration.md* and *administration_rpi.md* documents (see [Administration Docs](https://github.com/ConnectBox/connectbox-pi/blob/master/docs/administration.md) and [Administration Docs for RPi](https://github.com/ConnectBox/connectbox-pi/blob/master/docs/administration_rpi.md)) are the source documents for the *README.txt* default media content deployed on the NEO and RPi based ConnectBoxes.

## Developing the ConnectBox Software

The *development.md* document (see [Development Docs](https://github.com/ConnectBox/connectbox-pi/blob/master/docs/development.md)) gives good guidelines on the tools and methodology used in developing and enhancing the software used on the ConnectBox.

## Deploying the ConnnectBox Software

The *deployment.md* document (see [Deployment Docs](https://github.com/ConnectBox/connectbox-pi/blob/master/docs/deployment.md)) was the original document describing the development process and tools used in creating and deploying the ConnectBox software. 
<a href="https://github.com/ConnectBox/connectbox-pi/blob/master/doc/making_an_image.md">Makind A ConnectBox Software Image</a>
&nbsp;

## Hardware Configuration

After making the firmware, you need to have hardware configured for the firmware.
Hardware made with a **NEO Pi** from FriendlyArm usually uses a RTL8812au WiFi dongle to provide the WiFi connection.  Other WiFi modules can be used as well if they are supported by the Operating system or you install the device driver into the OS.  Battery units use a custom PCB that contains the RTL8812AU WiFi module as well as battery management hardware to charge/manage the charge level as well as a 0.98" I2C display and 2 buttons.  You can find the circuit diagram under the Github repository.  Additionally, you can 3D Print your case, for large volume production we have designed a battery version case to contain the custom PCB and the NEO Pi processor.

Secondly you can build the firmware for a **Raspberry Pi**.  This includes the Model Zero through the Model 4.  When using the Raspberry Pi, there is a limit of how many users can use the built in WiFi port.  We continue to recommend that you use an external WiFi module to provide better connection for users.  If an external WiFi module  is used then the internal module can be used for connection to a WiFi Access Point for internet connectivity.  This will NOT be passed on (bridged) to the users, but for the administrator can be used to update and modifiy the media content.

Contact *help@connectbox.org* if you have other questions regarding the software or hardware.

WiFi Modules that have been tested and used include:&nbsp;

- Module | Manufacturer
- ***RT5372 | by Realtek*** 
- ***RTL8192CU | by Realtek***
- MT7601U | by Realtek
- RT8812AU | by Realtek
- ***WUSB6100M | by Linksys*** 


***Prefered Units***