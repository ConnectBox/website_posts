
<img class="alignnone wp-image-210" src="https://connectbox.technology/wp/wp-content/uploads/2017/11/connectbox_logo_512.png" alt="" width="194" height="194" />

<br/><br/>            
<img class="alignnone wp-image-210" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/ConnectBox-BatteryVersion6.png" alt="" width="388" height="274" />  

### Model P - Battery Operated
        
<br/><br/>
<img class="alignnone wp-image-211" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/ConnectBox-Non-Battery-Transparent-BG.png" alt="" width="488" height="360" /> 
<br/><br/>
### Model S - Line Powered

<br/><br/>

# Overview and Initial Connection
This ConnectBox is nearly ready to go, just a few things that you need to do first to make the end user experience useful.

## Initial Setup

1. ConnectBox comes with internal system software. No content is included other than a readme file. You’ll need to add your own content to the device using the guidelines in the sections.
2. Your battery version ConnectBox comes with an internal lithium-ion battery which is shipped at 30% charge level. To charge the battery, you’ll need to connect it to a 1A or greater microUSB charger like are found with many cell phones. For charging from an empty to full battery, expect it to take around 4-7 hours. Your ConnectBox has built-in low battery protection which prevents the battery from going into deep discharge as well as from overcharging.  <span style="color: #ff0000;">PLEASE FULLY CHARGE YOUR CONNECTBOX BEFORE THE FIRST USE</span>.
3. With the microUSB charger plugged in or with a relatively full battery, turn your unit on using the switch on the side of the unit. Allow a ***minute or two*** to pass before using a wireless device to locate and join the default wireless network called *ConnectBox - Free*. You will know when it is available by the yellow LED turning on. (Note: that if you charge your unit and run the unit simultaneously in a hot climate it may cause a red flashing indicator of high temperature internal to the unit.)

