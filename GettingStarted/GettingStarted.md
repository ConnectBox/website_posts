> ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image1.png)

# Getting Started Guide With Your ConnectBox
Your ConnectBox is nearly ready to go. There are just a few things that we recommend that you do first to enhance the end-user experience.

---

## Initial Administration / Setup

Your ConnectBox comes preloaded with only the system software; no content is included. You'll need to add your own content to the device using the guidelines in the section below.

Your ConnectBox comes with an internal lithium-ion battery. To charge the battery, you'll need to connect up a 1A or greater microUSB charger similar to the ones bundled with many cell phones. From charging from an empty to full battery, expect it to take around 12 hours with the original unit to around 6 or less hours with the subsequent models. Your ConnectBox has built-in low battery protection to prevent ruining the battery if the battery was allowed to discharge all the way down.

With the microUSB charger plugged in or with a relatively full battery, turn your unit on using the switch on the side of the unit. Allow a minute or two to pass before using a wireless device to locate and join the default wireless network called *ConnectBox - Free Media*

> **Note:** if you are connecting from a mobile device it may 'validate the internet connectivity and/or check if a login is required for the network join'. In this case it may show a web browser window that say's to connect to [http://connectbox](http://connectbox/). In some cases you may need to go to the 'more' menu and 'keep the connection' -- close the default browser and re-open a web browser on the device and enter [http://connectbox](http://connectbox/) in the URL window. This should open the default front page of the Connectbox.

