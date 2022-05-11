# Prometheus ESP8266 HC-SR04 Exporter

[![GitHub release](https://img.shields.io/github/v/release/HON95/prometheus-esp8266-dht-exporter?label=Version)](https://github.com/HON95/prometheus-esp8266-dht-exporter/releases)

An IoT Prometheus exporter for measuring temperature using an ESP8266 (Arduino-compatible) with a Wi-Fi module and a DS18B20 (temperature) sensor.

## Metrics

| Metric | Description | Unit |
| - | - | - |
| `iot_info` | Metadata about the device. | |
| `iot_temperature_fahrenheit` | Air temperature. | `°F` |

## Requirements

### Hardware

- ESP8266-based board (or some other appropriate Arduino-based board).
    - Tested with "Adafruit Feather HUZZAH ESP8266" and "WEMOS D1 Mini".
- DS18B20 sensor.
    - Tested with a cheap DS18B20 from Amazon.

### Software

- [Arduino IDE](https://www.arduino.cc/en/Main/Software)
    - Download and install.
- [esp8266 library for Arduino](https://github.com/esp8266/Arduino#installing-with-boards-manager)
    - See the instructions on the page.
- [Library for Dallas/Maxim 1-Wire Chips](https://github.com/PaulStoffregen/OneWire)
    - Install using the Arduino library manager.
- [Arduino plug and go library for the Maxim (previously Dallas) DS18B20 (and similar) temperature ICs](https://github.com/milesburton/Arduino-Temperature-Control-Library)
    - Install using the Arduino library manager.
- [DS18B20 sensor library for ESPx](https://github.com/beegee-tokyo/DHTesp)
    - Install using the Arduino library manager.

## Building

### Hardware

Using the "Adafruit Feather HUZZAH ESP8266".

Wire the DS18B20 sensor power to the 3.3V and any GND on the ESP and wire the data output to e.g. pin 4 (aka D2).

### Software

Using the Arduino IDE.

1. Copy `config.default.h` to `config.h` and fill in the details.
1. Open `src/src.ino` in the Arduino IDE.
1. Set the correct settings for the board.
    - WEMOS D1 Mini uses board "WeMoS D1 R2 & mini".
    - Adafruit Feather HUZZAH ESP8266 uses "Adafruit Feather HUZZAH ESP8266".
1. Build and upload using the Arduino IDE.

## Version

See `src/version.h`.

It's set manually since no build tools (or CI) other than the Arduino IDE is used.

## License

GNU General Public License version 3 (GPLv3).

## References

- [ESP8266 DS18B20 Temperature Sensor with Arduino IDE (Single, Multiple, Web Server)](https://randomnerdtutorials.com/esp8266-ds18b20-temperature-sensor-web-server-with-arduino-ide/)
