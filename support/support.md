# Support

This is the Support page.

## Send Feedback to the Developers: 
[ConnectBox Feedback Form](http://http://geodirk-001-site1.btempurl.com/ "Feedback Page")

## Google Groups Forum / Mailing List:
[ConnectBox Google Groups Forum](https://groups.google.com/d/forum/connectbox "ConnectBox Google Groups Forum")

## Add an issue to GitHub:
[ConnectBox Github Project](https://github.com/ConnectBox/connectbox-pi/issues "GitHub Project Issues")

<hr />
<hr />

# Frequently Asked Questions (FAQ):

## Reset your ConnectBox back to "factory condition"
There are a few steps (a few more than we’d like to be honest, but we’re working on the update mechanism).

1. Download the latest release image from GitHub: https://github.com/ConnectBox/connectbox-pi/releases/ Pick the latest version of the *Release* branch and not the *Developer* version.
2. Download Etcher (http://etcher.io/) so you can burn the image to the microSD. We recommend this program even if you have another method for burning, as it actively verifies that the image has been successfully burnt.
3. Take the microSD card out of the ConnectBox (you’ll need to open the case to do this)
4. Burn the image to the microSD card using Etcher (Etcher will burn the image file that you downloaded without requiring decompression)
5. Pop it back in the ConnectBox and start it.


## Connecting to your ConnectBox via SSH
By default, your ConnectBox has SSH disabled over the LAN port.  It is relatively simple to turn it on.  Essentially, you need to create a specifically named directory and a file in that directory on your external USB stick.  Have it inserted, then boot the device.  The ConnectBox will automatically see those items and thereby enable SSH support over the LAN.  The folder must be named:
 
**.connectbox** (in all lowercase and with the preceeding period)

Inside that folder, you will need to put a file called: **enable-ssh** again without the quotes.  The file can contain information or be blank.

Under *Windows*, the Operating System won't let you make folders that start with a period so you need to do something a bit different.  Open up a Command Prompt, (hold down the **WINDOWS-R** keys and a window will pop open. Type **cmd** into it and hit the OK button).  From the terminal window, go to your USB drive by typing in the following:

**D:** where D: is the drive letter of your external USB stick.

Then type **mkdir .connectbox** which will allow you to make that special folder with the period in the front of the name.  Follow this with the command **cd .connectbox** to move inside of that folder.  Then make the file with the command **type nul >enable-ssh**.  That is all there is to doing that under Windows.

SSH Login Credentials:

_username:_ **root**

_password:_ **connectbox**

## Enabling PHP for your ConnectBox web Server

The ConnectBox software image does not come with PHP installed by default. However, with a few commands, you can enable PHP to work with your files on your external USB stick.  Follow the instructions below:

* Using the above described method, connect to your ConnectBox via SSH to get a BASH console and that your ConnectBox has internet access.  Easiest way to do this is to connect an Ethernet cable from your router to the ConnectBox's LAN port.  Depending on the model of ConnectBox that you have, you may need to take the case off to get to the LAN port.
* The first thing we want to do is update the code repositories for obtaining the PHP libraries.  From the commandline, type in the following: `apt update` and hit Enter on your keyboard.  Multiple lines will scroll by as the operating system updates itself.  Once it returns waiting at the command prompt, you can proceed with the next step.
* We now want to install the current PHP libraries.  We do that by typing in the following and hitting Enter: `apt install -y php-fpm`  This will take a few minutes to complete.
* Once PHP has been installed to the system, we need to inform the webserver to start to use it.  We'll need to update a config file with new information for the system to know how to use PHP.  Type the following at the commandline and press Enter: `nano /etc/nginx/sites-available/connectbox_static-site.conf`  An editor will show up with the contents of the configuration file. We want to make the following two changes to the file as shown in green:

<pre>
server {
    listen 80;
    server_name $hostname;
    root /media/usb0;
    index <span style="color:green"><b>index.php</b></span> index.html index.htm;
    error_page 404 /index.html;
    access_log /var/log/connectbox/connectbox-access.log;
    error_log /var/log/connectbox/connectbox-error.log error;
    rewrite_log on;

location /chat {
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header Host $http_host;
  proxy_redirect off;
  proxy_pass http://127.0.0.1:5000/chat;
  # Never cache
  expires -1;
}

location /admin/api {
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header Host $http_host;
  proxy_redirect off;
  proxy_pass http://127.0.0.1:5000/admin/api;
  # Never cache
  expires -1;
}

location /__connectbox_assets__ {
  alias /var/www/connectbox/connectbox_default;
  location ~ \.json$ {
    expires -1;
  }
}


    # Admin interface
    location /admin {
      alias /var/www/connectbox/connectbox_default;
      try_files $uri /admin/index.html;
    }
    <span style="color:green"><b>
    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    }
    </b></span>
}
</pre>

Use **CTRL-X** followed by **Y** to save the changes to the file and exit the editor.


* We'll need to create a test file to see if PHP will work correctly. Type the following into the commandline to create a new file on the root folder of the USB drive: `nano /media/usb0/hello.php` and once the editor opens up to a blank page, type in the following:

```
<?php
    print("Hello World");
?>
```

Again, use  **CTRL-X** followed by **Y** to save the changes to the file and exit the editor.

* Final step at the console line is to restart the websever.  The command to do this is: `systemctl reload nginx`

* Now that PHP is installed, we need to tell the ConnectBox to run using the Static Web Page mode instead of the default Icon-Only method that just serves up file listings.  We do that by logging into the Admin Panel.  Connect up your phone to your ConnectBox and once connected, type `http://connectbox/admin` into the address bar of your browser.  Log in using the admin password (defaults to `connectbox`).  Select the `Configuration` menu item, followed by `Web Server`, then `Static site configuration`. Toggle the buttons so that `Enabled` is selected followed by clicking on the `Update` button.  The device will reconfure itself so that it will now serve up webpages instead of just presenting files.
* Test that the changes worked by typing `http://connectbox/hello.php` which will display "Hello World" on the screen. If your device tries to download the file instead of rendering it, go back and ensure that the Static site configuration is enabled.
* You are now all set to use PHP in your web applications.

## Installing WordPress onto your ConnectBox (Advanced)

* Using the above described method, connect to your ConnectBox via SSH to get a BASH console and that your ConnectBox has internet access.  Easiest way to do this is to connect an Ethernet cable from your router to the ConnectBox's LAN port.  Depending on the model of ConnectBox that you have, you may need to take the case off to get to the LAN port.
* Enter in the following commands at the console line:
  * `apt-get update`
  * `apt install -y mariadb-server`
  * `sudo systemctl start mariadb.service`
  * `sudo systemctl enable mariadb.service`
  * `mysql_secure_installation`
    * `Enter current password for root (enter for none):`  <<===Just hit Enter here
    * `Set root password (Y/n)`  <<===Add in a password here by replying Y
    * `Remove anonymous users (Y/n)`  <<===Just hit Enter here
    * `Disallow root login remotely? (Y/n)`  <<===Just hit Enter here
    * `Remove test database and access to it (Y/n)`  <<===Just hit Enter here
    * `Reload privilege tables now? (Y/n)`  <<===Just hit Enter here
  * `mysql -u root -p`
								<<===When asked use the password set above
    From within the MySQL command prompt, type in these commands to create a database for WordPress and a user
    * `CREATE DATABASE connectbox DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;`
    * `GRANT ALL ON connectbox.* TO 'wordpressuser'@'localhost' IDENTIFIED BY 'password';`  <<=== note that if you change password then it must be changed below as well in wp-config.php
    * `FLUSH PRIVILEGES;`
    * `EXIT;`  <<===Exits you back to the regular console prompt
  * `apt install -y php-fpm php-mysql php-curl php-gd php-intl php-mbstring php-soap php-xml php-xmlrpc php-zip php-cli php-imagick`
  * `nano /etc/nginx/sites-available/connectbox_static-site.conf` 
    * Modify this existing line to add in `index.php` before the other index types
    <pre>index index.php index.html index.htm;</pre>
	
	You also need to modify the root file system to:
	<pre> root /var/www/html/wordpress; </pre>
	
    Add this whole section before the end of the last closing } character
    
	<pre>
    location ~ \.php$ {
        include snippets/fastcgi-php.conf;
        fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    }

    location = /favicon.ico { log_not_found off; access_log off; }
    location = /robots.txt { log_not_found off; access_log off; allow all; }
    location ~* \.(css|gif|ico|jpeg|jpg|js|png)$ {
        expires max;
        log_not_found off;
    }</pre>
  * `systemctl reload nginx`
  
  
  Lastly, we install the latest version of WordPress onto the USB drive.

  * `cd /tmp`
  * `curl -LO https://wordpress.org/latest.tar.gz`
  * `tar xzvf latest.tar.gz -C /var/www/html`
  * `sudo chown -R www-data:/var/www/html/wordpress`
  * `sudo systemctl start mariadb.service`
  * `sudo systemctl enable mariadb.service`
  * `cd /var/www/html/wordpress`
  * `cp wp-config-sample.php wp-config.php`
  * `nano wp-config.php`
    
    Change out the following lines:
    <pre>/** The name of the database for WordPress */
    define('DB_NAME', 'connectbox');
    
    /** MySQL database username */
    define('DB_USER', 'wordpressuser');
    
    /** MySQL database password */
    define('DB_PASSWORD', 'password');  <<=== note that if you change password then it must be changed below as well in wp-config.php
    </pre>
    Add in the below line somewhere in the config file:
    <pre>define('FS_METHOD', 'direct');</pre>
	
	Write out the file and exit nano
	
  * `systemctl reload nginx`

* Now that everything is installed, we need to tell the ConnectBox to run using the Static Web Page mode instead of the default Icon-Only method that just serves up file listings.  We do that by logging into the Admin Panel.  Connect up your phone to your ConnectBox and once connected, type `http://connectbox/admin` into the address bar of your browser.  Log in using the admin password (defaults to `connectbox`).  Select the `Configuration` menu item, followed by `Web Server`, then `Static site configuration`. Toggle the buttons so that `Enabled` is selected followed by clicking on the `Update` button.  
* The device will reconfure itself so that it will now serve up webpages instead of just presenting files.  Wait around 30 seconds for the device to update itself and get organized.  After that, log back into the regular ConnectBox home page (http://connectbox) and if all went well, you will see the installer for WordPress.

With WordPress running you may need to create a micro-USB based swap file to enable ram to not overload.  To do this, you can see what the current swap file situation is:

  * `sudo swapon --show`
  
This will show the current swap file.  By default there is a ram based swap file /dev/zram1 partition about 119M  To add a second swap file of 1GB do the following

  * `sudo fallocate -l 1G /swapfile`
  * `sudo chmod 600 /swapfile`
  * `sudo mkswap /swapfile`
  * `sudo swapon /swapfile`

This now creates the swapfile and enables it.  to make the change permanent we need to edit /etc/fstab as follows:

  * `sudo nano /etc/fstab`
  
Paste the following line into the file:

  * ` /swapfile swap swap defaults 0 0`
  
Then write the file with ^O then exit with ^X

To verify the change check the swap situation now with:

  * `sudo swapon --show`
  
  You should now see something like:
 NAME       TYPE        SIZE USED PRIO
/swapfile  file       1024M   0B   -2
/dev/zram1 partition 119.6M 7.3M    5

The 'Swappiness' of the memory now needs to be adjusted since
we were using 100% ram before lets lower the value:

  * `sudo sysctl vm.swappiness=60`

and then to make this persistant let edit the /etc/sysctl.conf file:

  * `sudo nano /etc/sysctl.conf`

At the end of the file you will find the line 'vm.swappiness=100' change this to 'vm.swappiness=60'

Then write the file with ^O and then exit ^X

you can check the current value of 'Swappiness' with 

  * `cat /proc/sys/vm/swappiness`

and the output should be 60

  
