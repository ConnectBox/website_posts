<!-- TOC -->

- [Utilizing Your Existing microSD Boot Card for Your Media Files](#utilizing-your-existing-microsd-boot-card-for-your-media-files)
    - [Step 1: Initializing the microSD Image](#step-1-initializing-the-microsd-image)
    - [Step 2: Getting an Ubuntu Instance in a Virtual Machine](#step-2-getting-an-ubuntu-instance-in-a-virtual-machine)
    - [Step 3: Installing gparted](#step-3-installing-gparted)
    - [Step 4: Selecting the microSD Device](#step-4-selecting-the-microsd-device)
    - [Step 5: Unmounting the USB device](#step-5-unmounting-the-usb-device)
    - [Step 6: Resize/Move the ext4 Partition](#step-6-resizemove-the-ext4-partition)
    - [Step 7: Creating a FAT32 Partition](#step-7-creating-a-fat32-partition)
    - [Step 8: Use gedit to Modify fstab](#step-8-use-gedit-to-modify-fstab)
    - [Step 9: Final Steps](#step-9-final-steps)

<!-- /TOC -->
# Utilizing Your Existing microSD Boot Card for Your Media Files

A the time of writing this walkthrough, the prices for a 16 Gb microSD card are significantly lower than the price of an 8 Gb card.  The operating system on the ConnectBox's microSD card only really requires around 2 Gb of space for the OS to properly operate.  That means that you are essentially wasting a lot of the capacity of your microSD card that you could use to store your data in.

If you are one of those groups that has essentially static content that you want to distribute via a ConnectBox, you probably want to consider modifying your microSD card so that you can create a media partition on it that is accessable from another, more standard, computer (e.g., Windows or Mac). This will allow you to only need the one internal microSD card that contains both the ConnectBox OS boot and also contains your website/media. You will end up saving some costs and time by only using the one microSD card and not have to replicate multiple memory cards.

If you have content that might change more frequently, this is probably a bad option for you as it will require the end user to take apart the ConnectBox case each time that something needs to be updated. The below described process really is for when you have relatively static media content that you want to distribute around and not requiring that you open up the ConnectBox case. It is ideal for rapidly duplicating content to other microSD cards.  

If your content does change often, just put the content onto an external USB stick so you the media is easily accessable for when you want to modify it.

There are a few things to watch out for when repartitioning your microSD card like described below. Please follow the directions exactly to obtain the best results.

## Step 1: Initializing the microSD Image

Once your base ConnectBox image has been burned to a microSD card, the first step is to install it on the ConnectBox device and let it boot up.  The intial booting process initializes the device and beyond setting up the device, it also modifies the partition on the microSD card by taking up almost all the rest of the free space on the card.  It does leave a buffer or empty space at the end of the card which is important to do when you decide to mirror the final image around to other microSD cards.  Different card vendors can have slightly different sizes even though they all report the same size in gigabytes.  The intital setup and resizing takes several minutes to complete, so wait a while and make yourself some tea. You will be able to tell when it is complete by when the "ConnectBox - Free Media" SSID shows up as being available as a WiFi connection on your devices.  At that point, switch off the ConnectBox using the switch and allow it to shutdown completely.  Take the microSD card out of your ConnectBox for the next part.

## Step 2: Getting an Ubuntu Instance in a Virtual Machine 

We'll now want to resize that partion down from taking up nearly all the entire card's space to only that which is necessary for the OS to boot and operate the device. Since this is a Linux partition, the easiest way to resize the card is to complete the action within a graphical Linux OS (i.e., Ubuntu or Debian).  If you don't have a Linux system handy, you can run it within a virtual machine (e.g., VMWare Player [VMWare Player](https://www.vmware.com/products/workstation-player.html "VMWare Player") or Oracle's VM VirtualBox [VirtualBox](https://www.virtualbox.org/ "VirtualBox")). Setting up these virtual machines isn't overly difficult and there are good guides to doing so on the internet. I would suggest following the video guide here: [YouTube](https://www.youtube.com/watch?v=RBU1xMP-SGc "YouTube")

## Step 3: Installing gparted

From the Linux Desktop (in this case I'll be using an Ubuntu 16.04 computer), you'll want to install the program `gparted` which allows us to modify and create partitions on the microSD. By clicking on the orange "Ubuntu Software" icon on the left dock, do a search for the gparted program and then install it. 

![gparted search](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_install.png?raw=true "Install gparted on Ubuntu")

## Step 4: Selecting the microSD Device

After it is installed, attach your microSD card to the machine that is running VirtualBox. You'll need to click onto the VirtualBox Window's menu and select \Devices\USB\ and then pick the device that is your microSD card. Doing this will transfer control from your host computer (Windows) to your Ubuntu computer running inside the VirtualBox.

![gparted USB](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_select_USB.png?raw=true "Transfer USB to VM")

Once you do that, then run gparted. By default, gparted comes up with your own virtual machine's hard drive (/dev/sda). We don't want that. So you'll need to select from the drop down menu on the upper right side the correct drive. Usually, this should be the second one; /dev/sdb. Ensure that the reported size of the drive roughly matches the size of your microSD card.

![gparted Select USB](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_select_drive.png?raw=true "Select USB Drive")

You'll notice that the partion on the drive is currently one massive ext4 partition with a small amount of unallocated space at the end (right side) of the drive.

## Step 5: Unmounting the USB device

Before we can do anything with this drive, we need to tell it to unmount itself from the operating system. Right click on the yellow and white bar and select "Unmount".

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_unmount_1.png?raw=true "Resize Partition")

## Step 6: Resize/Move the ext4 Partition

Putting your cursor over the partition, right click on it to bring up a menu and select "Resize/Move"

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_2.png?raw=true "Resize Partition")

In the box that shows up, click in the second box down and change the existing number to 4000.

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_3.png?raw=true "Resize Partition")

Then go to the first box and fill in the rounded number of the remaining space. In my example with a 16Gb microSD card, I'm allocating roughly 11000 megabytes and that will automatically calculate the third box's (Free space following) number. As stated above, we want to leave a small buffer at the end of at least 128 MiB. We'll leave the 342 number as the 11Gb of space in the front is enough to store all our media. You'll need to adjust your sizes in these boxes to match the capacity of your card. Just remember to make the ext4 drive about 4Gb and leave that buffer space after.

Click the "Resize/Move" button

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_4.png?raw=true  "Resize Partition")

A warning screen will come up...just click the "OK" button

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_5.png?raw=true "Resize Partition")

On the top menu, first click the green checkmark icon.  Another warning will come up.  Click on the "Apply" button.

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_6.png?raw=true "Resize Partition")

The process will start of resizing and moving the partition around on your microSD card. This can take a very long time to complete...  You'll want to look at the details as the process move along checking for disk errors. If there are disk errors, you probably should start from the beginning again or use a new microSD card.

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_7.png?raw=true "Resize Partition")

The reason that we not only resized the partition down but also moved it towards the end of the space is that if we want to plug this device onto a Windows machine to copy content over, Windows requires that the partition for the media be first on the microSD card.

## Step 7: Creating a FAT32 Partition

Once that operation is complete, we'll now need to convert that unalloced space into a new partition that we can use to store our media data. With our mouse over the gray partition labeled "unallocated", right click. From the menu, select "New".

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_8.png?raw=true "Resize Partition")

A new window will come up that wants to know how to create that new partition.

1. Make sure that the "Create as:" box is changed to **Primary Partition**

2. Change "File system" to be **fat32**

3. And change the "Label" to be **WIN-SIDE** so we can tell what this partition is from the others

Click the "Add" button.

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_9.png?raw=true "Resize Partition")

Once again, a warning message will come up. Click on the "Apply" button to continue.

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_10.png?raw=true "Resize Partition")

This will take a relatively short bit of time to complete.

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_11.png?raw=true "Resize Partition")

Once the process has finished successfully, you'll get a screen like this:

![gparted resize](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_resize_12.png?raw=true "Resize Partition")

You'll notice that the first partition is a fat32 one (where our media will go), the second is ext4 (where the ConnectBox's boot operating system is located), and the final unallocated space that gives us a buffer for when we want to mirror the microSD card out.

