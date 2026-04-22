# 🌡️ Temperature and Humidity Monitoring using Arduino

## 📌 Project Overview
This project measures temperature and humidity using a DHT11 sensor with Arduino.  
It provides real-time environmental data through the Serial Monito

## 🧰 Components Required
- Arduino Uno
- DHT11 Sensor
- Jumper Wires
- Breadboard

## ⚙️ Working Principle
The DHT11 sensor reads temperature and humidity from the environment and sends data to the Arduino.  
Arduino processes this data and displays it using serial communication.


## 💻 Arduino Code
```cpp
#include <DHT.h>

#define DHTPIN 6
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  float h = dht.readHumidity();
  float t = dht.readTemperature();

  if (isnan(h) || isnan(t)) {
    Serial.println("Sensor error!");
    return;
  }

  Serial.print("Humidity: ");
  Serial.print(h);
  Serial.println(" %");

  Serial.print("Temperature: ");
  Serial.print(t);
  Serial.println(" °C");

  Serial.println("------------------");

  delay(2000);
}
🔌 Connections
VCC → 5V
GND → GND
DATA → Pin 6
🧪 Simulation
This project was tested using the Wokwi online simulator due to the unavailability of physical hardware.
