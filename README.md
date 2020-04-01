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

<h3 align="left">Fan & Lighting Control</h3> 

| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Xiaomi%20Logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Sonoff%20Logo.png" width="200"/> |
| --- | --- |

<p align="left">I like many others use Sonoff single, daul and 4ch switches to control the power to my lights over Wi-Fi. These units need to be flashed with firmware (plenty of info out there on how to do it, I used Tasmota Firmware). I have placed all of my switches behind the wall plate (Gyprock walls) had to make fairly large holes to accomodate the 4ch model but can always plaster it back up afterwoods(took me about 2 months of nagging to sand the patches and re paint walls).</p>
<hr --- </hr>

| [Sonoff Basic](http://sonoff.itead.cc/en/products/sonoff/sonoff-basic) | [Sonoff Dual](http://sonoff.itead.cc/en/products/sonoff/sonoff-dual) | [Sonoff 4CH](http://sonoff.itead.cc/en/products/sonoff/sonoff-4ch) | [Sonoff RF Bridge 433](http://sonoff.itead.cc/en/products/appliances/sonoff-rf-bridge-433) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Sonoff%20Basic.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Sonoff%20Dual.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Sonoff%204ch.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Sonoff%20RF%20Bridge.jpg" width="250"/> |

<h4 align="left">Light Switches:</h4>
<p align="left">I use the Sonoff Basic & Dual for single and dual wall switches respectively and these are pretty straight forward flashed with Tasmota Firmware and added to HA via the MQTT Switch component. I installed all of these switches behind the existing wall plates and connected the original switch to the available gpio pins on the board.</p>
<h4 align="left">3 Speed Ceiling Fans:</h4>
<p align="left">I use the Sonoff 4Ch again flashed with the same firmware and I connected first ch to the high speed of the fan, 2nd & 3rd ch are connected to the med and low via a 6uf capacitor. The last channel is connected to the light switch again I used the gpio pin to connect the board to the wall plate, so the light can still be controlled via the wall switch. These can now be voice controlled via Alexa turn fan on/off turn fan speed to low, medium & high.</p>
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Fan%20CCT.png"/>
<h4 align="left">Garage Door:</h4>
<p align="left">I have an RF controlled relay connected to my garage door opener and I use the Sonoff RF Bridge to control it. I also have a Xiaomi Door Sensor to tell me whether the garage door is open. At the moment I use a Xiaomi smart switch located in the garage to control the door whilst I’m in there "Single Click" up, down and stop, "Double Click" Garage Light, Long Click manual up and down this way I can adjust how open I would like the door to be if I’m working in there. I wish to add a Bluetooth beacon to introduce geofencing to have the door open automatically when we are arriving home but atm there isn't enough room to fit the car due to my abundance of toys I no longer use.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">LED Lighting</h3> 
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Xiaomi%20Logo.png" width="150"/>
<p align="left">I have a few RGBWW strips around the house used mainly for mood lighting aswell as practical lighting on the staircase. These are all controlled by MiLight Wi-FI LED controllers with appropriate power supplies.</p>
<hr --- </hr>

| [5m RGBWW LED Strip](https://www.banggood.com/5M-RGBW-RGBWW-4-In-1-SMD5050-300LEDs-Strip-Light-Non-waterproof-Indoor-Use-DC12V-p-1155159.html?rmmds=myorder) | [LED Power](https://www.banggood.com/AC100-240V-To-DC12V-6A-72W-Power-Supply-Adapter-for-LED-Strip-Light-p-1111858.html?rmmds=myorder) | [Mi Light Wi-FI Controller](https://www.banggood.com/Mi-Light-24A-DC12-24V-2_4G-RF-4-Channel-RGB-LED-Remote-Controller-p-968820.html?rmmds=myorder) | [LED Diffuser](https://www.banggood.com/3050CM-XH-U1-U-Style-Aluminum-Channel-Holder-For-LED-Strip-Light-Bar-Under-Cabinet-Lamp-Lighting-p-1142676.html?rmmds=myorder&cur_warehouse=CN) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/LED%20Strips.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/LED%20PSU.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Mi%20Light.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/LED%20Diffuser.jpg" width="250"/> |

<h4 align="left">Staircase Lighting:</h4>
<p align="left">I have 80cm LED strips on the underside of each step installed with a LED Diffuser the steps are split by 2 Mi Light Wi-Fi controllers. I have all odd stairs on one controller and all even on the other so I can have the colours alternate when it’s a special occasion or seasonal holiday. Their standard setup is to turn on (warm white) 30mins after sundown and turn off with the activation of the bed time script. Once the bed time script kicks in the Staircase LED strips are set to turn on only during motion detection of the motion sensor at the top of the stairs, they turn off again 5 mins after last motion detection. Each alternate strip is soldered together and placed into a channel countersunk in to the step which is then covered by bamboo floor boards. The strips themselves are installed on the underside of the step overhang so they face back towards the step below it was a massive job (lots of swearing) and now all cabling is hidden it looks great and effect when stairs are light is awesome really makes the staircase a feature of the house. Each strip works out to be around 5.6m in length so I decided to power them sufficiently with 12v 6A 72W PSU.</p>
<h4 align="left">LED Back Lighting:</h4>
<p align="left">I purchased 3 x 5m LED strips to do the staircase mentioned above and had about 3.5m left after the project was complete so rather than let them go to waste (like they were ever going to be) I decided to place a few strips behind my PC Monitor, Media TV, Bedroom TV and Entertaining TV. Each strip is controlled by the Mi Light Wi-Fi LED controller and on normal nights they just give a soft blue glow from behind the screens. When music is playing I found a project where they had a script which would change the LED colour to match that of the Album artwork that was playing at the time. I also aim to port this across to work with Kodi and the TV Show/Movie Poster colours.</p>
<h4 align="left">Entertainment Lighting:</h4>
<p align="left">I have 20m festoon lighting with different sized Edison bulbs, it came with 20w bulbs (when turned on it light up not only the entertainment area but the whole suburb) I replaced them with 2-4w bulbs but I fear the damage to my retinas may be permanent. I also have 3 x 10m lengths of LED fairy lighting which run off USB 5V. To power them I use a Xiaomi Power Strip which has 3 Power and 3 USB points.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Appliances and Smart Power</h3> 
<img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Xiaomi%20Logo.png" width="150"/>
<p align="left">I am slowly replacing my Appliances with smarter connected devices as they need replacement, in the mean time I am installing Xiaomi ZigBee power strips and plugs to give me the ability to add them into my automations. These power switches also monitor power consumption which is an added bonus but I am yet to fully take advantage of this feature by graphing my consumption and finding out my biggest areas for saving on my bill.</p>
<hr --- </hr>

| [Xiaomi Robot Vacuum](https://www.banggood.com/Original-Xiaomi-Mi-Home-Smart-Robot-Vacuum-Cleaner-LSD-and-SLAM-1800Pa-5200mAH-with-APP-Control-p-1098131.html?rmmds=myorder&cur_warehouse=CN) | [Xiaomi Smart Mop](https://www.banggood.com/New-Arrivals-Xiaomi-Handheld-Stay-Upright-Electric-Mop-Long-Grip-Handle-Mopping-Robot-Clean-Machine-p-1171073.html?rmmds=myorder&stayold=1&cur_warehouse=CN) | [Xiaomi Wi-Fi Pedestal Fan](https://www.banggood.com/Original-Xiaomi-Mi-Smart-DC-Frequency-Electric-Stand-Fan-with-APP-Remote-Control-Natural-Wind-p-1156931.html?rmmds=search) | [Xiaomi Smart Power Switches](https://www.banggood.com/Original-Xiaomi-Mijia-Four-Digit-Individual-Control-Power-Strip-Socket-with-3-x-USB-Quick-Charge-p-1253472.html?rmmds=myorder&cur_warehouse=CN) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/RoboVac.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Smart%20Mop.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Smart%20Fan.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Smart%20Power.png" width="250"/> |

<h4 align="left">RoboVac:</h4>
<p align="left">This vacuum actually does a pretty good job of the day to day pickups of random crumbs my boys seem to generate at will. We still use the Dyson stick for a weekly clean or a big spill, but the RoboVac is set to clean twice a day and it just goes about its business we have lots of obstacles which it navigates with ease including the large dining table with 6 chairs. There is a new zone cleaning feature which I would like to take advantage of but in order to do that I would need to upgrade my app version and I'm still adding devices to HA which I lost this ability moving to newer versions of the app.</p>
<h4 align="left">Smart Mop:</h4>
<p align="left">This mop is not our main one as we have a steam mop for the tiled and bamboo flooring which is needed with two boys rampaging throughout the place. The thing I like about this mop is it has a built in light and is easy to whip out on those liquid spills that haven’t dried hard yet. As for smart features it really only has battery level indicators and alerts when it’s time to change over the mop pad.</p>

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

| [Samsung Smart TV](https://www.jbhifi.com.au/) | [Nuc 7th Gen Core i7](https://www.umart.com.au/Intel-NUC-BOXNUC7i7BNH-Barebone-Kit---7th-Gen-Core-i7_39118G.html) | [Broadlink RM3 Mini](https://www.banggood.com/Broadlink-Black-Bean-Smart-Home-Wifi-Remote-IR-Controller-Universal-Appliances-Smart-Control-p-1049494.html) | [Pulse Eight CEC Adaptor](https://www.pulse-eight.com/p/104/usb-hdmi-cec-adapter) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Samsung%20TV.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Nuc.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/RM3%20Mini.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Pulse%208%20CEC.png" width="250"/> |

<h4 align="left">Samsung Smart TVs:</h4>
<p align="left">As stated above the Samsung TV Component doesn't give much control at all, so I use Pulse Eight CEC Adaptor connected to the Media Nuc in conjunction with the CEC component to give me more control over the TV it also allows the family to control Kodi with the standard TV remote. The bedroom screen CEC adaptor doesn't pass all functions through so I also use a RM3 mini to get the remainder of control via IR blaster (I already have one there to control the air conditioner). Lastly I have a RPi Kodi so it has CEC natively and I can control TV and Kodi as I want there is an RM3 Mini there also for controlling the Fairy lights modes.</p>
<h4 align="left">Kodi Hardware:</h4>
<p align="left">- In the Media Room I run the latest 7th gen i7 Intel NUC with support for 4k playback, it has 16gb RAM and a SSD overkill for &nbsp; a Media PC but I like to have flawless playback of media files in this room.<br>
- The Master Bedroom inherited the old Media PC which is a 5th gen i7 Intel NUC, SSD and 8gb RAM this rarely is used these &nbsp; days for media playback as the kids are still young once they learn to sleep in their own beds we should be able to use it &nbsp; &nbsp; &nbsp; &nbsp; again for that. It is used for music streaming however.<br>
- The Entertainment Kodi is a RPi model b+ with a HiFiBerry Amp hat more than enough for outdoor entertaining or watching &nbsp; the Rugby.</p>
<h4 align="left">Media Servers:</h4>
<p align="left">I use a pair of Netgear 2 bay NAS drives both contain 2 x 16Tb HDD and neither has redundancy(something I plan to sort in the very near future). These serve media to all devices around the house they are nothing special the read write times are pretty horrible but they get the job done and when they dont I will look at upgrading them.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Multi Room Audio</h3> 

| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/xsqeeze%20logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Hifi%20Berry%20Logo.png" width="150"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Yamaha%20Logo.jpg" width="150"/> |
| --- | --- | --- |

<p align="left">I already had a bunch of media playing capable devices with speakers so I opted to take advantage of these over a dedicated multi-room music option like Sonos. I am using my Kodi devices with Logitech Squeezebox to sync audio across rooms in the house although I normally only have one room playing at a time unless we are entertaining.</p>
<hr --- </hr>

| [Logitech Squeezebox Server](https://www.mysqueezebox.com/download) | [HiFiBerry Amp2](https://www.hifiberry.com/shop/boards/hifiberry-amp2/) | [Yamaha NS-AW392 Outdoor Speakers](https://www.exeltek.com.au/yamaha-ns-aw392-black-all-weather-speakers-waterproof-bass-drivers-powder-coated-aluminium-grilles-swivel-brackets-included?gclid=Cj0KCQjwlv_XBRDrARIsAH-iRJQO8TKkjAygha50BMU-bB2xcYoKnt1uE0p4zy7zUDuVlaQiMRiqVBYaAsWKEALw_wcB) | [Yamaha NS-IC600 In Ceiling Speakers](https://www.exeltek.com.au/yamaha-ns-ic600-in-ceiling-speaker-pair) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Logitech%20Sqeezebox%20Logo.png" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Amp2.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Yamaha%20In%20Ceiling.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Yamaha%20Outdoor.jpg" width="250"/> |

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

| [MQTT Alarm Control Panel](https://www.hackster.io/thanksmister/mqtt-alarm-control-panel-for-home-assistant-a206cc) | [Raspberry Pi 3+ Touch Screen Kit](https://core-electronics.com.au/raspberry-pi-3-touch-screen-kit.html) | [Design Spark Rpi Enclosure](https://au.rs-online.com/web/p/development-board-enclosures/9064665/) | [Raspberry Pi Camera Board](https://core-electronics.com.au/raspberry-pi-camera-board-v2-8-megapixels-38552.html) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Alarm%20Panel.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Rasp%20Pi%20Touch%20Screen%20Kit.png" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/RPi%20Touch%20Screen%20Enclosure.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Pi%20Camera.jpg" width="250"/> |

<h4 align="left">MQTT Manual Alarm:</h4>
<p align="left">I built the MQTT Alarm Panel as per the instructions the only things I did different was adapt a DesignSpark Touch Screen Enclosure to wall mount the Alarm Panel so it can be armed/disarmed as we come in the door. The downside to this design is you have to remove it from the wall if you ever need to access the ports (I haven’t had a need to do that yet). I also connected the RPi to a Bluetooth speaker so any sounds will be played back through it.</p>
<h4 align="left">Alarm Modes:</h4>
<p align="left">Arm Home<br>
This is a kind of perimeter mode where it sets the exterior motion sensors and all door/window sensors to trigger the alarm sequence after 60 secs on motion detection and state change respectively. This mode allows us to walk about the house and frees up the indoor motion sensors to be used to trigger lights after it has been set with triggering alarm. If alarm is triggered the panel will beep every 5 secs for the first 60 secs to let you know you need to enter a valid code or it will sound the alarm, fire off TTS messages, start recording from all cameras etc. etc.<br>
  
Arm Away<br>
This arms the perimeter as above but it also arms tells the indoor motions sensors they are on watchdog mode and any motion detection from them will set of the alarm sequence as above. I get notifications to my slack, email and tasker I don't have it going to our phones via sms in case we are ever in the house with the would be assassins (that’s right I have made plenty of enemies in my time).<br>

Panic Mode<br>
During normal operation the alarm panel excepts a valid 4-digit code one for my wife and one for myself (as I type this I just thought I could use this for presence :+1:need to add to to-do list). If, however, you are in the unlikely or in my case seen too many movies very likely to happen scenario where you are being held at let’s say machete point (gun control is a big deal in Australia). There is a separate panic mode 4-digit code which will let you validate the alarm off sequence on the screen however it will send a msg to alert security company of situation #machetewieldingassailantsneedhelp.<br>

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

| [Sonoff POW](http://sonoff.itead.cc/en/products/sonoff/sonoff-pow) | [12V Solenoid](https://core-electronics.com.au/brass-liquid-solenoid-valve-12v-1-2-npt.html) | [Pi Zero](https://core-electronics.com.au/raspberry-pi-zero-w-starter-kit.html) | [Mi Flora](https://www.banggood.com/Original-Xiaomi-4-in-1-Flower-Plant-Light-Temperature-Tester-Garden-Soil-Moisture-Nutrient-Monitor-p-1068369.html?cur_warehouse=AU) |
| --- | --- | --- | --- |
| <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Sonoff%20POW.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/12V%20Solednoid.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Pi%20Zero.jpg" width="250"/> | <img src="https://github.com/JamesMcCarthy79/Home-Assistant-Config/blob/master/HA%20Pics/Mi%20Flora%201.jpg" width="250"/> |

<h4 align="left">Irrigation:</h4>
<p align="left">I bought a 12V Solenoid Valve and 12V 5A power supply which feeds into a Sonoff POW (with outdoor enclosure), and then into the 12V Solenoid. This feeds into a single hose that runs around my side and back garden beds. It is scheduled to water of an evening in the winter unless moisture sensor is over 20% or rain is forecast for the following 8hr period. In the spring I transition to morning watering and in the summer, it gets really hot here so morning and evening watering.</p>
<h4 align="left">Plant Monitoring:</h4>
<p align="left">I bought a bunch of these Mi Flora Plant sensors for monitoring the indoor and plants in pots we have in our entertaining area, as it states they shouldn't be flooded with water. I had a heap left over so I pushed a few into the garden beds also, and they are surprisingly still going strong. I figured for $25 a pop if they don't last then I will get something more suitable, they are accurate enough to decide when not to water the beds I am not growing crops that need to have measurements down to root level. These connect back to a Raspberry Pi Zero W via Bluetooth which I installed the Bluetooth add on and they integrated to HA pretty easily. I then use the HA API to get the Soil Moisture readings displayed into my main HA. I only really monitor Soil Moisture and Salinity as well as battery, but the sensors are equipped with Light and Temperature sensor. I wish to add my own weather station into the mix atm I use the BOM for weather conditions.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">My Favourite Resources</h3> 

<p align="left">I used the below links for inspiration, configuration help and I recommend a visit to them if you haven't already.</p>

[CCOSTAN](https://github.com/CCOSTAN/Home-AssistantConfig) - There is a reason this guys Repo is the most starred out there, his Repo layout was an inspiration for me to start this one and you will see a lot of similarities in my layout as a result. Whilst I don't yet use Docker or Floorplan this is the first place I will coming back to once I move in that direction. His use of TTS is awesome and very creative and I took alot of my TTS from this. His whole setup is very impressive and if you haven't already head over to his repo give it a star and get inspired.

[stanvx](https://github.com/stanvx/Home-Assistant-Configuration) - Another I visit regularly is stanvx he uses alot of Xiaomi products and he has really good examples for those looking for automation ideas.

[notoriousbdg](https://github.com/notoriousbdg/hassio-addons) - As mentioned above notoriousbdg has a great repo with add-ons for Node-Red, HA Bridge & Gogs.

[BRUH Automation](https://www.youtube.com/channel/UCLecVrux63S6aYiErxdiy4w) - Great place for video tutorials on HA related guides.

[DrZzs](https://www.youtube.com/channel/UC7G4tLa4Kt6A9e3hJ-HO8ng) - For anyone wanting to use Sonoff switches plenty of useful guides.

[HA Podcast](https://hasspodcast.io/) - I didn't mention above but I have an automation to send me a tasker notification that there is a new HA release, so that the next time I am driving to work I can say "ok google" play the latest home asssitant podcast. Nice way to keep abreast of what changes are coming in the latest release and if there is anything I would like to take advantage of. 
<hr --- </hr>

<h3 align="left">My Favourite Projects</h3> 

<p align="left">I used the below links for intergration into my own HA or I plan to at some point in the future.</p>

[HA UI Themes](https://community.home-assistant.io/t/share-your-themes/22018/100)<br>
[Custom UI Tiles](https://community.home-assistant.io/t/share-your-themes/22018/100)<br>
[Sonoff-HA](https://community.home-assistant.io/t/sonoff-homeassistant-alternative-firmware-for-sonoff-switches-for-use-with-mqtt-ha/2332/308)<br>
[Spotify Playlist Player](https://community.home-assistant.io/t/spotify-playlist-player/22491/67)<br>
[MQTT Alarm Panel](https://community.home-assistant.io/t/mqtt-alarm-control-panel-for-raspberry-pi-and-android/26484)<br>
[Better Looking Device Tracker](https://community.home-assistant.io/t/better-looking-device-tracker/27281)<br>
[Alexa as a Media Player](https://community.home-assistant.io/t/echo-devices-alexa-as-media-player-testers-needed/58639)<br>
[Zoned Cleaning Xiaomi](https://community.home-assistant.io/t/howto-xiaomi-vacuum-zoned-cleaning/51293)<br>
<a>**More to come as I can remember them**<a name="bottom" href="https://github.com/JoeStratton/home-assistant-config/blob/master/README.md"><img align="right" border="0" src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/Back%20to%20the%20Top.png" width="45" ></a><br>
<hr --- </hr>
<hr --- </hr>
