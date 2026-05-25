# ESPHome-MultiSensor-presence-light-temp-hum

This is a simple all-in-one sensor platform designed to make spaces smarter. It reliably detects human presence while tracking real-time changes in light, temperature, and humidity—all in one compact device.

You can automate environments based on what's actually happening in a room. Turn off lights when nobody’s around, adjust climate control to match the current occupancy, or simply collect detailed environmental data for your next project. Whether you’re into home automation, energy savings, or just cool data, this has got you covered.

Features:
* Human presence detection for responsive automation
* Ambient light sensingTemperature monitoring
* Humidity tracking
* Simple integration the popular platforms ESPHome and Home Assistant

Supplies:
  * esp32-c3 supermini → [Amazon](https://amzn.to/4qy8IoZ)  bigger pack [Amazon](https://amzn.to/4jgqCdq)
  * breadboards → [Amazon](https://amzn.to/3PnCKip)
  * HLK-LD2410C Presence Sensors → [Amazon](https://amzn.to/4slox4a)  FYI some precense sensors do not like ceiling fans. I have these in rooms with ceiling fans and they think that the room is occupied when the fan runs. I just take steps to avoid that. The b model can supposidly create an ignore zone but I do not have much issue with ceiling fans and this c model.
  * BH1750 Light Sensors → [Amazon](https://amzn.to/497iB5O)
  * DHT22 Temperature and Humidity Sensors → [Amazon](https://amzn.to/3YemiSc)

I do get a small commision for these links but I personaly did purchase these for this project.

OPTIONALS:

Any wiring accessories you may want like a [breadboard](https://amzn.to/3PnCKip), [wire](https://amzn.to/4p9BBXd), [jumper wire kit](https://amzn.to/4f6YU2G) , [connectors](https://amzn.to/4peqV9V), [usb-c cords](https://amzn.to/4b9XnGZ) and [powerbricks](https://amzn.to/4ph2mJs).

Tools:

[Soldering station](https://amzn.to/3YbfWDh), [solder flux](https://amzn.to/4sbSXpr), [wire strippers](https://amzn.to/4q7xsnW)

Wiring:

<img width="400" height="347" alt="Screenshot 2025-12-27 at 9 47 16 AM" src="https://github.com/user-attachments/assets/4706243c-440f-4de9-94c6-c80cd44e564b" />

Programing:

The esphome builder code is in the firmware folder. Please have a look and read. You must copy the components of the code you want into your own esphome builder device.

If you have a new C3 supermini it probably defaults to sleep and awake, over and over. You need to press and hold boot, then press reset and release, then release boot buttons. This method will allow the C3 supermini to program via usb.

Check out the Automation Examples.

Dashboard:

Example of fun badges for a room <img width="413" height="57" alt="Screenshot 2025-12-27 at 10 17 55 AM" src="https://github.com/user-attachments/assets/5e5d9b20-d28b-472b-a55c-b2dee6bfa59b" />

PCB: This is a PCB for this sensor. If you do not feel like building this on breadboard, purchase the PCB or have it made with the files.

<img width="500" height="250" alt="Screenshot 2025-12-31 at 12 07 59 PM" src="https://github.com/user-attachments/assets/16a1debe-daa2-4db9-a210-6be6bd7deb20" />

[Purchase PCB](https://www.paypal.com/instantcommerce/checkout/GRGFRKEN94Z84)

[Purchase PCB and all components](https://www.paypal.com/instantcommerce/checkout/KM33ATDQLENEC)

Or the Gerber files are attached so you can have the PCB built yourself. Design also available at [oshwlab](https://oshwlab.com/rockdown/multi-sensor)
