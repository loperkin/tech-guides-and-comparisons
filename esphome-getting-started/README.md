# 🔧 ESPHome Beginner Tutorials — ESP32-C3 SuperMini and Home Assistant

> **Website companion:** [PIP Builds ESPHome MultiSensor guide](https://pipbuilds.com/projects/multi-sensor/) · **Maintained project files:** [Original ESPHome MultiSensor repository](https://github.com/loperkin/ESPHome-MultiSensor-presence-light-temp-hum)

**Learn it. Build it. Put it into practice.**

This is a beginner-friendly learning path based on the original ESPHome MultiSensor project. It combines an ESP32-C3 SuperMini, an LD2410C mmWave presence sensor, a BH1750 ambient light sensor, and a DHT22 temperature/humidity sensor. It explains the order of operations and where to find the *actual tested project configuration* without inventing wiring pins or firmware values.

## Start here: the video learning path

| Stage | Video | What it covers |
|---|---|---|
| 1. See the finished device | [4-in-1 Home Assistant Sensor (50 sec)](https://www.youtube.com/watch?v=S8LQ3B025v0) | Presence, light, temperature and humidity |
| 2. Prepare the controller | [ESP32-C3 SuperMini Initial Setup (49 sec)](https://www.youtube.com/watch?v=-CHwtgzvuPs) | Getting ready to program the board |
| 3. Prepare connections | [Soldering ESP32-C3 headers](https://www.youtube.com/watch?v=cIKWinRn8Eo) | Header soldering |
| 4. Flash ESPHome | [Flash and Program the MultiSensor](https://www.youtube.com/watch?v=m8oFuj_5kZI) | ESPHome programming walkthrough |
| 5. Put it to work | [Presence-based lighting automation](https://www.youtube.com/watch?v=vPH7IRKjb40) | Using occupancy and light data |
| 6. Explore the upgrade | [Decora V2 update (26 sec)](https://www.youtube.com/watch?v=O4q-jh0e4ZQ) | Cleaner wall-mounted version |

[Watch the complete MultiSensor build](https://www.youtube.com/watch?v=qFK2t_15cas) for the longer project narrative.

## 1. Gather the hardware and tools

- ESP32-C3 SuperMini development board
- LD2410C mmWave presence module
- BH1750 light sensor module
- DHT22 temperature/humidity sensor
- Suitable USB data cable, breadboard/jumpers or soldered connections, and a safe low-voltage power source
- A computer with access to ESPHome

See the [original project's hardware and tools lists](https://github.com/loperkin/ESPHome-MultiSensor-presence-light-temp-hum#hardware) for links and the exact project scope. This guide intentionally provides **no product prices**; choose equipment that meets your needs and budget.

## 2. Start with the ESP32-C3 alone

1. Confirm your USB cable transfers data; some cables provide power only.
2. Connect the board to your computer before wiring external sensors.
3. Open the current [ESPHome getting started documentation](https://esphome.io/guides/getting_started_command_line/) or your preferred supported ESPHome workflow.
4. Use the **ESP32-C3 configuration from the project's Firmware folder**; don't select a generic ESP32 board configuration without checking the target.
5. Flash the firmware, then confirm the device boots and can connect to your intended network.

### If the board won't flash

The original MultiSensor documentation notes that some ESP32-C3 SuperMini boards may repeatedly reset or have trouble entering programming mode. Its documented recovery sequence is:

1. Hold **BOOT**.
2. While holding BOOT, press and release **RESET**.
3. Release BOOT.
4. Retry flashing over USB.

If the problem continues, verify the cable, USB connection, serial port selection and power before changing the wiring.

## 3. Wire the sensors using the project diagram

**Do not guess GPIO pins from a similar-looking ESP32 board.** Refer to the [original wiring diagram and Firmware folder](https://github.com/loperkin/ESPHome-MultiSensor-presence-light-temp-hum). Confirm the voltage and pin assignments for the exact modules in hand. Disconnect power while changing connections.

- **LD2410C:** mmWave presence sensing
- **BH1750:** ambient light level
- **DHT22:** temperature and humidity

Build and verify one connection at a time. The project's original breadboard design is suitable for learning; the custom PCB is an optional later step.

## 4. Verify each sensor in Home Assistant

1. Confirm the ESPHome device appears and stays connected.
2. Check presence state while entering, remaining still, and leaving the room.
3. Confirm light readings change when the room gets brighter or darker.
4. Compare temperature and humidity readings with a reference if available; note that enclosure heat and placement can affect readings.
5. Test with fans running. The original project notes that mmWave can sometimes detect moving fans as occupancy; tune and place the sensor based on actual room behavior.

Do not build important automations on a sensor until its behavior is reliable.

## 5. Build a simple presence-and-light automation

**Goal:** turn on a room light when someone is present *and* the room is dark, then turn it off after the room is actually vacant.

- Use the MultiSensor's presence entity as the occupancy signal.
- Use its ambient light reading as a condition for switching on.
- Add an appropriate vacancy delay to avoid flickering or premature shutoff.
- Decide how the automation should behave if the sensor goes unavailable.
- Test while someone is sitting still, and test after everyone leaves.

Use the project's maintained [automation examples](https://github.com/loperkin/ESPHome-MultiSensor-presence-light-temp-hum) as the source for entity-specific configurations. Avoid copying example entity IDs without adapting them.

## 6. Enclosures, PCBs and upgrades

The original repository includes **3D Print** STL files, PCB files, and firmware. Test-fit the components and leave required sensor openings unobstructed. The [Decora MultiSensor](https://github.com/loperkin/ESPHome-MultiSensor-Decora) is a different version with a different form factor; don't assume its enclosure or pin mapping is interchangeable.

## Troubleshooting checklist

| Symptom | Check first |
|---|---|
| Board powers up but cannot be flashed | USB data cable, selected port, BOOT/RESET sequence |
| ESPHome device disconnects | Power stability, Wi-Fi signal, logs and firmware configuration |
| Presence stays detected in an empty room | Moving fans, placement, mmWave configuration and reflections |
| Light value does not change | BH1750 connections and configuration |
| Temperature seems too warm | Enclosure heat, airflow, sensor placement and comparison with a reference |
| Automation fails | Correct entity IDs, sensor availability, conditions and Home Assistant traces |

## Sources, project status and disclosure

The [original MultiSensor repository](https://github.com/loperkin/ESPHome-MultiSensor-presence-light-temp-hum) is authoritative for current wiring, firmware, licensing and hardware revisions. This tutorial summarizes its documented process and links to existing YouTube tutorials; it does not claim independent testing of new configurations.

Some links in the original project may be affiliate links. If you purchase through those links, the creator may receive a commission at no additional cost to you. Product availability and specifications may change.
