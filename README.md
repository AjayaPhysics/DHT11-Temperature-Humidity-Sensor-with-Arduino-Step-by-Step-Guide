# DHT11-Temperature-Humidity-Sensor-with-Arduino-Step-by-Step-Guide
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