## Step 8: Use gedit to Modify fstab

Close the gparted program and Ubuntu should automatically mount both of the partitions. One will be labeled "WIN-SIDE" and the other will just say the size of the device. Click on the USB icon for the unlabeled on to open it in a file browser. Click on the folder named "etc" to open it. Scroll down till you see the file called "fstab". We'll need to edit this file to add in one new line that will allow the ConnectBox to automatically mount the partition.

Using the Ubuntu search, look for the program "Terminal" and then click on it to launch it.

![Terminal](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_terminal.png?raw=true "Terminal")

At the terminal, you'll need to first find out the "UUID" for the WIN-SIDE partition we made.  You do that by typing in `lsblk -f'

![Terminal](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_terminal_2.png?raw=true "Terminal")

In the above picture, what we are looking for is the "UUID" for our "WIN-SIDE" partition.  Make a note of your ID as we'll use it in a momement.

Next thing you need to do is type: `sudo gedit` at the command prompt followed by your user's password. This will launch up a graphical text editor in which we can edit the `fstab` file. From the file window, drag and drop the `fstab` file into the gedit window to edit it.

Go the end of the text file and add in a new line. **It is very important that you type this in exactly like show with the proper case and spacing. Double check this.**

`UUID=D2D0-8176 /media/usb0 vfat sync,noexec,nodev,noatime,nodiratime,utf8`

Replace the `UUID=D2D0-8176` portion with the UUID that you wrote down earlier. Double check your work and save the file and close the editor.

![Terminal](https://github.com/ConnectBox/website_posts/blob/master/partition_gparted_terminal_3.png?raw=true "Terminal")

## Step 9: Final Steps

Eject disk from Ubuntu. You can now use this on a Window's or Mac computer to add in your media to the new partition.

<span style="color:red">**One bit of warning:**</span> Windows is not going to like the "ext4" partition and will complain about when you add it to the machine. Expect to get something like this:

![Terminal](https://github.com/ConnectBox/website_posts/blob/master/partition_windows_error.png?raw=true "Terminal")

Be sure to hit "Cancel" to close out the window and any others that pop up.

On Windows, just open up the new drive that is labeled "WIN-SIDE" and drop your media files in there. Install the microSD card into the ConnectBox and boot up.  As long as you don't plug in an additional USB drive to the outside of the unit, your media files will now be shown by default. You have now just created a single microSD card that holds the ConnectBox operating system and all your media files.