### Setup

Before using this automation, replace the example entities with your own:

- `climate.thermostat` — your central HVAC thermostat
- `sensor.room_multi_sensor_temperature` — the temperature sensor for the room
- `cover.room_hvac_vent` — the smart vent for the room

The vent positions can also be adjusted for your installation.

| HVAC State | Room Condition | Vent Position |
| --- | --- | ---: |
| Cooling | Room above target | 100% |
| Cooling | Room at or below target | 0% |
| Heating | Room below target | 50% |
| Heating | Room at or above target | 0% |
| Idle | Any | 100% |
| Sensor unavailable | 3+ minutes | 100% |

### Why the Fail-Safe?

The automation intentionally defaults to an **open vent** when valid room-temperature data isn't available.

A disconnected, failed, or unavailable temperature sensor should not cause a smart vent to remain closed indefinitely.

This example is intended as a starting point. Adjust the temperature logic and vent positions to match your HVAC system, room layout, and airflow requirements.