*Note: if you are connecting from a mobile device it may ‘validate the internet connectivity and/or check if a login is required for the network join’. In this case it may show a web browser window that say’s to connect to [http://connectbox/]() or [http://wi.fi](). In some cases you may need to go to the ‘more’ menu and ‘keep the connection’ – close the default browser and re-open a web browser on the device and enter [http://connectbox/]() or [http://wi.fi]() in the URL window. This should open the default front page of the Connectbox.  (Note: on some Samsung Galaxy phones you may need to turn cellular data off for the wifi to fully work.)*


Internet validation windows will look like this:

<ul></ul>

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_WebConnect12.jpg" />
<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_WebConnect34.jpg" />

<ul></ul>

Switching between views showing what you should do next.  When you’re ready click OK.  To use the ConnectBox you need to open up a browser on your device (native browser, chrome, safari, firefox, etc.)  and type in the web address of <a href="http://wi.fi">http://wi.fi</a> which will then result in seeing the main ConnectBox window.  If there has not been any data loaded onto the device it will only show the single README.txt file as:
<ul></ul>

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_FirstRun.jpg" />

&nbsp;
<ul></ul>

Although the default settings for the ConnectBox make it usable without any changes, the Configuration options (discussed below) are available for those who wish to customize the operation of the ConnectBox.

# The Administrator Web Page


Navigate to the Administration area: <a href="http://connectbox/admin">http://connectbox/admin </a> (or press the cog icon on the bottom right of the screen)  and login with the default Connectbox credentials (username and password are case sensitive):
&nbsp;

- <u>username</u>: admin
- <u>password</u>: connectbox

&nbsp;
**Recommended** Change the password for the Administration area. Go to the <u>Configuration Menu</u> and select <u>Password</u>. Enter a new password and press submit. When you next try to enter the admin portal of the Connectbox, you will be prompted to login again. Use the new password when this happens.
<ul></ul>


# Configuring your unit

Configuration of your unit is done through the following 5 configuration pages:

- **Wireless Access Point:** change SSID (wireless display name), select the WiFi channel and increase security by adding a WPA passphrase.
- **Web Server:** set either Icon interface (default) or static web page as the main entry point as well as changing the Hostname that appears.
- **User Interface:** set up a custom Banner Message that shows on the main page in Icon interface mode.
- **Password:** allows you to change the system password for the Administrator functions (Note: we highly recommend changing the administrator password from the default ‘connectbox’).
- **System:** allows remote control of the ConnectBox to unmount the USB attached to the unit as well as the facility to reboot, reset or shutdown the unit remotely.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin2.jpg" />

&nbsp;
## Configuration  Items

### HOSTNAME
Change the name of the hostname (by default this is ‘connectbox’) to something of your own choosing. From the admin menu, go to (Configure -&gt; Hostname). This only appears in the location bar of the browser. If you are changing the hostname, you will need to use the new [http://hostname/]() for the default web page, or [http://hostname/admin]()for the administrative area. Additionally, new login credentials will be asked for.

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin3.jpg" />

&nbsp;
### WiFi SSID
Change the name of the wireless network. (Configure -&gt; SSID). When you do this, you will be disconnected from the wireless network and you will need to locate and join the newly named wireless network. (a maximum of 32 characters can be used.)

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin4.jpg" />

&nbsp;
### WiFi Channel

Change the WiFi channel to something that might be less congested in your area. (Configure -&gt; Channel) Your choices are channels 1 – 11 from the dropdown menu. When you change the WiFi channel, you will temporarily be disconnected form the Connectbox until your device reconnects to the WiFi SSID on the new channel.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin5.jpg" />

&nbsp;
### Icon-Only UI Banner Message

If you perhaps would like to share with your connected users some sort of banner message (e.g., contact info or organization name) you can set this from the (Configure -&gt; Banner Message) menu item. This box accepts input as either plain text or as html formatted. An example of something that would produce a banner that looks like this:
&nbsp;

Brought to you by: <strong>Global Systems Design</strong>

+1-720-515-4757 <em>(USA)</em>
<em> </em>

Using the html format of:

&nbsp;
***&lt;p&gt;Brought to you by: &lt;span style="color: #008000;"&gt;&lt;strong&gt;Global Tech Team&lt;/strong&gt;&lt;/span&gt;&lt;/p&gt;&lt;p&gt;+1-800-555-1212 &lt;em&gt;(USA)&lt;/em&gt;&lt;/p&gt;***

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin6.jpg" />


&nbsp;
### Enabling Custom Web Interface

By default, your ConnectBox is configured to run using what we call the “Icon-Only User Interface”. In this mode, the content that is displayed in your end user’s browser looks similar to a file explorer window. Each piece of media located on your USB flash disk is displayed as a file or folder allowing navigation into subfolders. This is the perfect option for content that is perhaps dynamic where you may be adding in new files each day and you don’t want to necessarily worry about having to format the display. Just add in your new media files, turn on the device and it will display it.

&nbsp;

For groups that would like a more customized look to the interface, they can put onto the media storage space a file that has to be named: <strong>index.htm </strong>This file would obviously need to be a html formatted file that can display icons, images, do text enhancements, link to a CSS file, etc.

However, from the ConnectBox Administration menu, you do need to trigger this mode by going to (Configuration -&gt; Static site) and clicking the ‘On’ button then clicking update. Reboot the device after the change for it to be enabled. To return back to the “Icon- Only User Interface”, repeat the process except click on the ‘Off’ button and then the ‘Update’ button followed by a reboot.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin7.jpg" />

&nbsp;
## System Control Items

### Unmounting the USB key
Allows for safe removal of the USB key

&nbsp;
### Shutting Down the Unit
Will shut down the ConnectBox remotely – Note: power is still on, but all functions will stop and the WiFi signal will stop. To reduce battery, drain, turn the power switch off.  (This can be used in creative access countries to quickly shut the unit down without having to touch the unit)

&nbsp;
### Rebooting the Unit

Will shut down and restart the ConnectBox – Note: it will take several seconds before the WiFi signal goes away and comes back again. This forces all attached devices to disconnect and then have to reconnect to use the ConnectBox.

&nbsp;
### Resetting to Default

This will reset all options to the default configuration and wipe all previous statistics/history.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Admin8.jpg" />

&nbsp;

## Adding in Media Content

You have the option of connecting an external USB stick to the USB port that is available on the ConnectBox’s exterior. The USB port will in a sense override any content that is displayed on the microSD card within the unit. The USB stick should be formatted for FAT32 format.  We recommend a slim line USB media stick like the SanDisk Cruzer line for low profile and USB 3 speed is recommended for faster system operation.   Media content can be added to it using a Windows or Mac system.  Folders can be used at your choosing and the file naming conventions can utilize the full character set of UTF-8, meaning non-roman scripts can be used.

&nbsp;
The unit will default to a simple Icon only interface allowing you simple navigation to the files and folders you have placed on the USB media stick.

&nbsp;
<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Gui1.jpg" />


&nbsp;
## Icon-Only User Interface Suggestions

The ConnectBox will display an appropriate icon for each folder on your USB stick. A folder icon can be set in one of these ways:

1. Choose an icon from the icon list here: <a href="http://fontawesome.io/icons/">http://fontawesome.io/icons/</a>. Give your folder the same name as the icon. For example, if you want to use the <u>address book icon</u>, your folder should be named "address-book". Your ConnectBox will automatically use that icon when it displays that folder.
2. Name your folder whatever you like (e.g. people). Choose an icon from the <u>icon list</u> (e.g. address-book) and create a file next to the folder called \_icon\_&lt;folder-name&gt;_&lt;icon-name&gt; e.g. `_icon_people_address-book` (be sure to use the underscore character in the folder name where appropriate).
3. Name your folder what you like (e.g. people). Put your own image on the USB stick, next to the folder and name it \_icon\_&lt;folder-name&gt;.&lt;extension&gt; where extension is the image type (gif, jpg, png) e.g. `_icon_people.jpg` (be sure to use the underscore character in the folder name where appropriate).
4. If none of the above are done, your folder will have a <u>default folder icon</u>. 

When you insert your USB stick into the ConnectBox, content will automatically be visible in the ConnectBox web interface (this is <a href="http://connectbox/">http://connectbox </a>unless the system name has been changed during Initial Administration described above).

To update the files on the USB stick, go to the Configure Menu in Administration area, then go to System and press "Unmount USB", then remove the USB stick from the ConnectBox. Or you can remove the USB at any time the unit is powered off. <strong>NOTE</strong>: Do not remove the USB key while the unit is powered on as this could cause corruption of the USB key.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_FileExplorer.jpg" />

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Gui2.jpg" />

&nbsp;


Some samples of the file icons are:
&nbsp;

<img class="alignnone size-full wp-image-223" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/a11.jpg" alt="" width="746" height="908" />

&nbsp;
A second methodology to add content to a connect box is to use the internal storage of the device.  The micro-flash drive internal to the unit also can store and contain data.  To add data to this drive, you will need to have data on a USB flash key that can be uploaded to the internal drive.  This is covered under LED Screen Usage.

&nbsp;

## Using the Chat functionality

Built into the main function of the Connectbox is the ability for users connected to the box to converse with one another.  This is entered by tapping the chat icon on the top right of the screen:

Tapping the Chat Icon

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Chat1.jpg" />

&nbsp;

This opens the chat window:

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Chat2.jpg" />

&nbsp;

Note that you can change the ‘name’ of the user in the bottom left panel and enter the text of the message in the bottom right panel.  Once entered it is posted by pressing the right arrow button on the bottom right.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Chat3.jpg" />

&nbsp;

All users can see all messages that have been posted.  Additionally, right to left languages can be supported by pressing the alignment button between the name and message entry boxes.  This allows each user to control the direction of text entry for their own post.

&nbsp;

<img src="https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/020721_Chat4.jpg" />

&nbsp;

To exit the chat function simply press the X on the top right of the screen.

&nbsp;

# LEDs and Screen Usage
<img class="alignnone size-full wp-image-210" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/ConnectBox-BatteryVersion6.png" alt="" width="1000" height="500" />

&nbsp;

&nbsp;

On the top front are three LED’s as well as one display and two buttons.  The Green LED indicates that the power is turned on.  The Orange LED indicates that the system is booted WiFi signal is transmitting.  The Red LED is lit during battery charging and will be extinguished when the battery if fully charged. Additionally the RED LED may blink to indicate a problem with the battery when the unit is charging or turned on, additionally, it may blink if the charging circuit is overheating.

&nbsp;

The OLED screen on power up will show the ConnectBox logo for a short period of time then turn off.  The two buttons, ressing the <em>up</em> button for 1 second will bring up the first status screen:

<img class="aligncenter wp-image-226" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d1.png" alt="" width="600" height="322" />

&nbsp;

This screen shows the number of connected people, the version number of firmware in the unit, the battery charge level (Note: on a battery less ConnectBox this area is blank) and the CPU temperature.  .

&nbsp;

Pressing the up button again for 1 second with the first status screen on, will bring up the second status screen.

<img class="aligncenter wp-image-227" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d2.png" alt="" width="600" height="327" />

&nbsp;

This screen shows the time duration that unit has been on, the number of people connected and the aggregate transmit and receive volume of data the unit has sent/received since powered on.

&nbsp;

Pressing the up button again for 1 second with the second status screen on, will bring up the third status screen:

<img class="aligncenter wp-image-228" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d3.png" alt="" width="600" height="319" />

&nbsp;

This screen shows more detailed information on the battery.  This includes the current battery power level in %, the voltage of the battery, the temperature of the power control chip and the current in or out of the battery (as indicated by the directional arrow).  Note that the battery is a 6400 mAh battery or a 3000 mAh battery depending on model.  On a battery less unit the % area is blank and the mV area show the voltage input from the power module and current being drawn from the power module.

&nbsp;

At any time after the first screen pressing the down button for 1 second will go back a screen.

&nbsp;

Pressing the up button again for 1 second with the third status screen on, will bring up the fourth status screen:

<img class="aligncenter wp-image-229" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d4.png" alt="" width="600" height="326" />

&nbsp;

This screen shows the amount of CPU usage in %, the amount of RAM memory usage in % and the amount of USB storage used in %

&nbsp;

Pressing the up button again for 1 second with the fourth screen on, will bring up the fifth status screen:

<img class="aligncenter wp-image-230" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d5.jpg" alt="" width="600" height="317" />

&nbsp;

This screen shows the most popular downloaded or viewed files on the unit <strong>over the last hour</strong>.  This screen show ‘p1’ indicating it is page one of the reports of hourly usage.  Pushing the up button again to see page ‘p2’.  If there is an ‘empty’ clipboard symbol, there are no statistics to view.

&nbsp;

Pressing the up button again for 1 second with the Sixth screen up will show the Seventh screen indicating the most popular file activity for the last Day.  The p number represents the page number of the report (1 or 2).

&nbsp;

<img class="aligncenter wp-image-231" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d6.png" alt="" width="600" height="300" />

&nbsp;

&nbsp;

This screen shows the most popular streamed/downloaded files on the unit for the day.  If there is an ‘empty’ clipboard symbol, there are no statistics to view.  The p marker shows which page of the report  (1 or 2) you are looking at.

&nbsp;

Pressing the up button again for 1 second with the Eighth  screen on, will bring up the Ninth  status screen showing the most popular streamed/downloaded files on the unit for the Week.  If there is an ‘empty’ clipboard symbol, there are no statistics to view.  The p marker shows which page of the report  (1 or 2) you are looking at.

<img class="aligncenter wp-image-232" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d7.png" alt="" width="600" height="300" />

&nbsp;

Pressing the up button again for 1 second with the Tenth screen on, will bring up the Eleventh status screen showing the most popular streamed/downloaded files on the unit for the Month.  If there is an ‘empty’ clipboard symbol, there are no statistics to view.  The p marker shows which page of the report (1 or 2) you are looking at.

&nbsp;

<img class="aligncenter wp-image-233" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d8.png" alt="" width="600" height="300" />

&nbsp;

&nbsp;

Pressing the up button again for 1 second with the 12<sup>th</sup> screen on, will bring up the Memory copy entry screen showing how to enter file copy mode by pressing both up and down buttons simultaneously for more than 5 seconds.

&nbsp;

<img class="aligncenter wp-image-234" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d9.png" alt="" width="600" height="300" />

&nbsp;

&nbsp;

If no buttons are pressed after 10 seconds, then the screen will go black again to conserve battery power.  Pressing the Up button for more than 1 second will again show the first screen.

&nbsp;

&nbsp;

If at any active screen you push and hold both left and right buttons for more than 5 seconds you will open a file copy menu which is explained in more detail in the following block diagram:

&nbsp;

<img class="alignnone size-full wp-image-235" src="https://connectbox.technology/wp/wp-content/uploads/2020/06/d10.png" alt="" width="2502" height="3259" />

&nbsp;

### Optional Features:

&nbsp;

The Connectbox can be ordered in two models:

**Model P:** 
  
- Battery Version with 6,000 mAh battery
- 109mm L x 80mm W x 28mm H
- 208 g Weight

&nbsp;


**Model S:**
 
- Non-Battery Version with power module only
- 73mm L x 80mm W x 28mm H
- 99 g Weight
       
&nbsp;
&nbsp;


Both of the **P** and **S** versions can be ordered with two accessories:

**Accessory 1:**

Metal tie wrap to attach the Connectbox to another object/anchor to keep it from being removed. Once attached the only way to detach it is to cut the metal tie-wrap.

**Accessory 2:**

Micro-SD card cover that can be inserted inside of the unit to keep the micro-SD card from being removed without opening the case.  This accessory can be retrofitted into existing Connectbox version 6 units or later.  But is best if pre-ordered with the unit.

&nbsp;

This is an open source project and we appreciate your feedback and suggestions. Please visit: [http://feedback.connectbox.technology/](http://feedback.connectbox.technology/) and leave your comments. Anything posted here will automatically go directly to the developers for consideration.

&nbsp;

ConnectBox Homepage: [https://connectbox.technology](https://connectbox.technology)

ConnectBox Development Source Code: [https://github.com/ConnectBox](https://github.com/ConnectBox)

ConnectBox Discussion Forum:  [https://groups.google.com/forum/#!forum/connectbox](https://groups.google.com/forum/#!forum/connectbox)
