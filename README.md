#  Enhanced ESP8266 Color Weather Station w/ Touchscreen -- (Version v17, Open Weather Map) (based on original by Daniel Eichorn (squix78) modified for DHT22)

Original desctiption and instrukciton see here: https://github.com/fowlerk/ESP8266-Color-Weather-Station-v17

Changes:
 mod for DHTesp.h and DHT22, if you want to use DHT11 you have to change the line 
 dht.setup(DHTPIN, DHTesp::DHT22); and replace DHT22 by DHT11
 had to change some wiring, LED=D0, CS=D8 and DHT=D1, details see below
 added WiFiManager.h v01.14 zu src, since its the last one which is working with this code

## Wiring


| ILI9341   | NodeMCU | WeMos D1 Mini | 
| --------- |:---------:|:---------------:|
| T_IRQ     | D4    | D4  | 
| T_DO      | D6    | D6  | 
| T_DIN     | D7    | D7  | 
| T_CS      | D3    | D3  | 
| T_CLK     | D5    | D5  | 
| SDO/MISO  | D6    | D6  | 
| LED       | D0    | D0  | since LED doesnt need interrupt, default was D8
| SCK       | D5    | D5  | 
| SDI/MOSI  | D7    | D7  |
| DC/RS     | D2    | D2  |
| RESET     | RST   | RST | 
| CS        | D8    | D8  | needed D1 for DHT, since DHT and D8 crashed ESP, default was D1
| GND       | GND   | GND | 
| VCC       | 3V3   | 3V3 | 
| DHTdata   | D1    | D1  |
| DHTV+     | 3V3   | 3V3 | 
| DHTGND    | GND   | GND | 

**Note that I have not tested the NodeMCU 

##  Contributed Libraries / Core / IDE (and links)


Library / Core Referenced | Version | Description | Link
------------------ | ------- | ----------- | ----
**Arduino IDE** | 1.8.10 | Arduino IDE | <https://www.arduino.cc/en/Main/Software>
**ESP8266 core** | 2.5.2 | ESP8266 board definitions | <https://arduino-esp8266.readthedocs.io/en/2.5.2/installing.html>
**<FS.h>** | 2.5.2 | Part of ESP8266 core, SPIFFS filesystem support | <https://arduino-esp8266.readthedocs.io/en/2.5.2/installing.html>
**<Adafruit_GFX.h>** | 1.3.4 | Adafruit's core graphics library | <https://github.com/adafruit/Adafruit-GFX-Library>
**<Adafruit_ILI9341.h>** | 1.2.0 | Adafruit's ILI9341 LCD hardware-specific library | <https://github.com/adafruit/Adafruit_ILI9341>
**<SPI.h>** | 2.5.2 | Part of ESP8266 core, used for DHT temperature readings if used | <https://arduino-esp8266.readthedocs.io/en/2.5.2/installing.html>
**<math.h>** | 1.6.23 | Part of Arduino core, advanced math functions used for calculating wind-chill/heat-index
**<XPT2046_Touchscreen.h>** | 1.2.0 | XPT2046 library for touch-screen controller by Paul Stoffregen | <https://github.com/PaulStoffregen/XPT2046_Touchscreen>
**<WiFiManager.h>** | 0.14.0 | WiFi Manager library by Tzapu | <https://github.com/tzapu/WiFiManager> added to source
**<ArduinoJson.h>** | 5.13.4 | JSON library by Bblanchon | <https://github.com/bblanchon/ArduinoJson>
**<JsonListener.h>** | 1.0.5 | JSON streaming parser by Squix78 | <https://github.com/squix78/json-streaming-parser>
**<OpenWeatherMapCurrent.h>** | 1.6.6 | ESP8266 Weather Station client library by Squix78 - current conditions | <https://github.com/squix78/esp8266-weather-station>
**<OpenWeatherMapForecast.h>** | 1.6.6 | ESP8266 Weather Station client library by Squix78 - 5-day forecast | <https://github.com/squix78/esp8266-weather-station>
**<Astronomy.h>** | 1.6.6 | ESP8266 Weather Station Astronomy client library by Squix78 - sunrise/set, moon illumination, age, phase calcuations | <https://github.com/squix78/esp8266-weather-station>
**<SunMoonCalc.h>** | 1.6.6 | ESP8266 Weather Station sun/moon calculations (not currently used - maybe for future moonrise/set calcs?) | <https://github.com/squix78/esp8266-weather-station>
**<WundergroundClient.h>** | | (*** No longer used ***) | <https://github.com/squix78/esp8266-weather-station>
**<simpleDSTadjust.h>**	| 1.2.0 | Simple daylight-savings time adjustment by Neptune | <https://github.com/neptune2/simpleDSTadjust>
**"TimeZone.h"** | 1.2.2 | Time zone conversion library by JChristensen | <https://github.com/JChristensen/Timezone>
**"DHTesp.h"** | 1.17.0 | Bernd Giesecke's DHT sensor library for ESP | <https://github.com/beegee-tokyo/DHTesp>
**<Adafruit_Sensor.h>** | 1.0.2 | Adafruit's Unified Sensor library | <https://github.com/adafruit/Adafruit_Sensor>

