# LEWIS-X: Low-cost Efficient Wireless Intelligent Sensor

This is the repo for LEWIS development on ESP32 platform using Feather form factor.

The aim of this project is to liberate and democratize the structural health monitoring.
This sensor is useful for:
- Citizen-based science
- K-12, undergrad, grad level education
- Introductory workshops to micro-computing for civil engineers

This work is in development. Will be updated from time to time.

## Roadmap
There is a informal map of what I want to achieve with this sensing system. 
The end goal is a solar-powered self-sustained GPS-synched sensors that have some IoT capability.

### Main challenges:
- Library for sd card (sdfat-lib) needs to be modified for esp32
- How to program gps and how to get time information is unknown to me
- PPS can be used to track accurate timing. How to use gps interrupt for pps needs to be researched.
- Working with two cores (sensor reading+writing on core 1 and gps read and synch at core 0) is the major challenge. ESP32 documents can aid
- ~Multiple i2c devices sharing the same address.~ MPU6050 can be assigned to 0x69 via AD0 while auxilary RTC has 0x68 reserved. 

### Further plans:
- GPS is a battery eater. For now, this will be a 'wired' prototype but a wireless sensor by heart. 
A better implementation would be base station only being gps and the other nodes synch with the base station.
- In the initial design, each sensor will be decentralized.
Sensors talking to each other and almost synchronized start at the same time is desirable.
- Self-aware sensing: Sensors letting base station if a sensor is down
- Reactive/responsive sensors (sensors that wake up each other)
- Android/iOS integration for remote amangement of sensors
- Better power management / deep sleep for esp32. Along the way, we need to get rid of usb-to-serial programmer which is there eating battery.
This almost always warrants for a new circuitry design
