# Support

This is the Support page.

## Send Feedback to the Developers: 
[ConnectBox Feedback Form](http://http://geodirk-001-site1.btempurl.com/ "Feedback Page")

## Google Groups Forum / Mailing List:
[ConnectBox Google Groups Forum](https://groups.google.com/d/forum/connectbox "ConnectBox Google Groups Forum")

## Add an issue to GitHub:
[ConnectBox Github Project](https://github.com/ConnectBox/connectbox-pi/issues "GitHub Project Issues")

## Frequently Asked Questions (FAQ):

### Reset your ConnectBox back to "factory condition"
There are a few steps (a few more than we’d like to be honest, but we’re working on the update mechanism).

1. Download the latest release image from GitHub: https://github.com/ConnectBox/connectbox-pi/releases/ Pick the latest version of the *Release* branch and not the *Developer* version.
2. Download Etcher (http://etcher.io/) so you can burn the image to the microSD. We recommend this program even if you have another method for burning, as it actively verifies that the image has been successfully burnt.
3. Take the microSD card out of the ConnectBox (you’ll need to open the case to do this)
4. Burn the image to the microSD card using Etcher (Etcher will burn the image file that you downloaded without requiring decompression)
5. Pop it back in the ConnectBox and start it.

Note: You won’t be able to use the internal storage on the microSD for data with this process, but if you’re using external USB storage, that won't be a problem. There is a process that allows you to dual partition the internal microSD for use both for the OS and for your media, but it’s for advanced users: https://connectbox.technology/wp/utilizing-your-existing-microsd-boot-card-for-your-media-files/

If you want to use a master connectbox-pi release 20180122 with a 10GB fat32 format partition on the start of the micro-sD then in step #1 above download from:
https://emailnet-my.sharepoint.com/:u:/g/personal/kirk_wilson_om_org/Eb2HpKKxcF1Fn8qZar-zvEABh8vPpKYERoSiPsTaLvKtHw?e=AiAlPh
This will require a 16GB micro-sD card and will fill it with 2 partitions, a fat32 and an ext4 partition for booting the ConnectBox OS.

### Connecting to your ConnectBox via SSH
By default, your ConnectBox has SSH disabled over the LAN port.  It is relatively simple to turn it on.  Essentially, you need to create a specifically named directory and a file in that directory on your external USB stick.  Have it inserted, then boot the device.  The ConnectBox will automatically see those items and thereby enable SSH support over the LAN.  The folder must be named:
 
`.connectbox` (in all lowercase and with the preceeding period)

Inside that folder, you will need to put a file called: `enable-ssh` again without the quotes.  The file can contain information or be blank.

Under *Windows*, the Operating System won't let you make folders that start with a period so you need to do something a bit different.  Open up a Command Prompt, (hold down the `WINDOWS-R` keys and a window will pop open. Type `cmd` into it and hit the OK button).  From the terminal window, go to your USB drive by typing in the following:

`D:` where D: is the drive letter of your external USB stick.

Then type `mkdir .connectbox` which will allow you to make that special folder with the period in the front of the name.  Follow this with the command `cd .connectbox` to move inside of that folder.  Then make the file with the command `type nul >enable-ssh`.  That is all there is to doing that under Windows.