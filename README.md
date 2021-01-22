# Raspberry-Touch
Raspberry Touchscreen , Node Red Dashboard
This is only for reference , please dont expect the flows files to work without modifying them as they are made specifically for my setup

First of all Load up a raspberry with a fresh copy of rasbian lite and set it up as a kiosk using this as a guide
https://desertbot.io/blog/raspberry-pi-touchscreen-kiosk-setup

After you have confirmed this kiosk works , proceed to install Node Red on the same Raspberry PI
When Node red is installed and working , install the Dashboard addon 
https://flows.nodered.org/node/node-red-dashboard

You then need to point the kiosk browser to 127.0.0.1:1880/ui
this points your kiosk to the local dashboard , refer to kiosk setup guide

To enable your touchscreen to replicate your remotes you will need to make/get and smart IR Transmitter
I made one using a Wemos DI mini esp8266 loaded with the irserver sketch  ,you will also need an IR reciever module and an ir led that is driven via a 2n7000 transistor .(Jaycar and Altronics in Aus have all these parts available although ebay is cheaper)

This sketch will send ir codes to the ir transmitter LED, and also decode the incoming ir from your remote
The method I used  to communicate between node red and irserver is MQTT messages , If you choose this method you will need a mqtt broker (you could install this on the same pi )and point the ir server and node red to the mqtt broker by changing the sketch to suit 

My Audio System (ROTEL 1500 series) which have the capability of control via direct ethernet connection , This is achieved by using RS232 commands via telnet and reading the responses , this enables source infomation and volume level.

The Audio control page changes the button functions based on the source provided from the Rotel

My power switches are rf power points 
I used this https://www.jaycar.com.au/iot-wireless-switch as a basis and converted it to run on MQTT messages

This is a guide only.







