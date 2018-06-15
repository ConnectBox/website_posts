# CONNECTBOX TEMPERATURE TESTING

I was able to get in some temperature sensors to start doing the heat measurements on just how hot the ConnectBox can get before we melt it.  This is in response to a field request from a jungle location where they are worried about our units overheating.  So set up the following system:

## Test Setup

Took one of our latest HATs with the OLED and got a unit up and running inside one of our normal cases.  Got the unit pretty much fully charged up for the test (up to 94% anyways).

Took an Arduino, hacked together a SD card datalogger for it and wrote some code to monitor the temperature and humidity inside the case.

Wrote some Python code for the ConnectBox which monitored and datalogged to disk the battery chip for a number of items.

## Running the Test

1. Started by having the ConnectBox OFF and just getting some baseline numbers for temperature and humidity inside the box (vents uncovered).  Room temperature was about 80°F at the time.
2. Started up the ConnectBox and covered the vents to allow heat buildup during operation
3. After five minuted, pulled the external power plug to make the unit start to use the internal battery
4. At about 2:45:00 into the test, I started a sysbench task to create a simulated CPU load while it calculated the prime numbers up to 200000.
5. Let the battery run down and the unit shut down

![alt text](https://raw.githubusercontent.com/ConnectBox/website_posts/master/temperature_testing/setup.jpg "Test Setup")

## Results

### Temperature/Humidity Results
![alt text](https://raw.githubusercontent.com/ConnectBox/website_posts/master/temperature_testing/image1.jpg "Humidity Results")

From the temperature / humidity graph you can notice a few things.  The unit went from the ambient room temperature of around 80°F to around 107°F in about an hour where it pretty much stabilized.  The unit was idling during this time.  After I started the CPU Stress Test, the temperature rose some more but only by another 10 degrees F or so.  The highest temperature that the unit every reached was only 112°F / 44.6C; well within the unit's range of getting pretty warm but no where near a meltdown.

Took another hour for the unit to cool down to the ambient room temps after the unit shutdown.  Longer than I expected but I guess unsurprising since I did have the vents covered.

### Battery Discharge
![alt text](https://raw.githubusercontent.com/ConnectBox/website_posts/master/temperature_testing/image2.jpg "Battery Discharge")

As expected, the unit had a rather linear discharge of between 480mA to 580mA while idling.  What I find as odd is that the discharge rate increased over time even through the unit was in idle.  Perhaps that is related to the previous chart which show that as the temperature goes up, the efficiency of the battery declines??  Or maybe our OS is having an increasing load over time that we aren't expecting?

As expected, once the Stress Test starts, the CPU needs more juice and there is a dramatic increase in the current required.  But again there is that creep upward whereas I would have expected a more straight horizontal line.

### Battery Drain
![alt text](https://raw.githubusercontent.com/ConnectBox/website_posts/master/temperature_testing/image3.jpg "Battery Drain")

The above battery drain from the initial 94% down to around 2% where the unit shut down automatically shows a fairly constant drain over time.  Oddly enough, we are not seeing the expected the battery's capacity numbers to take a nose dive once the Stress Test starts and the current load increased.  Instead, we actually continue to see a rather linear drain down.

## Take Aways

- We don't look like we need to worry about the temperatures overheating the unit.  It was a fairly warm day here and I couldn't even get the inside of the covered ConnectBox to break 112°F on a heavy CPU load.
- There might be some CPU load/memory leak type issues that are causing the unit to always be more hungry for more current over time.
- The 3400mAh battery seems to be able to give us around 4.5 hour of usable life.