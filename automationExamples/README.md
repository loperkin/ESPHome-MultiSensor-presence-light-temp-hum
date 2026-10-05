
# Home Assistant Automation Examples

These are example Home Assistant automations showing some of the ways I use the **ESPHome MultiSensor** for room-level automation.

The MultiSensor provides more than just environmental data. Its mmWave presence sensor can determine whether someone is actually still in a room, which makes it particularly useful for automations that shouldn't rely on traditional motion sensors alone.

These examples are intended as **starting points**.

Device IDs and entity IDs have intentionally been removed. You'll need to select your own MultiSensor and devices when creating the automation in Home Assistant.

---

# Auto Off Room

`autoOff.yaml`

One of the simplest — and probably most useful — automations for the MultiSensor is automatically turning things off when a room is empty.

Traditional PIR motion sensors can sometimes decide a room is empty simply because someone hasn't moved recently.

The mmWave presence sensor used by the MultiSensor is much better at detecting someone who is still sitting in the room.

That makes it ideal for an automation like this.

## How It Works

The basic logic is:

**Room becomes unoccupied**

↓

**Wait 2 minutes**

↓

**Check whether any controlled devices are still on**

↓

**Turn the room devices off**

The two-minute delay helps prevent lights or other devices from immediately shutting off when someone briefly leaves the sensor's detection area.

## Example Uses

This can be used to automatically turn off things such as:

- Room lights
- Lamps
- Fans
- Accent lighting
- Smart plugs
- Other switches controlled by Home Assistant

You can add as many or as few devices as make sense for the room.

---

## Setting It Up

The easiest way to configure this automation is through the **Home Assistant Automation GUI**.

### 1. Create a New Automation

In Home Assistant, create a new automation and give it a name such as:

`Auto Off - Living Room`

or

`Auto Off - Office`

### 2. Select the MultiSensor Presence Sensor

For the trigger, select the **occupancy or presence binary sensor** from your MultiSensor.

Configure the trigger for:

**Not Occupied**

and set:

**Duration: 2 minutes**

This means the automation will only continue if the room remains unoccupied continuously for two minutes.

If someone is detected again during that period, the timer effectively resets.

### 3. Add Your Conditions

The example automation uses an **OR condition** to check whether any of the devices being controlled are currently on.

For example:

- Ceiling light is on
- OR lamp is on
- OR accent lights are on

The automation only needs one of these conditions to be true before continuing.

This step isn't absolutely required, but it prevents Home Assistant from unnecessarily sending OFF commands when everything is already off.

### 4. Add the Actions

Add an action for each device you want turned off when the room becomes vacant.

For example:

- Turn off ceiling light
- Turn off lamp
- Turn off fan
- Turn off accent lighting

Once configured, Home Assistant will automatically shut those devices down after the MultiSensor determines the room has been empty for the specified amount of time.

---

# Example Logic

The included `autoOff.yaml` demonstrates the basic structure:

```text
MultiSensor reports NOT OCCUPIED
              |
              v
        Wait 2 minutes
              |
              v
     Is anything still ON?
              |
          YES | NO
              |  |
              v  └── Do nothing
      Turn devices OFF
```

---

## Adjusting the Delay

Two minutes is what I use in this example, but it isn't necessarily the right value for every room.

A hallway or bathroom might work well with a shorter delay.

A living room, office, bedroom, or other space where people may remain relatively still may benefit from a longer delay.

For example:

| Room | Possible Starting Delay |
| --- | ---: |
| Hallway | 1 minute |
| Bathroom | 2–5 minutes |
| Kitchen | 3–5 minutes |
| Office | 5–10 minutes |
| Living Room | 5–10 minutes |

These aren't rules. They're simply reasonable starting points.

Experiment with the timing until the automation feels natural for the way the room is actually used.

---

## Why Presence Instead of Motion?

This is one of the main reasons I started using mmWave sensors.

A traditional motion sensor essentially asks:

**Did something move?**

A presence sensor is trying to answer a much more useful question:

**Is someone still here?**

That distinction matters when you're sitting at a desk, watching television, reading, eating, or doing anything else that doesn't involve constantly moving around.

For an automatic OFF automation, knowing that the room is actually empty is much more useful than simply knowing that nobody moved recently.

---

## Included Example

The example YAML is available here:

`autoOff.yaml`

The `device_id` and `entity_id` values have intentionally been removed from the example because those values are specific to my Home Assistant installation.

I recommend using the Home Assistant Automation GUI to select your own:

- MultiSensor presence entity
- Lights
- Switches
- Fans
- Smart plugs
- Other devices

You can then use the included YAML as a reference for how the automation is structured.

---

## Take It Further

Once the basic Auto Off automation is working, the same presence sensor can become part of much more sophisticated room automation.

For example, you could combine:

**Presence + Ambient Light**

to turn lights on only when someone is present **and** the room is actually dark.

Or combine:

**Presence + Temperature + HVAC State**

to control smart HVAC vents based on whether a room is occupied and actually needs heating or cooling.

That's where having several room sensors together in one MultiSensor starts becoming particularly useful.

**Learn it. Build it. Put it into practice.**
