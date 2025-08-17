# Ultrasonic Radar (Arduino + HC-SR04 + Servo)

A simple “radar” that sweeps an ultrasonic sensor across 0–180° and streams angle–distance readings, useful for quick obstacle scanning and demos. Built on Arduino Uno with an HC-SR04 and a micro-servo.

---

## Features
- 0→180°→0° sweep with per-step distance sampling and serial output.  
- Compact wiring: HC-SR04 (Trig=9, Echo=10), Servo control on D3.  
- Fast scan with jitter control (small delay between steps; “out of range” handling). 

---

## Hardware

**Materials used**
- Arduino Uno (or whatever compatible)  
- HC-SR04 ultrasonic module  
- SG90 (or similar) micro servo  
- Breadboard + jumpers, 5V supply (recommended for servo)

**Wiring**
- **HC-SR04**: VCC→5V, GND→GND, **Trig→D9**, **Echo→D10**.   
- **Servo**: +5V→5V, GND→GND, **Signal→D3**. 

> Power tip: if the servo browns out USB, power the servo from a separate 5V source and **share GND** with Arduino.

---
