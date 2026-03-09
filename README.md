# Maze Navigator 🧩

> Autonomous maze-solving robot using a Raspberry Pi Pico and ultrasonic sensors.

## Overview

An autonomous robot developed using a **Raspberry Pi Pico** and **Python** to navigate a standard maze as part of a university course project. The robot uses an **Asynchronous Finite State Machine (AFSM)** to implement modular and robust navigation behaviours including wall-following and turning, guided by real-time data from multiple ultrasonic sensors.

Completed independently, this project demonstrates strong problem-solving skills and hands-on proficiency in embedded systems and autonomous control.

## Features

- 🗺️ **Autonomous Maze Traversal** — Navigates from start to finish without human input
- 🔁 **AFSM Architecture** — Structured state machine for reliable and modular behaviour control
- 📡 **Multi-Sensor Fusion** — Combines data from multiple ultrasonic sensors for reliable obstacle detection
- 🔄 **Wall-Following Algorithm** — Follows maze walls to efficiently navigate corridors
- ⚡ **Real-Time Control** — Low-latency sensor polling and motor response

## State Machine Design

```
           ┌─────────────────────────────────────┐
           ↓                                     |
[INIT] → [FORWARD] → [CHECK_WALLS] → [TURN_LEFT / TURN_RIGHT]
                          ↓
                      [REVERSE]
                          ↓
                       [STOP]
```

Each state runs asynchronously, allowing sensor polling and motor control to operate concurrently without blocking.

## Tech Stack

| Category | Tools |
|---|---|
| Microcontroller | Raspberry Pi Pico |
| Language | MicroPython / Python |
| Sensors | HC-SR04 Ultrasonic (x3) |
| Actuation | DC Motors + L298N Driver |
| Control Logic | Asynchronous FSM (asyncio) |

## Project Structure

```
Maze-Navigator/
├── main.py                # Entry point + state machine runner
├── states/
│   ├── forward.py         # Move forward state
│   ├── check_walls.py     # Sensor reading + decision state
│   ├── turn.py            # Turn left/right state
│   └── reverse.py         # Back-up state
├── sensors/
│   └── ultrasonic.py      # HC-SR04 driver
├── motors/
│   └── driver.py          # L298N motor control
├── config.py              # Thresholds and tuning
└── README.md
```

## Getting Started

### Hardware Required

- Raspberry Pi Pico
- 3× HC-SR04 Ultrasonic Sensors (front, left, right)
- L298N Motor Driver Module
- 2× DC Gear Motors
- Chassis + wheels
- 5V power bank

### Setup

1. Flash MicroPython onto the Raspberry Pi Pico
2. Upload all files using Thonny or `mpremote`
3. Wire sensors and motors per the schematic in `/docs`
4. Run `main.py`

## Results

- ✅ Successfully navigated standard university maze layout
- ✅ Robust wall-following with minimal sensor noise sensitivity
- ✅ AFSM design enabled easy debugging and behaviour tuning

## Skills Demonstrated

`Raspberry Pi Pico` · `Python` · `MicroPython` · `Autonomous Navigation` · `State Machine` · `Ultrasonic Sensors` · `Embedded Systems`
