# Support

This is the Support page.

## Send Feedback to the Developers: 
[ConnectBox Feedback Form](http://feedback.connectbox.technology/ "Feedback Page")

## Add an issue to GitHub:
[ConnectBox Github Project](https://github.com/ConnectBox/connectbox-pi/issues "GitHub Project Issues")

## Frequently Asked Questions (FAQ):

### Reset your ConnectBox back to "factory condition"
There are a few steps (a few more than we’d like to be honest, but we’re working on the update mechanism).

1. Download the latest release image from GitHub: https://github.com/ConnectBox/connectbox-pi/releases/ Pick the latest version of the *Release* branch and not the *Developer* version.
2. Uncompress it.
3. Download Etcher (http://etcher.io/) so you can burn the image to the microSD. We recommend this program even if you have another method for burning, as it actively verifies that the image has been successfully burnt.
4. Take the microSD card out of the ConnectBox (you’ll need to open the case to do this)
5. Burn the image to the microSD card using Etcher.
6. Pop it back in the ConnectBox and start it.

Note: You won’t be able to use the internal storage on the microSD for data with this process, but if you’re using external USB storage, that won't be a problem. There is a process that allows you to dual partition the internal microSD for use both for the OS and for your media, but it’s for advanced users: https://connectbox.technology/wp/utilizing-your-existing-microsd-boot-card-for-your-media-files/