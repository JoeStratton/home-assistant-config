<!-- <p align="center">
  <img src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/xxxxx.png" width="250"/>
</p> -->
<h1 align="center">unJoe Smart Home Configuration</h1>
<h3 align="center">Home Assistant Configuration &amp; Documentation for my Smart House.</h3>
<p align="center">Be sure to :star: my repo!</p>
<p align="center">
<img src="http://hits.dwyl.io/JoeStratton/home-assistant-config.svg"/>
</p>  
<p>
  <img src="https://img.shields.io/github/stars/JoeStratton/home-assistant-config.svg?style=plasticr"/>
  <img src="https://img.shields.io/badge/HA--Version-0.118.0-brightgreen.svg"/>
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
<img src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/i7.png" width="95"/>
<img src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/Rasp%20Pi%20Logo.png" width="200"/> 
<img src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/docker.png" width="200"/> 
<p align="left">I am using a server and Docker for this, but I included the Raspberry Pi logo because that is all you need to get most of this up and running.</p>
<hr --- </hr>

<h3 align="left">Home Assistant Software</h3>

<h4 align="left">Home Assistant:</h4>
<p align="left">You have a few options to install home assistant. There is a standalone OS called Hass.IO as well as the application home assistant. Both do the same thing, hass.io does have a built in package manager and a few other things as well. This build uses a docker container and the core application, not hass.io</p>

<h4 align="left">MQTT Broker:</h4>

I use a MQTT server to create a communication bridge between my ring products and home assistant. This allows me to detect door status as well as maniuplate my alarm over MQTT as the original ring api does not support these from within hass.

<h4 align="left">Node-RED:</h4>

When I started experimenting with automations in Hass I noticed how limited it was. With recent versions they have improved the automation interface extensively and almost any user can figure this out on their own. I still decided to stick with node red which allows a more visiual represetnation of the flows and relies heavily on javascript/yaml/json knowledge.

<a href="https://github.com/JoeStratton/node-red-flows">My Node Red Repo<a>

<hr --- </hr>
<hr --- </hr>

<h3 align="left">unJoe Network</h3>
I have a full stack Ubiquiti Unifi network. This includes a USG Pro, 24 POE switch, 8 unifi cameras, Unifi Protect, Unifi Cloud Key Gen2
<hr --- </hr>

UBNT devices are configured by their Web UI and then managed by a USG Pro (overkill for 3 devices) they have been set and forget with only firmware upgrades performed if they address any security patches.</br> 

<h3 align="left">Voice Control & TTS</h3> 
I originally wanted Amazon Alexa's or Google Home's for their bluetooth tracking capability, but as time went on I realized that was not feasable. Instead, I have the Echo's communicating to a custom lamnda function that allows communication with ALL of my hass devices. I can call or maniuplate any services I need to this way. I will implement bluetooth tracking via ESP chips later on. I also use alexa media player to play notifications from these devices. It is a handy notification system, although it is not 2 way.
<hr --- </hr>
<hr --- </hr>

<h4 align="left">Smart Fan:</h4>

We bought a Modern Homes smart fan for outdoors when it is hot, mostly just to experiment with another api from within home assistant. The next steps will be moving away from mainstream api's and setting all fans up on HTTP relays of some sort.

<h4 align="left">Power Switches:</h4>
<p align="left">I have lost count of how many of these things I have around the place, I have some on light swtiches, some on floor fans, some on appliances. They work great and allow for energy monitoring if needed.
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Media Control</h3> 

I have a full Dolby theater setup, which uses a Nvidia Shield and Yamaha reciever. I use the shield in developer mode along with a docker container that allows communication via api. This allows me to control the shield without finding the remote everytime as well as automate a movie start. The Yamaha has its own api that controls the source/power/volume and finally the projector painfully uses telnet (I had no choice!)

<h3 align="left">Multi Room Audio</h3> 

The house is set up in 3 zones and there is 1 receiver for each floor of the house. Via the zone discovery feature of hass, we are able to control all zones and volume.
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Security</h3> 
I use a Ring security system along with some other modified sensors and automations (and 2 big dogs)

<hr --- </hr>

<h4 align="left">Cameras:</h4>
<p align="left">Exterior<br>
There are 8 cameras aroun the house including the exterior and first floor interior, all are Unifi G3 cameras powered by the unifi switch mentioned above.</p>
<hr --- </hr>
<hr --- </hr>

<h3 align="left">Garden and Irrigation</h3> 

<p align="left">Coming Soon.</p>
<hr --- </hr>

<h3 align="left">My Favourite Projects</h3> 

<p align="left">I used the below links for intergration into my own HA or I plan to at some point in the future.</p>

- [Alexa as a Media Player](https://community.home-assistant.io/t/echo-devices-alexa-as-media-player-testers-needed/58639)<br>
  
<a>**More to come as I can remember them**<a name="bottom" href="https://github.com/JoeStratton/home-assistant-config/blob/master/README.md"><img align="right" border="0" src="https://github.com/JoeStratton/home-assistant-config/blob/master/HA%20Pics/Back%20to%20the%20Top.png" width="45" ></a><br>
<hr --- </hr>
<hr --- </hr>
