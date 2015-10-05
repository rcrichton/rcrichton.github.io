---
layout: post
title: "Installing a Nexus 7 into a Subaru WRX STi"
---

Subaru's aren't exactly known for their sound systems. My '06 Subaru WRX STi is no exception. For some reason, in a 2006 car, Subaru decided to put in a headunit with a combo CD changer and tape deck. I wanted to update my headunit for something a bit more modern and I had an old Nexus 7 (2012) lying. I had seen a few other articles online about tablet installs into cars so I though I'd give it a try myself. In this article I will outline how I went about it.

The Nexus 7 is the perfect size for the job at hand. It fits almost perfectly in the stock location. My Subaru's interior trim had already been cut out slightly for an aftermarket headunit which allowed it to fit perfectly. The bad news was that this aftermarket install was a mess so the first thing that I had to do was tidy up the wiring and get rid of what I didn't need.

![](/images/nexus7-headunit/5656809476393208851.jpg)

![](/images/nexus7-headunit/IMG_20140913_125235.jpg)

I cut off the entire loom that went to the stock radio, shortened it and rewired it back to the stock plug. [This wiring pinout](http://ae64.com/WRX-pinout.htm) was pretty handy.

![](/images/nexus7-headunit/IMG_20140913_133427.jpg)

![](/images/nexus7-headunit/IMG_20140914_112544.jpg)

Ah, much neater. Next, I needed to install a small amp to amplify the sound from the Nexus 7's 3.5mm jack to the cars speakers. I chose a [Lepai LP-2020A+](http://www.amazon.com/Lepai-LP-2020A-Tripath-Class-T-Amplifier/dp/B0049P6OTI). It's pretty cheap, small and, from some reviews online, it punches out of its weight class for such a small, low powered amp.

I spliced in some wires for the left and right speakers into my rebuilt loom. This way it would be easy to go back to stock if I ever needed to. I also spliced in a cigarette lighter connection to the power wires so that I could power the amp.

![](/images/nexus7-headunit/IMG_20141102_185255.jpg)

After a bit of testing with this setup I found that there was ALOT of electromagnetic interference coming from the alternator. There was a bad wine that got louder as the revs increased. This equipment was obviously not designed to be used in a car.

To solve this problem I purchased a ground loop isolator which filters out the noise on the cable from the Nexus 7 to the amp. This worked pretty well and got the noise levels down to almost nil. [This is the ground loop isolator that I used](https://www.soundmatch.co.za/Products/Product/2220/pac-lpgl-2-locpro-universal-ground-loop). I stuck this down with some double sided tap to make sure it didn't move around.

(Also pictured is a bluetooth module that I bought, but I didn't ever get this to work reliably so at the moment it is unused.)

![](/images/nexus7-headunit/IMG_20150321_100918.jpg)

![](/images/nexus7-headunit/IMG_20151003_120019.jpg)

To power the tablet I used a USB cable from the existing cigarette lighter and a USB adapter that supports 2.1amp output. The Nexus 7 fitted pretty perfectly in the space available and the easiest way I found to mount it was to use duct tape :) (the sophisticated man's tool). I also put some adhesive foam strips on the brackets that held the old unit in place for some stability on the back of the Nexus 7 (you can see these in the image above). This seems to hold the tablet in place pretty well and is pretty easy to remove if needed.

![](/images/nexus7-headunit/IMG_20151003_120032.jpg)

Here you can the final fitment. It came out pretty perfect.

![](/images/nexus7-headunit/IMG_20151003_120338.jpg)

Next up is the software and firmware hacking to make for a good in-car experience. Firstly, I needed the tablet to power on when I started the car. Luckily this turned out to be pretty simple. There is a [flag that you can set](http://forum.xda-developers.com/showpost.php?p=36479803&postcount=37) on the bootloader that allows the Nexus 7 to power itself on whenever it is charging. It's as simple as:

```
$ fastboot oem off-mode-charge 0
```

So, whenever I turned on the car's accessories the tablet turned on. Perfect.

Now, I needed to get it to power down when I turned the car off. This proved to be more challenging. At first I tried to use an app ([autosleeper](https://play.google.com/store/apps/details?id=com.as.powerchecker&hl=en)) that automatically sleeps the tablet by turning off the screen whenever it wasn't charging.

![](/images/nexus7-headunit/autosleep.webp)

This worked fairly well but didn't turn the tablet off completely so it eventually drained all power from the tablet. Booting it up the next time I drove the car would lead to bootloops because the tablet couldn't charge fast enough with an empty battery. Not good enough.

The app also had an option to power down the tablet but this required the tablet to be rooted. So, my next step was to root the tablet. I installed Cyanogenmod to get an easy root. It turned out to be a fairly straight forward process. I followed [the official guide](https://wiki.cyanogenmod.org/w/Install_CM_for_grouper) on the Cyanogenmod wiki. I then refitted the tablet and tried out the app again.

Unfortunately, it didn't work out too well. The autosleep app is pretty buggy and the tablet would only powerdown directly after you set the powerdown setting and after that it would just sleep the tablet as usual. That wasn't workable. I have since settled for [a simple app](https://play.google.com/store/apps/details?id=com.superappslab.shutdown&hl=en) that gives me a powerdown button on my homescreen (this also requires root access). That works pretty well but I have to remember to powerdown the tablet each time I turn off the car, not ideal but it works.

For volume control I use an app called [Virtual Volume Button](https://play.google.com/store/apps/details?id=it.claudio.chimera.virtualvolume&hl=en). It provides floating on-screen volume controls and works great. I set it up to have an up and down volume button and to display the overall system volume on each volume adjustment.

Overall, this setup works really well. I use Google Maps for navigation and Google Play Music with offline syncing to play all my music. I also have a [bluetooth ODB2 adapter](http://www.obdlink.com/mxbt/) that can read and display some statistics about the inner-workings of my car. The tablet boot s when I turn the car on and I can shut it down with the touch of a button. The on-screen volume buttons allow me to control the volume from any screen. I think its quite an upgrade over stock. Next up, I need to get some decent speakers in there!

Here is a short video of the end product. Enjoy!

<div class="videoWrapper">
  <iframe width="560" height="315"  src="https://www.youtube.com/embed/f_U_1RQrhf4" frameborder="0" allowfullscreen></iframe>
</div>