Navigate to the Administration area: [http://connectbox/admin](http://connectbox/admin) and login with the default Connectbox credentials (username and password are case sensitive):

`username: admin`
`password: connectbox`

> **Recommended**: Change the password for the Administration area. Go to the 'Configure Menu' and select 'Password'. Enter a new password and press submit. When you next try to enter the admin portal of the Connectbox, you will be prompted to login again. Use the new password when this happens.

### Other notes:
When you insert your USB stick into the ConnectBox, content will automatically be visible in the ConnectBox web interface (this is [http://connectbox](http://connectbox/) unless the system name has been changed during Initial Administration described below).
    
To update the files on the USB stick, go to the Configure Menu in Administration area, then go to System and press 'Unmount USB', then remove the USB stick from the ConnectBox. Or you can remove the USB at any time the unit is powered off. NOTE: Do not remove the USB key while the unit is powered on as this could cause corruption of the USB key.

---

## Optional Admin Setup Items

### HOSTNAME

Change the name of the hostname (by default this is 'connectbox') to something of your own choosing. From the admin menu, go to (Configure --\> Hostname). This only appears in the location bar of the browser. If you changing the hostname, you will need use the new [http://hostname](http://hostname/) for the default web page, or [http://hostname/admin](http://hostname/admin) for the administrative area. Additionally, new login credentials will be asked for.

### WiFi SSID

Change the name of the wireless network that is visible to the users. (Configure -\> SSID). When you do this, you will be disconnected from the wireless network and you will need to locate and join the newly named wireless network.

### WiFi Channel

Change the WiFi channel to something that might be less congested in your area. (Configure -\> Channel) Your choices are channels 1 -- 11 from the dropdown menu. When you change the WiFi channel, you will temporarily be disconnected from the Connectbox until your device reconnects to the WiFi SSID on the new channel.

### Icon-Only UI Banner Message

If you perhaps would like to share with your connected users some sort of banner message (e.g., contact info or organization name) you can set this from the (Configure -\> Banner Message) menu item. This box accepts input as either plain text or as html formatted. An example of something that would produce a banner that looks like this:

> Brought to you by: <span style="color:#008000">**Global Tech Team**</span>
>
> +1-800-555-1212 **(USA)**

Using the html format of:

`<p><i>Brought to you by: <span style="color: #008000;"><strong>Global Tech Team</strong></span></p><p>+1-800-555-1212 <em>(USA)</em></i></p>`

### Enabling Custom Web Interface

By default, your ConnectBox is configured to run using what we call the "Icon-Only User Interface". In this mode, the content that is displayed in your end user's browser looks similar to a file explorer window. Each piece of media on located on your disk is displayed as a file or folder allowing navigation into subfolders. This is the perfect option for content that is perhaps dynamic where you may be adding in new files each day and you don't want to necessarily worry about having to format the display. Just add in your new media files, turn on the device and it will display it.

For groups that would like a more customized look to the interface, they can convert the interface into a typical webpage.  You start by putting onto the media storage space a file that has to be named: **index.htm** This file would obviously need to be a html formatted file that can display icons, images, do text enhancements, link to a CSS file, etc.

From the ConnectBox Administration menu, you do need to do one more step to trigger your ConnectBox to use this mode. Go to (Configuration -\> Static site) and clicking the 'On' button then clicking update. Reboot the device after the change for it to be enabled. To return back to the "Icon- Only User Interface", repeat the process except click on the 'Off' button and then the 'Update' button followed by a reboot.

---

## System Control Items

### Unmounting the USB key

Allows for safe removal of the USB key

### Shutting Down the Unit

Will shut down the ConnectBox remotely -- Note: power is still on, but all functions will stop and the WiFi signal will stop. To reduce battery drain, turn the power switch off.

### Rebooting the Unit

Will shut down and restart the ConnectBox -- Note: it will take several seconds before the WiFi signal goes away and comes back again. This forces all attached devices to disconnect and then have to reconnect to use the ConnectBox.

### Resetting to Default

This will reset all options to the default configuration and wipe all previous statistics/history.  Note that this does not effect your media files which will remain the same.  This just resets the Admin area's settings.

---

## Adding in Media Content

Your microSD card has been dual formatted to contain both the operating system partition as well as an additional large partition for media. Since the microSD card is enclosed within the case, removal it isn't always the easiest way to add content since it requires you to disassemble the ConnectBox and remove the microSD card. You'll then usually need to host the microSD card within a standard USB adapter to be able to gain access to the media partition from your laptop.

The microSD card's media partition has been formatted using FAT32 which is a file format that nearly every computer can read and write to. However, the second partition that contains the operating system has been formatted using a file system that Windows and Mac computers cannot read and will complain about (Unix EXT4 format). **It is imperative that if you take out your microSD card from the ConnectBox and connect it up to your Windows or Mac computer that you ignore any warnings from them about it being a bad disk that needs formatting.**  Just cancel or close any windows that appear saying something similar. Doing any sort of the suggested Windows or Mac formatting of the microSD will overwrite the operating system for the ConnectBox which means that it will no longer work.

However, you can use the other FAT32 partition which will show up normally to write your media files to. Feel free to make subfolders to better arrange content into logical groupings. This FAT32 partition will normally show up as 'CBMedia' or 'WINSIDE' on your computer.

If you do not desire to use the internal microSD card's available memory, then you also have the option of connecting an external USB stick to a USB port that is available on the ConnectBox's exterior. Either USB port will in a sense override any content that is displayed on the microSD card with the rear USB port (next to the network jack) taking priority over the side USB port (next to the power switch). If you install two USB memory sticks into the unit only the rear USB will be utilized for media content.

---

## Icon-Only User Interface Suggestions

The ConnectBox will display an appropriate icon for each folder on your USB stick. A folder icon can be set in one of these methods:

### Method 1 - Default Icon

If you do nothing, your folder will recieve the default icon look to it. 

### Method 2 - Automatic Icon Selection
> **Note:** Currently there is a bug in that the automatic icon will only work in the root folder and does not work in subfolders.

Naming your folder the same name as one of the FontAwesome names will render that folder's icon to the be FontAwesome image.  First, choose an icon from the icon list here:
[http://fontawesome.io/icons/](http://fontawesome.io/icons/)

Give your folder the same name as the icon you want to show. For example,if you want to use the [address book icon], your folder should be named `address-book`. Your ConnectBox will automatically use that icon when it displays that folder to the user.

A subset of available icons are shown below.

### Method 3 - Use Your Own Icon
In this method, you supply the icon that will be used by your folder.  Start by naming your folder what you like e.g. 'people'. Put the image that you want to use for the folder onto the same directory level as the folder.  In other words, if your new `people` folder is in a subdirectory called 'groups', you would want both your folder and the image that you want to show for it in the same 'groups' directory. The image you want to use needs a special naming convention so that the ConnectBox knows to show this image in place of the default folder icon. You need to name the image in the format of:

    _icon_<folder-name>.<extension>

Where the <extension> part is the image type (gif, jpg, png).  So in our example, you would take your image and name it:

    _icon_people.jpg
    (be sure to use the underscore character in the folder name where appropriate)

> **Note:** This method works well for all subdirecties.

### Method 4 - Use Your Own Folder Name and Icon
> **Note:** This method currently does not work correctly.

In this method Name your folder whatever you like and the image that will be displayed for it can likewise be any name. Start by naming your folder what you like e.g. 'people'. Put the image that you want to use for the folder onto the same directory level as the folder. In other words, if your new `people` folder is in a subdirectory called 'groups', you would want both your folder and the image that you want to show for it in the same 'groups' directory. The image you want to use no longer would need a special naming convention.  But in order for the ConnectBox to associate your 'people' folder with some icon e.g., 'irish-man.png' well need a special file to link the two together.

A new file will need to be created, which can be blank, that like Method 3, has a special image to link your unique folder and image file together. You will need to name this new file in the format of:

    _icon_<folder-name>_<icon-name>

Note that there is NO extension for the file name.  So for our example, you would name the file this:

    _icon_people_irish-man.png

### Some samples of the file icons are:

&nbsp;  | &nbsp;  | &nbsp;  | &nbsp; 
--- | --- | --- | ---
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image2.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image3.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image4.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image5.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image6.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image7.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image8.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image9.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image10.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image11.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image12.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image13.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image14.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image15.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image16.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image23.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image24.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image25.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image26.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image27.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image28.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image29.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image30.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image37.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image38.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image39.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image40.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image41.png)
![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image42.png) | ![](https://raw.githubusercontent.com/ConnectBox/website_posts/master/GettingStarted/image43.png)

---

This is an open source project and we appreciate your feedback and suggestions. Please visit:
[http://feedback.connectbox.technology/](http://feedback.connectbox.technology/) and leave your comments. Anything posted here will automatically go directly to the developers for consideration.

ConnectBox Homepage: [https://connectbox.technology/wp/]

ConnectBox Development Source Code: [https://github.com/ConnectBox]
