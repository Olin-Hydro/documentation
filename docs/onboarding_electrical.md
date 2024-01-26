# Hydroponic System Onboarding Tutorial

Welcome to your onboarding! This document will guide you through the initial steps of setting up your hydroponic system. During the onboarding, you should be provided with the following items:

- 1x Adafruit ESP32 Feather Board
- 1x Breadboard
- 1x Sensor (various types)
- A bunch of cables
- A few LED bulbs

## Section 1: Overview of Electrical Parts and Sensors

### Peristaltic Water Pump

- **Function:** Delivers water, nutrients, or any liquid solution throughout the hydroponic system.
- **Operation:** Compresses and relaxes a tube to create a steady flow of liquid without contamination.
- **Use Case:** Controlled delivery of water and nutrients at scheduled intervals.

### Temperature Sensor

- **Function:** Monitors the temperature within the hydroponics system.
- **Operation:** Measures ambient temperature, maintaining optimal growth conditions.
- **Measurement Range:** 10 mV/°C scale factor, 500mV offset (0.5V @ 0°C).

### TDS Sensor (Analog)

- **Function:** Measures Total Dissolved Solids in water, indicating nutrient concentration.
- **Operation:** Monitors nutrient levels in water.
- **Measurement Range:** 0 ~ 1000ppm (±10% accuracy).

### Luminance Sensor (Analog)

- **Function:** Measures light intensity within the system.
- **Operation:** Regulates artificial lighting or assesses natural light levels.
- **Measurement Range:** 0 - 4095; lower values indicate brighter areas.

### pH Sensor (I2C)

- **Function:** Monitors pH level of the water.
- **Operation:** Ensures pH is within optimal range for nutrient absorption.
- **Measurement Range:** .001pH − 14.000pH.

### Humidity Sensor (I2C)

- **Function:** Measures humidity levels in the environment.
- **Operation:** Maintains ideal humidity for plant growth.
- **Notes:** Prevents excess moisture or dry conditions.

## Section 2: Adafruit ESP32 Feather Board

The Adafruit ESP32 Feather Board is a versatile and powerful microcontroller board, ideal for a variety of DIY projects, especially in hydroponics. It's the brain of your hydroponic system, seamlessly connecting and controlling various sensors and components.

### Understanding the Adafruit ESP32 Feather Board

Before diving into the connections, let's understand what makes the ESP32 Feather Board stand out:

- **Wi-Fi and Bluetooth Capabilities:** Allows for wireless communication and remote monitoring of your hydroponic system.
- **Rich Set of I/O Pins:** Ample digital and analog pins to connect a variety of sensors and actuators.
- **Low Power Consumption:** Ideal for battery-operated or energy-efficient hydroponic setups.
- **Compact Size:** Its small form factor makes it easy to integrate into your hydroponic system without taking up much space.

### Tutorial on Connecting Sensors to the Adafruit ESP32

#### Visual Guide:

![Adafruit ESP32 Feather Board Connection Diagram](https://cdn-learn.adafruit.com/assets/assets/000/111/179/large1024/wireless_Adafruit_HUZZAH32_ESP32_Feather_Pinout.png?1651089809)

#### Step-by-Step Guide:

1. **Identify the I/O Pins (input/output pin):** First, familiarize yourself with the I/O pins (the numbers on the board, as seen in the visual diagram as well) on the ESP32 board. Each sensor will connect to these pins for data communication. You don't really need to know what an I/O pin is, right now, just think of it as a communication channel. If you are interested, here is a [simple analogy](analogy_io.md).
2. **Start with your sensor (e.g., Temperature Sensor). Locate the VCC, GND, and DATA pins on the sensor.**
3. **Connect the VCC pin to the 3V3 (3.3V) output on the ESP32.**
4. **Connect the GND pin to one of the GND (Ground) pins on the ESP32.**
5. **Connect the DATA pin to a digital or analog input pin on the ESP32, depending on the sensor's output type.** All of your onboarding sensors should be analog. Search up the name and brand of your sensor, and the manufacturer should have a document on what pin the device should be connected to. Feel free to message the discord if you cannot find it, but we intentionally left it out so you can practice this process and use these skills on future sensors.
6. **Repeat for Additional Sensors:** Follow the same process for each sensor you have, ensuring that each sensor's DATA pin connects to a unique input pin on the ESP32.
7. **Powering the ESP32 Board:** You can power the ESP32 Feather Board via USB or through a battery if your setup is remote.
8. **Check Connections:** Once all sensors are connected, double-check each connection for correctness and security.

### Additional Resources:

- [Adafruit's Official Guide to ESP32 Feather Board](link-to-adafruit-guide)
- [Forum for Troubleshooting ESP32 Connections](link-to-forum)
- [Video Tutorial on Connecting Various Sensors to ESP32](link-to-video-tutorial)

By following these steps and utilizing the resources provided, you'll be able to successfully connect and configure the sensors with the Adafruit ESP32 Feather Board, laying a solid foundation for your hydroponic system's functionality.

- [Detailed connection tutorial](https://learn.adafruit.com/adafruit-huzzah32-esp32-feather/pinouts)

## Section 3: Coding for the Sensors

The sensors provided have analog outputs and are labeled with their names and brands.

1. To find the test code, start by searching online using the specific brand and model of your sensor. For example, DFRobot provides excellent documentation for their products, such as this [documentation for the Gravity Analog TDS Sensor & Meter for Arduino (SKU: SEN0244)](https://wiki.dfrobot.com/Gravity__Analog_TDS_Sensor___Meter_For_Arduino_SKU__SEN0244). You can typically find this information by searching for terms like "tds sensor dfrobot code." This search should lead you to the correct documentation, usually within the first few search results. Remember, the code provided in this example is specific to the DFRobot sensor and SHOULD NOT BE DIRECTLY COPIED for use with a different sensor. Always use the code intended for your specific sensor model.

2. Review the code and highlight any confusing parts. I recommend printing out the code for easier annotation. Bring your annotated version to our next PInT meeting, where we'll go over it together. If you're up for a challenge, try creating documentation for the code and explaining it to the group. This exercise is designed to help us practice understanding and documenting code that has poor documentation (or none at all T_T). It's completely fine if you don't understand everything yet. Just do your best, and we'll discuss it together at the meeting!

3. If you're stuck, feel free to ask for help on our Discord channel.

## Section 4: Putting It All Together

1. Download PlatformIO from [PlatformIO Documentation](link-to-platformio).
2. Set up your breadboard as described in Section 2.
3. Import the sensor codes onto the Adafruit ESP32 board using PlatformIO.
4. Troubleshoot any issues by revisiting previous sections or asking on Discord.
5. Remember, it's common to encounter challenges at this stage. Keep trying, and don't hesitate to ask for help!

## Section 5: Celebrate Your Success

Congratulations on reaching this significant milestone! Once you have successfully configured the sensor to transmit data to your terminal (or any other preferred method), you're ready to integrate it into the larger network. At this point, your sensor is prepared to be connected to the internet through our central communication system.

This achievement marks not just a technical accomplishment but also your contribution to setting up a crucial part of the hydroponics system. Your efforts bring us a step closer to creating a more efficient and responsive growing environment.

Take a moment to appreciate your hard work and persistence. Remember, every successful connection and configuration you complete is an integral part of the hydroponics journey. Well done!

_Good luck, and welcome to the exciting world of hydroponics!_
