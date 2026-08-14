# IoT-Based Three Phase Transmission Line Fault Detection and Analysis

![Arduino](https://img.shields.io/badge/Arduino-NodeMCU%20ESP8266-blue)
![IoT](https://img.shields.io/badge/IoT-ESP8266%20WiFi-orange)
![Published](https://img.shields.io/badge/Published-IJSRP%20July%202023-green)

**Authors:** Shazia Afroze, Md Asifuzzaman, Md. Istiak Hossain Paran
**Institution:** Department of Electrical & Electronic Engineering, Stamford University Bangladesh
**Supervisor:** Shazia Afroze, Assistant Professor, SUB
**Published:** International Journal of Scientific and Research Publications (IJSRP), Volume 13, Issue 7, July 2023
**DOI:** http://dx.doi.org/10.29322/IJSRP.13.07.2023.p13921

---

## Overview

This project implements a smart IoT-based fault

![banner](assets/banner-iot-fault-detection.png)
 detection system for three-phase
transmission lines. The system automatically detects, classifies, and locates faults
in real time and transmits fault information to a control room via Wi-Fi, drastically
reducing response time for technical crews.

The system detects three fault types:
- Line-to-ground faults
- Short circuit faults (phase-to-phase)
- Multi-line faults

---

## System Architecture

- 3-phase transmission line model with step-down transformer (220V to 3.3V)
- NodeMCU ESP8266 microcontroller (32-bit Tensilica RISC CPU, 80MHz, 4MB Flash)
- Relay-based multiplexing — 3 relays handle 3 phase inputs into NodeMCU's single analog pin
- Voltage regulators (diode-based) generate three reference voltages: 1.2V, 1.9V, 2.6V
- Google Firebase cloud server for real-time data transmission
- Custom Android app (IOT Transmission) built with MIT App Inventor

---

## Hardware Components

- NodeMCU ESP8266 (V3) Wi-Fi module
- Step-down transformer
- ASM1117 voltage regulator IC
- 3 relays (for 3-phase line multiplexing)
- Diodes for voltage regulation
- Resistors, capacitors
- LED loads (prototype)

---

## How It Works

1. System powers up and continuously reads three-phase line voltages via relay multiplexing
2. Each relay switches to its phase line for 1 second, sending voltage to NodeMCU analog pin (A0)
3. NodeMCU reads analog values (0-1024 range) and classifies line status:
   - D3 = 2.6V → ADC value 850-1000 (line in service)
   - D2 = 1.9V → ADC value 550-650 (line in service)
   - D1 = 1.2V → ADC value 400-500 (line in service)
   - 0V → ADC value 0-100 (fault detected)
4. Fault data transmitted via Wi-Fi to Firebase cloud server
5. Android app displays real-time line status and fault notifications

---

## Results

The prototype successfully detected and classified all fault types:
- Line-to-ground faults on individual phases
- Phase-to-phase short circuits
- Multi-line simultaneous faults

Fault detection response time: approximately 4 seconds per full 3-phase cycle.

---

## Publication

International Journal of Scientific and Research Publications (IJSRP)
Volume 13, Issue 7, July 2023, ISSN 2250-3153
DOI: http://dx.doi.org/10.29322/IJSRP.13.07.2023.p13921

---

## Related Projects

- [Hybrid A*-RRT* Path Planner](https://github.com/Asif-Ucchwas/hybrid-a-star-rrtstar-path-planning) — MES Thesis, Lamar University 2026
- Smartphone-Controlled Mobile Robot — 3rd place, national robotics competition, Bangladesh

---

## Contact

- LinkedIn: https://linkedin.com/in/masifuzzaman
- GitHub: https://github.com/Asif-Ucchwas
- Email: asifuzzamanucchwas@gmail.com
