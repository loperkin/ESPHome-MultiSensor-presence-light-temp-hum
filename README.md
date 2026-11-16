# ESPHome MultiSensor — Presence, Light, Temperature & Humidity

A simple, all-in-one **ESPHome room sensor** designed to give Home Assistant a better understanding of what's actually happening in a space.

This project combines **human presence detection, ambient light, temperature, and humidity sensing** into one compact device built around the ESP32-C3 Super Mini.

It started as a simple idea: instead of giving Home Assistant several separate sensors scattered around a room, why not put the most useful room-level sensors together into one device?

That idea became the original **ESPHome MultiSensor** — and eventually led to several other projects and variations built around the same concept.

The project includes ESPHome firmware, wiring information, custom PCB files, automation examples, and now **3D-printable STL files** so you can build your own.

**[▶ Watch the Full YouTube Demo](https://youtu.be/qFK2t_15cas)**

---

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
- **3D-printable enclosure files (STL)**
- Fully customizable automations
- Open-source firmware and hardware designs

## Project Files

Everything needed to explore and reproduce the project is organized in this repository.

| Folder / Resource | Description |
|---|---|
| **Firmware** | ESPHome configuration for the MultiSensor |
| **Automation Examples** | Example Home Assistant automations |
| **3D Print** | STL files for printing the original MultiSensor enclosure |
| **Gerber Files** | PCB manufacturing files included in the repository |
| **Wiring Diagram** | Connections for the ESP32-C3 and sensors |
| **LICENSE.md** | Licensing information for the project |

### Quick Links

- [**Watch the YouTube Demo →**](https://youtu.be/qFK2t_15cas)
- [**Download the 3D Printing Files →**](./3D%20Print/)
- [**View the PCB Design on OSHWLab →**](https://oshwlab.com/rockdown/multi-sensor)

---

## Hardware

### Main Components

- [**ESP32-C3 Super Mini →**](https://geni.us/mZse)
- [**HLK-LD2410C mmWave Presence Sensor →**](https://geni.us/TfpZvN)
- [**BH1750 Ambient Light Sensor →**](https://geni.us/sySYq0f)
- [**DHT22 Temperature & Humidity Sensor →**](https://geni.us/jqC5I)
- [**Breadboards →**](https://geni.us/UiAciwT)

### A Note About Ceiling Fans

Some mmWave presence sensors can detect the movement of a ceiling fan and report the room as occupied.

I've used the **LD2410C** in rooms with ceiling fans and generally haven't had much trouble with it, although you may need to adjust the sensor configuration or account for the fan in your automations.

Other LD2410 variants may provide additional configuration options, including the ability to better control or exclude certain detection areas.

## Optional Supplies

Depending on how you build your sensor, you may also want:

- [Breadboard](https://geni.us/UiAciwT)
- [Wire](https://geni.us/BJ17)
- [Jumper Wire Kit](https://geni.us/qSjn)
- [Connectors](https://geni.us/77p986)
- [USB-C Cables](https://geni.us/0TGqa0E)
- [USB Power Adapters](https://geni.us/kpsq)

## Tools

A few basic electronics tools will make the project easier:

- [Soldering Station](https://geni.us/le9ZvwC)
- [Solder Flux](https://geni.us/ZWPR)
- [Wire Strippers](https://geni.us/RIeto)

> **Affiliate Disclosure:** Some of the links above are affiliate links. I may receive a small commission if you purchase through them at no additional cost to you. These are components and tools that I personally purchased or used while developing this project.

---

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

**Motion detected → Turn on light**

You can create logic closer to:

**Someone is present + The room is dark → Turn on light**

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

If you don't want to order and assemble the PCB yourself, I also have a couple of options available.

### PCB Only

For anyone who already has the components and just wants the custom board:

[**Purchase PCB →**](https://www.paypal.com/instantcommerce/checkout/GRGFRKEN94Z84)

### PCB + Components

For anyone who wants the PCB along with the components needed for the MultiSensor:

[**Purchase PCB and Components →**](https://www.paypal.com/instantcommerce/checkout/KM33ATDQLENEC)

---

# 3D Printing — Original MultiSensor Enclosure

Want to give your MultiSensor a cleaner, more finished appearance?

I've included the **3D-printable STL files for the original ESPHome MultiSensor** so you can print an enclosure yourself.

The enclosure gives you another option for housing the electronics rather than leaving the project exposed on a workbench.

Whether you're building your first MultiSensor or making several for different rooms, having printable parts makes it easier to create a more permanent installation.

## Download the STL Files

All available STL files for the original MultiSensor are located in the **3D Print** folder.

### [**Download the 3D Printing Files →**](./3D%20Print/)

You can download the files, open them in your preferred slicer, and prepare them for your printer.

These files are provided so you can print and modify the enclosure yourself without needing to purchase a finished case.

## Recommended Printing Considerations

If you're printing the enclosure, here are a few things to consider:

- **Material:** PLA or PETG are good starting options for typical indoor installations.
- **Layer Height:** A layer height around 0.20 mm is a reasonable starting point.
- **Infill:** Start with 15–20% infill and adjust based on the part.
- **Supports:** Check the model orientation in your slicer to determine whether supports are necessary.
- **Fitment:** Verify that your particular PCB and sensor modules fit before completing the assembly.
- **Sensor Openings:** Make sure any openings for the temperature, humidity, or light sensors remain unobstructed.
- **Ventilation:** Consider heat generated by the ESP32 and other components when evaluating temperature readings.

These are general starting recommendations, not verified settings for every included STL. Adjust them for your printer, material, and the actual geometry of the parts.

## Assembly and Installation

Before assembling your MultiSensor:

1. Print the required enclosure parts.
2. Remove any supports and clean up the printed pieces.
3. Test-fit the PCB and sensor modules.
4. Check that the USB connection and any required openings remain accessible.
5. Install the electronics and secure the enclosure using the mounting features provided by the design.
6. Power up the device and verify that all sensors report correctly in Home Assistant.

The enclosure is intended for the **original MultiSensor design**. Other versions, including the Decora MultiSensor, may require different printed parts.

## Customize It

One of the reasons I enjoy 3D printing is the ability to take an existing design and make it better.

Want a different mounting method? A different color? Need to adjust something to fit your installation?

Feel free to experiment.

The mechanical design files are provided under the project's hardware license, so you can build on the original design while following the license requirements.

If you print one or improve the enclosure, I'd love to see what you've created.

---

# Where This Project Went Next

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

Firmware updates, PCB revisions, automation examples, 3D-printable parts, and related versions of the MultiSensor may be added over time.

If you build one, modify the design, print an enclosure, or come up with an interesting automation using it, feel free to share what you've created.

## 📜 License

This project is open source, with licensing based on the type of material:

- **Software, ESPHome configurations, Home Assistant automations, and code:** MIT License
- **PCB designs, mechanical designs, and functional 3D-printable parts:** CERN-OHL-W-2.0
- **Documentation, photos, and Purpose in Practice branding:** Copyright © 2026 Lee Perkins unless otherwise noted

See [LICENSE.md](LICENSE.md) for complete licensing information.

You're welcome to learn from it, build it, modify it, and improve it in accordance with the applicable licenses.

---

## Purpose in Practice

This project is part of **Purpose in Practice**, where I explore home automation, electronics, 3D printing, practical DIY projects, and learning by doing.

The goal isn't just to show off finished projects. It's to share the process, including what worked, what didn't, and what I learned along the way.

If this project helped you, consider watching the video, sharing the repository, or giving it a star on GitHub.

**[▶ Watch the ESPHome MultiSensor Demo on YouTube](https://youtu.be/qFK2t_15cas)**

**Learn it. Build it. Put it into practice.**
