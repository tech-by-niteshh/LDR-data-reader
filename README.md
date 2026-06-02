# IoT Smart Streetlight System with ESP32 & ThingSpeak

An automated, cloud-connected IoT project built for the ESP32. This system monitors ambient light levels using a Light Dependent Resistor (LDR), automatically controls an LED (simulating a streetlight), and logs real-time brightness data to the cloud via the ThingSpeak platform.

# you can check the live project at [here](https://wokwi.com/projects/465169169113150465)
# the live cloud data is here [here](https://thingspeak.mathworks.com/channels/3395420/charts/1?bgcolor=%23ffffff&color=%23d62020&dynamic=true&results=60&type=line&update=15)

This code is configured out-of-the-box for simulation on the **Wokwi** virtual platform.

---

## 🚀 Features

* **Smart Automation**: Automatically toggles the LED based on a customizable brightness threshold.
* **Cloud Logging**: Uploads real-time sensory data to ThingSpeak every 15 seconds.
* **Virtual WiFi Support**: Configured to seamlessly connect to Wokwi's virtual WiFi access point.
* **Serial Diagnostics**: Outputs clear debugging information to the Serial Monitor.

---

## 🛠️ Hardware Requirements (or Wokwi Equivalents)

* **Microcontroller**: ESP32 Development Board
* **Sensors**: LDR (Photoresistor) Module
* **Actuators**: 5V/3.3V LED (with a $220\Omega$ current-limiting resistor)
* **Hookup**: Breadboard and jumper wires

### Pin Mapping

| Component | ESP32 Pin | Mode | Description |
| :--- | :--- | :--- | :--- |
| **LDR Analog Out** | `Pin 34` | `INPUT` | Reads ambient light levels (ADC value 0 to 4095) |
| **LED Anode (+)** | `Pin 13` | `OUTPUT` | Actuates the light source |

---

## 📡 Software & Cloud Setup

### 1. ThingSpeak Configuration
1. Sign up or log into [ThingSpeak](https://thingspeak.com/).
2. Create a **New Channel**.
3. Enable **Field 1** and name it something descriptive (e.g., `Ambient Light Level`).
4. Navigate to the **API Keys** tab and copy your **Channel ID** and **Write API Key**.

### 2. Code Customization
Open the code and replace the placeholder values with your specific ThingSpeak credentials:

```cpp
unsigned long myChannelNumber = YOUR_CHANNEL_ID;  // Replace with your actual Channel ID
const char* myApiKey = "YOUR_WRITE_API_KEY";     // Replace with your actual Write API Key
