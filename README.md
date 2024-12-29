# DHT11-Temperature-Humidity-Sensor-with-Arduino-Step-by-Step-Guide
# DHT11 Temperature & Humidity Sensor with Arduino

## Overview
This project demonstrates how to use the DHT11 temperature and humidity sensor with an Arduino. The sensor outputs temperature in both Celsius and Fahrenheit, along with the humidity percentage, which can be viewed in the Serial Monitor.

---

## Components
| **Component**        | **Quantity** | **Description**                                    |
|-----------------------|--------------|----------------------------------------------------|
| Arduino Uno           | 1            | Microcontroller board                              |
| DHT11 Sensor          | 1            | Measures temperature and humidity                 |
| Resistor (10kΩ)       | 1 (optional) | Pull-up resistor (if required by your sensor)      |
| Jumper Wires          | Several      | For making connections                            |

---

## Connections
| **DHT11 Pin**       | **Description**        | **Arduino Pin**     |
|----------------------|------------------------|----------------------|
| VCC                 | Power Supply (5V)      | 5V                  |
| GND                 | Ground                 | GND                 |
| Data                | Data Signal            | Digital Pin 2       |

---

## Arduino Code

Here’s the Arduino code to read data from the DHT11 sensor:

### Step 1: Install the DHT Library
1. Open Arduino IDE.
2. Go to **Sketch → Include Library → Manage Libraries...**.
3. Search for **DHT sensor library by Adafruit** and install it.

### Step 2: Upload the Code
```cpp
#include <DHT.h>

// Define DHT11 pin and type
#define DHTPIN 2     // Data pin connected to DHT11
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600); // Start serial communication
  Serial.println("DHT11 Sensor Initialization...");
  dht.begin(); // Initialize DHT sensor
}

void loop() {
  // Read humidity and temperature
  float humidity = dht.readHumidity();
  float temperatureC = dht.readTemperature();
  float temperatureF = dht.readTemperature(true);

  // Check if any readings failed
  if (isnan(humidity) || isnan(temperatureC) || isnan(temperatureF)) {
    Serial.println("Failed to read from DHT sensor!");
    return;
  }

  // Print values to Serial Monitor
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.print(" %\t");

  Serial.print("Temperature: ");
  Serial.print(temperatureC);
  Serial.print(" °C / ");
  Serial.print(temperatureF);
  Serial.println(" °F");

  // Wait 2 seconds between readings
  delay(2000);
}

How to Use DHT11 Temperature &amp; Humidity Sensor with Arduino | Step-by-Step Guide
To connect and code the DHT11 temperature and humidity sensor with an Arduino, follow the steps below:

Components Required:
Arduino board (e.g., Arduino Uno)
DHT11 sensor
10kΩ resistor (optional, if required by your sensor module)
Jumper wires
Circuit Connection:
VCC (DHT11) → 5V (Arduino)
GND (DHT11) → GND (Arduino)
Data (DHT11) → Digital Pin 2 (Arduino)
Note: Some DHT11 modules include a built-in pull-up resistor; if yours does not, place a 10kΩ resistor between the Data pin and VCC.

Arduino Code:
First, you’ll need to install the DHT sensor library if you haven’t done so already:

Open Arduino IDE.
Go to Sketch → Include Library → Manage Libraries...
Search for DHT sensor library by Adafruit and install it.
Explanation of Code:
DHTPIN is set to 2 to match the data pin connection on the DHT11.
The dht.readHumidity() and dht.readTemperature() functions fetch humidity and temperature data.
Data is printed to the Serial Monitor every 2 seconds.
Running the Code:
Connect your Arduino to your computer.
Open Serial Monitor (set baud rate to 9600) to see the humidity and temperature values.
This code should output the temperature in both Celsius and Fahrenheit, along with the humidity percentage, updating every two seconds.
