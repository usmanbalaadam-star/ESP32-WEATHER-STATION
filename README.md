# ESP32-WEATHER-STATION
IOT weather monitor using eps32, DHT11, open weather map and things speak  
# 🌡️ ESP32 Weather Station

An IoT project that reads local temperature & humidity using a DHT22 sensor, 
fetches online weather data from OpenWeatherMap, and visualizes everything 
on ThingSpeak cloud platform.

---


---

## 🛠️ Hardware

| Component | Purpose |
|-----------|---------|
| ESP32 DevKit | Main microcontroller & WiFi |
| DHT22 Sensor | Local temperature & humidity readings |
| Breadboard | Circuit prototyping |
| Jumper Wires | Connections |

### Wiring Diagram

| DHT11 Pin | ESP32 Pin |
|-----------|-----------|
| VCC | 3.3V |
| DATA | GPIO 4 |
| GND | GND |

*Add 10kΩ pull-up resistor between VCC and DATA if module doesn't have one.*

---

## 💻 Software

### Libraries Required
- `WiFi.h` — ESP32 WiFi connectivity
- `HTTPClient.h` — HTTP requests
- `ArduinoJson.h` — JSON parsing
- `DHT.h` — DHT22 sensor interface

### APIs Used
- **OpenWeatherMap** — Real-time weather data
- **ThingSpeak** — IoT cloud visualization

---

## 🚀 Features

- ✅ Reads local temperature & humidity (DHT22)
- ✅ Fetches online weather data via OpenWeatherMap API
- ✅ Compares local vs. online readings
- ✅ Auto-reconnects WiFi if disconnected
- ✅ Sends data to 4 ThingSpeak fields with retry logic
- ✅ Non-blocking timing using `millis()`

---

## 📊 ThingSpeak Fields

| Field | Data Source |
|-------|-------------|
| Field 1 | Local Temperature (°C) |
| Field 2 | Local Humidity (%) |
| Field 3 | Online Temperature (°C) |
| Field 4 | Online Humidity (%) |

---

## 🔧 Setup

1. **Install Arduino IDE** and ESP32 board support
2. **Install libraries**: `DHT sensor library` by Adafruit, `ArduinoJson` by Benoit Blanchon
3. **Create accounts**:
   - [ThingSpeak](https://thingspeak.com) — Get Write API Key
   - [OpenWeatherMap](https://openweathermap.org/api) — Get API Key
4. **Update credentials** in `esp32_weather.ino`:
   ```cpp
   const char* ssid = "YOUR_WIFI_NAME";
   const char* password = "YOUR_WIFI_PASSWORD";
   const char* openWeatherApiKey = "YOUR_OPENWEATHER_KEY";
   const char* thingSpeakApiKey = "YOUR_THINGSPEAK_WRITE_KEY";
