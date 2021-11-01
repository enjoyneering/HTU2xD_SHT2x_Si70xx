[![license-badge][]][license] ![version] [![stars][]][stargazers] ![hit-count] [![github-issues][]][issues]

# HTU2xD/SHT2x/Si70xx 

This is an Arduino library for _TE Connectivity_ HTU20D/HTU21D, _Sensirion_ SHT20/SHT21/SHT25, _Silicone Labs_ Si7006/Si7013/Si7020/Si7021 Digital Humidity & Temperature Sensor

- HTU2xD +1.5v..+3.6v, SHT2x +2.1v..+3.6v, Si70xx +1.9v..+3.6v
- HTU2xD 0.14uA..0.500uA, SHT2x 0.04uA..0.330uA, Si70xx 0.6uA..180uA
- integrated resistive heater HTU2xD/SHT2x 1.83mA, Si70xx 3.1mA..94.2mA **(4)**
- temperature range HTU2xD/SHT2x -40C..+125C, Si702x (G-grade) -40C..+80C
- humidity range 0%..100% **(1)**
- typical accuracy T +-0.3C at 14-bits, RH +-2% at 12-bits
- typical resolution T 0.01C at 14-bits, RH 0.04% at 12-bits
- maximum T measurement time Si70xx 11msec, HTU2xD 50ms, HTU2xD 85ms
- maximum RH measurement time Si70xx 12msec, HTU2xD 16ms, HTU2xD 25ms
- I2C bus speed 100KHz..400KHz
- response time 8..30sec **(2)**
- recommended to route VDD or GND between I2C lines to reduce crosstalk between SCL & SDA
- power supply pins must be decoupled with 100nF capacitor

Supports all sensors features:
- read humidity **(3)**
- read temperature **(3)**
- soft reset
- enable/disable heater **(4)**
- set heater level, for Si70xx only
- set resolution
- read low voltage alarm
- read ID
- read FW
- CRC calculation **(3)**

Tested on:
- Arduino AVR
- Arduino ESP8266
- Arduino ESP32
- Arduino STM32

**(1)** Prolonged exposure for 60 hours at humidity > 80% can lead to a temporary drift of the signal +3%. Sensor slowly returns to the calibrated state at normal operating conditions.<br>
**(2)** Measurement with high frequency leads to heating of the sensor, must be >= 0.5 seconds apart to keep self-heating below 0.1C<br>
**(3)** Library returns 255 if a communication error occurs or CRC doesn't match.<br>
**(4)** To remove dew from the sensor or to return the sensor to a calibrated state after prolonged exposure to humidity > 80%.

[license-badge]: https://img.shields.io/badge/License-GPLv3-blue.svg
[license]:       https://choosealicense.com/licenses/gpl-3.0/
[version]:       https://img.shields.io/badge/Version-1.1.0-green.svg
[stars]:         https://img.shields.io/github/stars/enjoyneering/HTU2xD_SHT2x_Si70xx.svg
[stargazers]:    https://github.com/enjoyneering/HTU2xD_SHT2x_Si70xx/stargazers
[hit-count]:     https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fenjoyneering%2FHTU2xD_SHT2x_Si70xx&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false
[github-issues]: https://img.shields.io/github/issues/enjoyneering/HTU2xD_SHT2x_Si70xx.svg
[issues]:        https://github.com/enjoyneering/HTU2xD_SHT2x_Si70xx/issues/
