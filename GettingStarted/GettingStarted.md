# Getting Started Guide to Your ConnectBox

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/cb_icon.png" alt="ConnectBox" width="150">

[DOWNLOAD THIS GUIDE AS PDF](https://github.com/ConnectBox/website_posts/raw/master/GettingStarted/ConnectBox-GettingStarted_V4.pdf)


This ConnectBox is nearly ready to go already. Just a few things that you need to do first to make the end user experience useful.

## Initial Administration / Setup

- ConnectBox comes with system software. No content is included. You'll need to add your own content to the device using the guidelines in the section

- Your ConnectBox comes with an internal lithium-ion battery. To charge the battery, you'll need to connect up a 1A or greater microUSB charger like are found with many cell phones. From charging from an empty to full battery, expect it to take around 2 - 5 hours. Your ConnectBox has built-in low battery protection which prevents the battery from going into deep discharge.

PLEASE FULLY CHARGE YOUR CONNECTBOX BEFORE THE FIRST USE

- With the microUSB charger plugged in or with a relatively full battery, turn your unit on using the switch on the side of the unit. Allow a **minute** or two to pass before using a wireless device to locateand join the default wireless network called _ConnectBox - Free__Media_

_Note: if you are connecting from a mobile device it may &#39;validate the internet connectivity and/or check if a login is required for the network join&#39;. In this case it may show a web browser window that say&#39;s to connect to_ [http://connectbox](http://connectbox/)_. In some cases you may need to go to the &#39;more&#39; menu and &#39;keep the connection&#39; – close the default browser and re-open a web browser on the device and enter_ [http://connectbox](http://connectbox/) _in the URL window. This should open the default front page of the Connectbox._

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/first_run.png" alt="First Run" width="300">


1. Navigate to the Administration area: [http://connectbox/admin](http://connectbox/admin) (or press the cog icon on the bottom right of the screen) and login with the default Connectbox credentials (username and password are casesensitive):

  - username: admin
  - password: connectbox

_Recommended_: Change the password for the Administration area. Go to the Configure Menu and select Password. Enter a new password and press submit. When you next try to enter the admin portal of the Connectbox, you will be prompted to login again. Use the new password when this happens.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin1.png" alt="Admin Area" width="300">
<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin2.png" alt="Admin Area" width="300">

## Optional Admin Setup Items

_HOSTNAME_:

Change the name of the hostname (by default this is `connectbox`) to something of your own choosing. From the admin menu, go to (Configure -> Hostname). This only appears in the location bar of the browser. If you are changing the hostname, you will need to use the new [http://hostname](http://hostname/) for the default web page, or [http://hostname/admin](http://hostname/admin) for the administrative area. Additionally, new login credentials will be asked for.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin3.png" alt="Admin Area" width="300">

- _WiFi__SSID_:

Change the name of the wireless network. (Configure -> SSID). When you do this, you will be disconnected from the wireless network and you will need to locate and join the newly named wireless network.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin4.png" alt="Admin Area" width="300">

- _WiFi__Channel_:

Change the WiFi channel to something that might be less congested in your area. (Configure -> Channel) Your choices are channels 1 – 11 from the dropdown menu. When you change the WiFi channel, you will temporarily be disconnected form the Connectbox until your device reconnects to the WiFi SSID on the new channel.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin5.png" alt="Admin Area" width="300">

- _Icon-Only UI Banner Message_:

If you perhaps would like to share with your connected users some sort of banner message (e.g., contact info or organization name) you can set this from the (Configure -> Banner Message) menu item. This box accepts input as either plain text or as html formatted. An example of something that would produce a banner that looks like this:

Brought to you by: **Global Tech Team**

+1-800-555-1212 _(USA)_

Using the html format of:

```
<p>Brought to you by: <span style="color: #008000;"><strong>Global Tech Team</strong></span></p><p>+1-800-555-1212 <em>(USA)</em></p>
```

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin6.png" alt="Admin Area" width="300">

- _Enabling Custom_ _Web_ _Interface:_

By default, your ConnectBox is configured to run using what we call the "Icon-Only User Interface". In this mode, the content that is displayed in your end user's browser looks similar to a file explorer window. Each piece of media located on your USB flash disk is displayed as a file or folder allowing navigation into subfolders. This is the perfect option for content that is perhaps dynamic where you may be adding in new files each day and you don't want to necessarily worry about having to format the display. Just add in your new media files, turn on the device and it will display it.

For groups that would like a more customized look to the interface, they can put onto the media storage space a file that has to be named: **index.htm** This file would obviously need to be a html formatted file that can display icons, images, do text enhancements, link to a CSS file, etc.

However, from the ConnectBox Administration menu, you do need to trigger this mode by going to (Configuration -> Static site) and clicking the `On` button then clicking update. Reboot the device after the change for it to be enabled. To return back to the "Icon- Only User Interface", repeat the process except click on the `Off`; button and then the `Update` button followed by a reboot.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin7.png" alt="Admin Area" width="300">

## System Control Items

- _Unmounting the USB__key:_

Allows for safe removal of the USB key

- _Shutting Down the__Unit:_

Will shut down the ConnectBox remotely – Note: power is still on, but all functions will stop and the WiFi signal will stop. To reduce battery, drain, turn the power switch off.  (This can be used in creative access countries to quickly shut the unit down without having to touch the unit)

- _Rebooting the__Unit:_

Will shut down and restart the ConnectBox – Note: it will take several seconds before the WiFi signal goes away and comes back again. This forces all attached devices to disconnect and then have to reconnect to use the ConnectBox.

- _Resetting to__Default:_

This will reset all options to the default configuration and wipe all previous statistics / history.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/admin8.png" alt="Admin Area" width="300">

# Adding in Media Content

You have the option of connecting an external USB stick to the USB port that is available on the ConnectBox's exterior. The USB port will in a sense override any content that is displayed on the microSD card within the unit. The USB stick should be formatted for FAT32 format.  We recommend a slim line USB media stick like the SanDisk Cruzer line for low profile.  Media content can be added to it using a Windows or Mac system.  Folders can be used at your choosing and the file naming conventions can utilize the full character set of UTF-8, meaning non-Latin based scripts can be used.

The unit will default to a simple Icon only interface allowing you simple navigation to the files and folders you have placed on the USB media stick.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/gui1.png" alt="GUI" width="300">

## Icon-Only User Interface Suggestions

The ConnectBox will display an appropriate icon for each folder on your USB stick. A folder icon can be set in one of these ways:

1. Choose an icon from the icon list here: [http://fontawesome.io/icons/](http://fontawesome.io/icons/) Give your folder the same name as the icon. For example, if you want to use theaddress book icon, your folder should be named address- book Your ConnectBox will automatically use that icon when it displays that folder.
2. Name your folder whatever you like e.g. people. Choose an icon from theicon listg.address-book and create a file next to the folder called `_icon_<folder-name>_<icon-name>` e.g.
`_icon_people_address-book` (be sure to use the underscore character in the folder name where appropriate).
3. Name your folder what you like e.g. `people`. Put your own image on the USB stick, next to the folder and name it `_icon_<folder-name>.<extension>` where extension is the image type (gif, jpg, png) e.g. `_icon_people.jpg` (be sure to use the underscore character in the folder name where appropriate).
4. If none of the above are done, your folder will have a default folder icon.

When you insert your USB stick into the ConnectBox, content will automatically be visible in the ConnectBox web interface (this is [http://connectbox](http://connectbox/)unless the system name has been changed during Initial Administration described above).

To update the files on the USB stick, go to the Configure Menu in Administration area, then go to System and press `Unmount USB`, then remove the USB stick from the ConnectBox. Or you can remove the USB at any time the unit is powered off. **NOTE** : Do not remove the USB key while the unit is powered on as this could cause corruption of the USB key.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/file_explorer.png" alt="GUI">
<br />
<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/gui1.png" alt="GUI" width="300">

Some samples of the file icons are:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/icons.png" alt="GUI">

# Using the Chat functionality

Built into the main function of the Connectbox is the ability for users connected to the box to converse with one another. This is entered by tapping the chat icon on the top right of the screen:

Tapping the Chat Icon

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/chat1.png" alt="GUI" width="300">

This opens the chat window:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/chat2.png" alt="GUI" width="300">

Note that you can change the `name` of the user in the bottom left panel and enter the text of the message in the bottom right panel.  Once entered it is posted by pressing the right arrow button on the bottom right.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/chat3.png" alt="GUI" width="300">

All users can see all messages that have been posted.  Additionally, right to left languages can be supported by pressing the alignment button between the name and message entry boxes.  This allows each user to control the direction of text entry for their own post.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/chat4.png" alt="GUI" width="300">

To exit the chat function simply press the X on the top right of the screen.

# LED and Screen Usage

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/OLED1.png" alt="GUI" width="500">

On the top front are three LED's as well as one display and three buttons.  The Green LED indicates that the power is turned on.  The Orange LED presently indicates that the WiFi signal is transmitting.  The Red LED is lit during battery charging and will be extinguished when the battery if fully charged.  Additionally the RED LED may blink to indicate a problem with the battery when the unit is charging or turned on.

The OLED screen on power up will show the ConnectBox logo for a short period of time then turn off.  Of the three buttons, ˄ up, ˅ down, ∧˩ return, only the up and down buttons are used at this time.  Pressing the up button for 1 second will bring up the first status screen:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/OLED2.png" alt="GUI" width="300">

This screen shows the number of connected people, the version number of firmware in the unit, the battery charge level and the CPU temperature.   **NOTE** : The CPU temperature should never exceed 70˚C.

Pressing the up button again for 1 second with the first status screen on, will bring up the second status screen:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/OLED3.png" alt="GUI" width="300">

This screen shows more detailed information on the battery.  Including the current battery power level in %, the voltage output from the battery, the temperature inside the case and the amount of current being drawn out of the battery.  Note that the battery is a 3400 mAh battery or a 3000 mAh battery depending on model.

At any time after the first screen pressing the down button for 1 second will go back a screen.

Pressing the up button again for 1 second with the second status screen on, will bring up the third status screen:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/OLED4.png" alt="GUI" width="300">

This screen again shows the number of people connected (or devices), the amount of time in hours : minutes : seconds since the unit was started or rebooted.  And the total amount of WiFi traffic transmitted and received.

Pressing the up button again for 1 second with the third status screen on, will bring up the fourth status screen:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/OLED5.png" alt="GUI" width="300">

This screen shows the most popular downloaded or viewed files on the unit.  The screen will allow you to scroll up/down the list with the most popular on the top by using the up and down buttons.  If there is an `empty` clipboard symbol, there are no statistics to view.  The p marker shows which page of the report you are looking at.  Using the enter button on any particular listing line will give you additional information on the file usage.

If no buttons are pressed after 10 seconds, then the screen will go black again to conserve battery power.  Pressing the Up button for more than 1 second will again show the first screen.

This is an open source project and we appreciate your feedback and suggestions. Please visit: [http://feedback.connectbox.technology/](http://feedback.connectbox.technology/) and leave your comments. Anything posted here will automatically go directly to the developers for consideration

ConnectBox Homepage: https://connectbox.technology/wp/

ConnectBox Development Source Code: https://github.com/ConnectBox