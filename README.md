<!-- <p align="center">
  <img src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/xxxxx.png" width="250"/>
</p> -->
<h1 align="center">WIP - NOT ACCURATE - unJoe Smart Home Configuration</h1>
<h3 align="center">Home Assistant Configuration &amp; Documentation for my Smart House.</h3>
<p align="center">Be sure to :star: my repo!</p>
<p align="center">
<img src="http://hits.dwyl.io/JoeStratton/home-assistant-config.svg"/>
</p>  
<p>
  <img src="https://img.shields.io/github/stars/JoeStratton/home-assistant-config.svg?style=plasticr"/>
  <img src="https://img.shields.io/badge/HA--Version-0.107.7-brightgreen.svg"/>
  <img src="https://img.shields.io/maintenance/yes/2020.svg"/>
  <img src="https://img.shields.io/github/commit-activity/y/JoeStratton/home-assistant-config.svg"/>
  <img src="https://img.shields.io/github/last-commit/JoeStratton/home-assistant-config.svg?style=plasticr"/>
  <img src="https://img.shields.io/github/issues/JoeStratton/home-assistant-config.svg"/>
  <img src="https://travis-ci.org/JoeStratton/home-assistant-config.svg?branch=master"/>
</p>
<hr --- </hr> 

| [Home Assistant Screenshots](https://github.com/JoeStratton/home-assistant-config/tree/master/HA%20Pics/HA%20Screenshots) |
| --- |
| [<img src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/HA%20Screenshots/01-home.PNG"/>](https://github.com/JoeStratton/home-assistant-config/tree/master/HA%20Pics/HA%20Screenshots) |

<hr --- </hr>

<h3 align="left">Home Assistant Hardware</h3> 
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/i7.png" width="95"/>
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Rasp%20Pi%20Logo.png" width="200"/> 
<p align="left">I am using a server for this, but I included the raspberry pi logo because that is all you need to get most of this up and running.
<hr --- </hr>

<h3 align="left">Home Assistant Software</h3>
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/HA%20logo%202%20.png" width="200"/>
<p align="left">Lately I have started to notice the automations becoming sluggish and this is due to the resources of my HA Server becoming occupied with background tasks like device tracking and sensor polling. With the recent release of HASSIO on its new operating system HASSOS I decided now was a good time to upgrade and splinter my automations off my main HA instance onto a dedicated RPi. Splitting my HA tasks across 3 Pis has made a huge difference and my automations have become snappy again whilst all my sensors can run in the background not effecting the performance of my essential tasks. I used the MQTT Statestream to keep all the Pis insync with each other. I have used Hassio with standard Add-On store packages which include Appdaemon for use with HaDashboard, Mosquitto Broker for MQTT Broker & Node-RED for more complex Automation flows. I have now installed a stand alone RPi with Grafana, InfluxDB and Node-RED to take the strain off resources on my HA device and to also have access to a larger hdd for database storage. My config in this repo is a combination of all my Pi's as if you were running it all of the same device to save confusion message me if you would like more info on how I splintered off the automations to a dedicated device.</p>

| [Hass.io](https://www.home-assistant.io/hassio/installation/) | [Mosquitto MQTT Broker](https://www.home-assistant.io/addons/mosquitto/) | [Node-RED](https://github.com/notoriousbdg/hassio-addons/tree/master/node-red) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/HA%20logo.png" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Mosquitto%20MQTT%20Logo.png" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/appdaemon.PNG" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Node-RED%20Logo.png" width="250"/> |

<h4 align="left">Home Assistant:</h4>
<p align="left">As I am still new to Home Assistant (and always learning), I decided to install HASSIO. I have been using HASSIO since December 2017, for anyone new to HA I recommend this type of installation and once you are more comfortable with it I would then look to move onto some of the other methods of installation.</p>

<h4 align="left">MQTT Broker:</h4>

One of the first things I needed to do once I got HA up and running was to setup a MQTT Broker, I decided to use [CloudMQTT](https://www.cloudmqtt.com/) as I found this helpful guide from [BRUH](https://www.youtube.com/watch?v=VaWdvVVYU3A) and was up and running in 15mins. The main problem I had with this method was using a cloud-based service to control my MQTT based light switches. I decided to install Mosquitto Broker from the Hass.io Add-On Store. Doing this means I can host the MQTT Broker locally therefore having control of who can access my devices and data.

<h4 align="left">Node-RED:</h4>

After using HA for a few months, I began to really enjoy the sometimes-complicated methods of using automations, I also came to realise some of the limitations in its implementations. I found a good repo with an easy to follow installation guide by [NotoriousBDG](https://github.com/notoriousbdg/hassio-addons/tree/master/node-red) this handles any of my more complicated flows and conditioning required for my Automations.

<hr --- </hr>
<hr --- </hr>

<h3 align="left">unJoe Network</h3>
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Network%20Topo.png"/>
<p align="left">My Internet is a 100/40Mb/s FTTN solution where the fibre is terminated about 50m up the road and travels down phones lines (VDSL2+) for the remainder I typically achieve speeds of 92/35Mb/s. The core of my network switching devices are made up of Mikrotik Cloud Router Series, whilst my wireless network is comprised of both Altai and UBNT devices. I use a VPN and isolate my Smart Home devices from my Personal and Guest access networks through VLAN's and client isolation is implemented on the guest network.</p>
<hr --- </hr>

UBNT devices are configured by their Web UI and then managed by a CRM Point Device (overkill for 3 devices) they have been set and forget with only firmware upgrades performed if they address any security patches.</br> 

<h3 align="left">Voice Control & TTS</h3> 
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/alexa.png" width="150"/> 
<p align="left">The voice control war has only just hit Australian shores, I dipped my toes into the Alexa waters a few years back with the original Echo and it was a bit of a flop due to nothing being supported in Australia. Once I moved to HA and its Amazon cloud component I dusted off the Echo and now have voice control over a majority of my Smart Home.</p>
<hr --- </hr>

| [Amazon Echo](https://www.jbhifi.com.au/amazon/amazon-echo-plus-with-bonus-philips-hue-bulb-edison/574929/) | [Amazon Echo Dot](https://www.jbhifi.com.au/amazon/amazon-echo-dot-2nd-generation-black/574910/) | [Kodi TTS](https://www.home-assistant.io/components/notify.kodi/)
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Amazon%20-%20Echo.png" height="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Amazon%20-%20Dot.png" width="200"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Kodi%20Logo%202.png" width="200"/> | 

<h4 align="left">Voice Control:</h4>
<p align="left">I use a combination of Amazon Echo and Echo Dot's in conjunction with HA Cloud with its Alexa Integration to enable voice control over most functions in the house. My wife hates the voice control (she wants to be the only female voice of control in our house), but my young boys love it.</p>
* Light Control - LED Strips, Wall Switches and Bulb specific (Brightness, Colour, Warmth etc)</br>
* Climate Control - Control Upstairs/Downstairs Climate (temp up/down etc) turn ceiling fans on off (no speed control yet)</br>
* Media Control - Turn on/off Media Devices, player control of Kodi Media</br>
* Group Control - I can turn on/off all devices in a group e.g. "Alexa, turn off Downstairs" as we go to bed turns off all devices</br>
* Scene Selection - Enable predefined scenes with voice command</br>
* Automation Control - Perhaps the best part the ability to toggle Automations "Turn on Morning Cartoons", "Turn on &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;Entertaining mode"</br>
<h4 align="left">Announcements TTS</h4>
<p align="left">For TTS I use a combination of Kodi devices (I have one always on downstairs) and Android tablets with Lannouncer. I love the TTS and notifier component this is where you can start to give your Smart Home some personality as well as keep informed of events & reminders. I also use it for feedback after certain actions like confirmation of fan speed settings.</p>
* Notify of Presence - Unique messages played upon my wife and I arrival home</br>
* Notify of Tasks - Msg played when washer/dryer have finished their respective cycles, with 30min reminders until emptied</br>
* Reoccurring Events - Reminder msg to take out bins night before rubbish collection day, with alt msg for recycling week</br>
* Warning Events - Notify of Alarm Trigger, Arming, Outdoor Motion, Smoke/C02 Detection</br>
* Automation Notify - Notify on certain Automation runs like when sun is above horizon and lights are still on I turn them off &nbsp; &nbsp; and have TTS play a message "I guess I better turn the lights off or Tina will leave them on all day"
<hr --- </hr>
<hr --- </hr>

<h4 align="left">Smart Fan:</h4>

I was excited to get this fan as it was to go into the playroom for the kids the room has no windows or is quiet closed off so airflow isn't the best. When it arrived I went to integrate it with HA to realise that it is one of the few Xioami devices that didn't have auto discovery or a custom component for it. I reached out to the community and our very own @syssi had a component for me to do testing with in the matter of hours. We are actually only about 50% through this as it is waiting for me to finish testing the remainder of its functions and it will be added in future release. [Smart Pedestal Fan](https://community.home-assistant.io/t/mi-smart-pedestal-fan/49998/52).

<h4 align="left">Power Switches:</h4>
<p align="left">I have lost count of how many of these things I have around the place, I use single plugs for those higher power consumers like the washer/dryer & fridges. The rest I have a heap of smart power strips powering everything else to give me insights into power consumption but mainly to control when devices are allowed to be on and consuming power. I have a strip setup in the laundry that all my battery appliances plug into (all the mentioned above) and this only turns during between 1-4am and only for long enough to charge all connected devices to 100%. I also do the same for my outdoor lighting they are all connected back to these strips and I then automate them to turn on x time after sunset for x amount of time and turn off again. Once bed time script is enabled they are then set to turn on upon motion in their areas. I also use one for my Christmas lighting to ensure they are on for the kids to enjoy (as I used to forget to turn them on until after they are in bed) and turn off by midnight.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Media Control</h3> 

| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Samsung%20TV%20Logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Kodi%20Logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Nuc%20Logo.svg" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Broadlink%20logo.jpg" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Pusle%20Eight%20Logo.jpg" width="150"/> |
| --- | --- | --- | --- | --- |

<p align="left">I have chosen Samsung as my screens of choice and Kodi as the media players. I have this combo setup in my Media Room, Master Bedroom, Study and Entertainment Area. Integration into HA for Kodi is straight forward (actually I think the latest update to HA 0.69.1 introduced auto discovery for Kodi so even easier now) but I found the Samsung Smart TV component without anywhere near the amount of control I needed. I use a combo of Broadlink RM3 mini and Pulse Eight HDMI-CEC adaptors to gain the control I wanted.</p>
<hr --- </hr>

<h3 align="left">Multi Room Audio</h3> 

| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/xsqeeze%20logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Hifi%20Berry%20Logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Yamaha%20Logo.jpg" width="150"/> |
| --- | --- | --- |

<p align="left">I already had a bunch of media playing capable devices with speakers so I opted to take advantage of these over a dedicated multi-room music option like Sonos. I am using my Kodi devices with Logitech Squeezebox to sync audio across rooms in the house although I normally only have one room playing at a time unless we are entertaining.</p>
<hr --- </hr>

<h4 align="left">Music Server:</h4>
<p align="left">I used to have the Logitech Squeezebox Server installed on my NAS but its functionality died a few updates back so I moved the server across to my (mostly always on) Configuration PC in the study. I am thinking of moving this to a RPi with MAX2Play need to look into this as I have a few Rpi around the house that only have Libreelc Installed. It really is a shame Logitech shelved this product as its functionality in some ways is still far superior of those in the market today. The main drawback to this setup over a dedicated system like Sonos is the hardware timing isn't there for a pure audiophile, however if you don’t have multiple groups of speakers in the same room you wouldn't notice. Walking from room to room it works well enough to carry music sync throughout the house. Spotify dropped LMS support last year but where one drops the ball the community takes over with a plugin called spotty.</p>
<h4 align="left">Playback Devices:</h4>
<p align="left">I use a combination of many things in order to get music to where I want it.<br>
Kitchen<br>
I use a Samsung Tablet I already have installed there and a Bluetooth speaker. To automate music playback, I use tasker and a python script in HA I use this one the most when doing the dishes, I can just say "Alexa, turn on Kitchen Spotify" HA and Tasker do the rest. Tasker unlocks the screen, opens Spotify starts playing my last playlist and opens the screen to the album artwork. If after sunset the led strip above the kitchen sink changes colours to match the Album artwork.<br>
Garage<br>
I use a Rpi Zero W with HifiBerry Mini Amp it’s just a low powered amp with about 3W but perfect for small areas where you would never turn the sound right up. I use this with some old speakers I had lying around works well, I need to get another Amazon Dot for the Garage so I can turn it on and off with Alexa.<br>
Bathroom<br>
I use a Rpi Model B+ with HifiBerry Amp2 and official 7" touchscreen with a Yamaha NS-IC600 in Ceiling Speaker. These speakers are dual firing meaning they can handle 2ch sound out of the single speaker ideal for smaller spaces where installing 2 speakers isn't practical (they cost the same as buying 2 individual speakers so no savings there). This setup runs Kodi in the background and uses HADashboard as its interface. There is an Echo Dot located about 2m away in the adjacent room so it is all voice controlled however my wife wants physical control for herself and any guests we have, so there is light, heater and fan control via this interface as well as some scenes that run morning briefing for myself and wife and a script that will play music whilst showering.<br>
Toilets<br>
To not miss out on any action when one needs a toilet break I have a RPi Zero with MiniAmp installed in the ceiling cavity above where the cheap Chinese dual firing 4" speaker is. There is one of these for the downstairs and upstairs toilets as well as in the hallway ceiling space.<br>
Entertainment Area<br>
In this area I have a RPi Model B+ and I initially connected it to the 32" Samsung TV via HDMI used the TV built in speakers for playback, whilst this was sufficient for watching sport I wanted more for music playback. I went with the HiFiBerry Amp2, this amp is capable of providing 60W and it packs a pretty decent punch for what it is. I paired this up with a set of Yamaha NS-AW392 Outdoor Speakers (these speakers are awesome). This combo ensures are entire block will know when we are entertaining, during the click here to purchase phase I could hear my wife in the background saying you are getting them for background music right? Of course babe :grin:.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Security</h3> 
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Android%20Things.png" width="200"/>

There are many takes on Alarm Panels in the HA Forums I decided to go with this one [MQTT Alarm Control Panel](https://community.home-assistant.io/t/mqtt-alarm-control-panel-for-raspberry-pi-and-android/26484) which utilises the HA Manual Alarm Panel component. It was really easy to setup with great detailed instructions, installed this on the recommended hardware metioned in the project.

<hr --- </hr>

<h4 align="left">Cameras:</h4>
<p align="left">Exterior<br>
On the exterior of the property I use HIKVision cameras they have motion detection night vision and integrate into HA without too much issue.<br>

Interior<br>
In the house I have TP Link NC250 and these integrate to HA with the "generic" camera platform there is a bit of lag displaying these in the HA UI and in HADash but I don’t really use HA for viewing the camera feeds.<br>
I also bought a heap of Xiaomi Miji 1080p IP Cameras thinking they could be hacked and easily added to HA it appears this was not the case so I have about 10 of these cameras around the place but not integrated with HA.</p>

<h4 align="left">Smoke Detectors:</h4>
<p align="left">I have installed 2 Xiaomi Honeywell Smoke Detectors One Downstairs and the other upstairs. These sound an alarm when they detect smoke as you would expect they also flash the gateway LED red and the downstairs and hall light bulbs will flash red upon smoke alarm trigger. If alarm has been triggered and we are "away" it will fire off notifications to my wife and mines phones.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Garden</h3> 

<p align="left">I have a pretty simple garden irrigation system using a Sonoff Basic and 12V Solenoid Valve. I also have a bunch of Moisture sensors conting back to a Raspberry Pi Zero.</p>
<hr --- </hr>

<h3 align="left">My Favourite Projects</h3> 

<p align="left">I used the below links for intergration into my own HA or I plan to at some point in the future.</p>
-
- [Alexa as a Media Player](https://community.home-assistant.io/t/echo-devices-alexa-as-media-player-testers-needed/58639)<br>
  <a>**More to come as I can remember them**<a name="bottom" href="https://github.com/JoeStratton/home-assistant-config/blob/master/README.md"><img align="right" border="0" src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/Back%20to%20the%20Top.png" width="45" ></a><br>
<hr --- </hr>
<hr --- </hr>
