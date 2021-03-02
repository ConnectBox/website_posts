**The following document explains how to build the firmware for a ConnectBox.
**This can be done on  a Windows machine with VirtualBox running Linux or on a Mac or a Raspberry Pi 3+ 4

<a href="https://github.com/ConnectBox/connectbox-pi/blob/master/doc/making_an_image.md">Makind A ConnectBox Software Image</a>
&nbsp;
After making the firmware, you need to have hardware configured for the firmware.
Hardware made with a NEO Pi from FriendlyArm usually uses a RTL8812au WiFi dongle to provide the WiFi connection.  Other WiFi modules can be used as well if they are supported by the Operating system or you install the device driver into the OS.  Battery units use a custom PCB that contains the RTL8812AU WiFi module as well as battery management hardware to charge/manage the charge level as well as a 0.98" I2C display and 2 buttons.  You can find the circuit diagram under the Github repository.  Additionally, you can 3D Print your case, for large volume production we have designed a battery version case to contain the custom PCB and the NEO Pi processsor.

Secondly you can build the firmware for a Raspberry Pi.  This includes the Model Zero through the Model 4.  When using the Raspberry Pi, there is a limit of how many users can use the built in WiFi port.  We continue to recommend that you use an external WiFi module to provide better connection for users.  If an external WiFi module  is used then the internal module can be used for connection to a WiFi Access Point for internet connectivity.  This will NOT be passed on (bridged) to the users, but for the administrator can be used to update and modifiy the media content.

Contact help@connectbox.org if you have other questions regarding the software or hardwarae.

WiFi Modules that have been tested and used include:&nbsp;

-Module|Manufacturer
-RT5372 |by Realtek /*&nbsp;
-RTL8192CU|by Realtek  /*&nbsp;
-MT7601U|by Realtek&nbsp;
-RT8812AU|by Realtek&nbsp;
-WUSB6100M|by Linksys  /*&nbsp;


/*Prefered Units&nbsp;
