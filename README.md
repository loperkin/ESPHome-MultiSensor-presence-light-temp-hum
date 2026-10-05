# ESPHome MultiSensor — Presence, Light, Temperature & Humidity

A simple, all-in-one **ESPHome room sensor** designed to give Home Assistant a better understanding of what's actually happening in a space.

This project combines **human presence detection, ambient light, temperature, and humidity sensing** into one compact device built around the ESP32-C3 Super Mini.

It started as a simple idea: instead of giving Home Assistant several separate sensors scattered around a room, why not put the most useful room-level sensors together into one device?

That idea became the original **ESPHome MultiSensor** — and eventually led to several other projects and variations built around the same concept.

## What It Does

The MultiSensor gives Home Assistant four useful pieces of information about a room:

- **Is someone actually in the room?**
- **How bright is it?**
- **What's the temperature?**
- **What's the humidity?**

That information can then be used together to create much smarter automations.

For example:

- Turn lights on when someone enters a dark room
- Keep lights on while someone is sitting still
- Turn lights off when the room is actually empty
- Adjust HVAC based on room occupancy and temperature
- Track temperature and humidity throughout the house
- Create room-level occupancy indicators
- Collect environmental data for dashboards and automations

Whether you're interested in home automation, energy savings, environmental monitoring, or just collecting some cool data, this little sensor can do quite a bit.

## Features

- Human presence detection using mmWave radar
- Ambient light sensing
- Temperature monitoring
- Humidity monitoring
- ESP32-C3 based
- ESPHome firmware
- Native Home Assistant integration
- Breadboard-friendly design
- Optional custom PCB
- Fully customizable automations

## Hardware

### Main Components

- **ESP32-C3 Super Mini** → [Amazon](https://amzn.to/46SiDOh)  
  Larger pack → [Amazon](https://amzn.to/4jtJqYC)

- **HLK-LD2410C mmWave Presence Sensor** → [Amazon](https://amzn.to/4z05qyP)

- **BH1750 Ambient Light Sensor** → [Amazon](https://amzn.to/4e47EFg)

- **DHT22 Temperature & Humidity Sensor** → [Amazon](https://amzn.to/4ys3nUs)

- **Breadboards** → [Amazon](https://amzn.to/3TvAQ0U)

### A Note About Ceiling Fans

Some mmWave presence sensors can detect the movement of a ceiling fan and report the room as occupied.

I've used the **LD2410C** in rooms with ceiling fans and generally haven't had much trouble with it, although you may need to adjust the sensor configuration or account for the fan in your automations.

Other LD2410 variants may provide additional configuration options, including the ability to better control or exclude certain detection areas.

## Optional Supplies

Depending on how you build your sensor, you may also want:

- [Breadboard](https://amzn.to/3TvAQ0U)
- [Wire](https://amzn.to/4AUwiCm)
- [Jumper Wire Kit](https://amzn.to/4ypj52L)
- [Connectors](https://amzn.to/4rFU4hc)
- [USB-C Cables](https://amzn.to/3VaIoXF)
- [USB Power Adapters](https://amzn.to/4hkBdoj)

## Tools

A few basic electronics tools will make the project easier:

- [Soldering Station](https://amzn.to/4jf3w9d)
- [Solder Flux](https://amzn.to/3VYDqgL)
- [Wire Strippers](https://amzn.to/4jf3zBV)

> **Affiliate Disclosure:** Some of the Amazon links above are affiliate links. I may receive a small commission if you purchase through them at no additional cost to you. These are components and tools that I personally purchased or used while developing this project.

## Wiring

The original version of the MultiSensor was designed so it could be built using readily available development boards and a breadboard.

<p align="center">
  <img width="500" alt="ESPHome MultiSensor Wiring Diagram" src="https://github.com/user-attachments/assets/4706243c-440f-4de9-94c6-c80cd44e564b" />
</p>

This is still a great way to build the project if you're learning, experimenting, or simply don't need the custom PCB.

## ESPHome Firmware

The ESPHome configuration for this project is located in the **Firmware** folder.

Take some time to read through the configuration before using it. You'll need to copy or modify the appropriate components for your own ESPHome device and Home Assistant installation.

### Programming the ESP32-C3 Super Mini

Some new ESP32-C3 Super Mini boards may repeatedly enter a sleep/reset cycle and can be difficult to flash initially.

If the board won't enter programming mode:

1. Press and hold the **BOOT** button.
2. While continuing to hold BOOT, press and release **RESET**.
3. Release the **BOOT** button.
4. Try flashing the ESP32-C3 again over USB.

Once the initial firmware has been installed, ESPHome can normally handle subsequent updates.

## Automation Examples

Check out the **Automation Examples** included with the project for ideas on how to use the sensor data inside Home Assistant.

The real advantage of combining these sensors becomes apparent when you start using the values together.

For example, instead of simply saying:

**Motion detected → turn on light**

you can create logic closer to:

**Someone is present + the room is dark → turn on light**

Then keep the light on until the room is actually unoccupied.

That's where presence detection becomes considerably more useful than a traditional motion sensor.

## Home Assistant Dashboard

Here's an example of some simple room-status badges using the MultiSensor data:

<p align="center">
  <img width="500" alt="Home Assistant MultiSensor Room Badges" src="https://github.com/user-attachments/assets/5e5d9b20-d28b-472b-a55c-b2dee6bfa59b" />
</p>

---

# Custom PCB

The original MultiSensor can be built on a breadboard, but after building several of them I wanted something cleaner and easier to reproduce.

So I designed a custom PCB specifically for the project.

The PCB brings the ESP32-C3 and sensor connections together on a dedicated board, reducing the amount of loose wiring and making it much easier to build additional MultiSensors.

<p align="center">
  <img width="500" alt="ESPHome MultiSensor Custom PCB" src="https://github.com/user-attachments/assets/16a1debe-daa2-4db9-a210-6be6bd7deb20" />
</p>

## Build It Yourself

The **Gerber files are included in this repository**, so you're welcome to have the PCB manufactured yourself.

The PCB design is also available on [OSHWHub / OSHWLab](https://oshwlab.com/rockdown/multi-sensor).

You do **not** need to purchase a PCB from me to build this project. The hardware design, firmware, and PCB files are available so you can build and modify your own.

## Ready-Made PCB Options

If you don't want to order and assemble the PCB yourself, I also have a couple of options available:

### PCB Only

For anyone who already has the components and just wants the custom board:

[Purchase PCB](https://www.paypal.com/instantcommerce/checkout/GRGFRKEN94Z84)

### PCB + Components

For anyone who wants the PCB along with the components needed for the MultiSensor:

[Purchase PCB and Components](https://www.paypal.com/instantcommerce/checkout/KM33ATDQLENEC)

---

## Where This Project Went Next

This was the **original MultiSensor** and the starting point for several of my later ESPHome projects.

Once I started using these around the house, the next question became:

**How can I make this smaller, cleaner, and easier to permanently install?**

That eventually led to versions such as the **Decora MultiSensor**, custom PCBs, 3D-printed enclosures, and other room-level sensor experiments.

But this original version remains one of the easiest ways to build the project, understand how everything works, and modify it for your own needs.

That's really the point.

Build it. Experiment with it. Change it. Make it useful for your own space.

---

## Project Status

This project continues to evolve as I experiment with ESPHome, Home Assistant, presence detection, and room-level automation.

Firmware updates, PCB revisions, automation examples, and related versions of the MultiSensor may be added over time.

If you build one, modify the design, or come up with an interesting automation using it, feel free to share what you've created.

**Learn it. Build it. Put it into practice.**
