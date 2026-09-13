# 🚁 5-Inch FPV Drone

A custom-built **5-inch FPV drone** built around the **SpeedyBee F405 V4 flight controller + ESC stack**, T-Motor VLOX motors, and an **ExpressLRS (ELRS)** radio system.

The drone was assembled, wired, configured, and tuned using **Betaflight**, creating a responsive and reliable FPV platform.

---

## ✨ Features

* 🛩️ 5-inch FPV drone
* ⚡ 4 × T-Motor VLOX 2207 2250KV motors
* 🧠 SpeedyBee F405 V4 FC + ESC Stack
* 📡 ExpressLRS (ELRS) receiver
* 🎮 RadioMaster TX15 transmitter
* ⚙️ Betaflight flight controller configuration
* 🔧 Custom-built and configured
* 🔄 Props Out motor configuration

---

## 🧩 Hardware

| Component                  | Specification                       |
| -------------------------- | ----------------------------------- |
| Flight Controller          | SpeedyBee F405 V4                   |
| ESC                        | SpeedyBee F405 V4 Stack             |
| Motors                     | T-Motor VLOX 2207 2250KV            |
| Propeller Size             | 5 inch                              |
| Radio Receiver             | ExpressLRS (ELRS)                   |
| Radio Transmitter          | RadioMaster TX15                    |
| Flight Controller Firmware | Betaflight                          |
| Frame                      | 5-inch FPV frame                    |
| Battery                    | LiPo battery suitable for the setup |

---

## ⚙️ Motor Configuration

The drone uses a **Props Out** configuration.

### Motor Layout

```text
                    FRONT
          ┌─────────────────────┐
          │                     │
       M3 ↻                   ↺ M1
          │                     │
          │                     │
       M4 ↺                   ↻ M2
          │                     │
          └─────────────────────┘
                    REAR
```

### Motor Positions

| Position    | Motor |
| ----------- | ----- |
| Front Left  | M3    |
| Front Right | M1    |
| Rear Left   | M4    |
| Rear Right  | M2    |

### Motor Rotation

```text
Front Left  → M3 ↻
Front Right → M1 ↺

Rear Left   → M4 ↺
Rear Right  → M2 ↻
```

This is a **Props Out** setup, where the front propellers rotate outward from the center of the drone.

> ⚠️ Always verify motor order and motor rotation in Betaflight with the propellers removed before flight.

---

## 🔌 Electronics

### SpeedyBee F405 V4 Stack

The **SpeedyBee F405 V4 stack** serves as the main flight-control and motor-control system.

The flight controller:

* Processes gyro and accelerometer data
* Runs Betaflight
* Receives commands from the ELRS receiver
* Sends motor commands to the ESC
* Handles flight stabilization
* Provides battery monitoring and OSD functionality

The ESC drives the four brushless motors based on commands from the flight controller.

---

## 📡 ExpressLRS Receiver

The drone uses an **ExpressLRS (ELRS)** receiver for the radio-control link.

Typical connection:

```text
        ELRS RECEIVER
             │
       ┌─────┼─────┐
       │     │     │
      5V    GND   TX/RX
       │     │     │
       └─────┼─────┘
             │
             ▼
    SpeedyBee F405 V4 FC
             │
             ▼
         Betaflight
```

The receiver communicates with Betaflight through a UART using a serial protocol.

> The exact UART and pad connections depend on the wiring used in this particular build.

---

## 🎮 RadioMaster TX15

The **RadioMaster TX15** is used as the primary transmitter.

The transmitter communicates with the onboard ELRS receiver.

Typical flight controls:

```text
LEFT STICK
├── Throttle
└── Yaw

RIGHT STICK
├── Roll
└── Pitch
```

Auxiliary switches can be configured for:

```text
ARM
FLIGHT MODES
BEEPER
OTHER AUX FUNCTIONS
```

The exact switch mapping depends on the Betaflight and transmitter configuration.

---

## 🖥️ Betaflight Configuration

The drone is configured using **Betaflight**.

Main configuration areas include:

* Flight controller setup
* Receiver configuration
* ELRS configuration
* UART configuration
* Motor configuration
* Motor direction
* ARM switch
* Flight modes
* OSD
* Failsafe
* Battery monitoring
* PID tuning
* Filters
* Rates

### Important Betaflight Checks

Before the first flight:

1. Connect the flight controller to Betaflight.
2. Verify the flight controller orientation.
3. Check receiver communication.
4. Confirm all transmitter channels.
5. Verify the ARM switch.
6. Check motor numbering.
7. Check motor rotation direction.
8. Verify the Props Out configuration.
9. Configure and test failsafe.
10. Verify battery voltage readings.
11. Perform a final pre-flight inspection.

---

## 🔋 Power System

The battery supplies power to the ESC stack, which powers the four brushless motors.

Before flying, verify:

* Battery voltage
* ESC voltage rating
* Motor KV
* Propeller size
* Current requirements
* Battery connector
* Battery polarity
* LiPo battery condition

> ⚠️ Never connect a battery with reversed polarity.

---

## 🛠️ Build Process

The drone was assembled following a basic FPV build workflow:

```text
5-INCH FRAME
     │
     ▼
INSTALL MOTORS
     │
     ▼
INSTALL SPEEDYBEE F405 V4 STACK
     │
     ▼
CONNECT MOTORS TO ESC
     │
     ▼
CONNECT ELRS RECEIVER
     │
     ▼
CONNECT POWER SYSTEM
     │
     ▼
FLASH / CONFIGURE BETAFIGHT
     │
     ▼
CONFIGURE ELRS
     │
     ▼
CHECK MOTOR ORDER
     │
     ▼
CHECK MOTOR DIRECTION
     │
     ▼
CONFIGURE PROPS OUT
     │
     ▼
CONFIGURE ARM & MODES
     │
     ▼
CONFIGURE OSD & FAILSAFE
     │
     ▼
PID / RATE CONFIGURATION
     │
     ▼
FINAL SAFETY CHECK
     │
     ▼
🚁 FIRST FLIGHT
```

---

## 🧪 Pre-Flight Checklist

Before installing the propellers:

* [ ] Flight controller orientation is correct
* [ ] Receiver is communicating
* [ ] Roll, pitch, yaw and throttle channels work correctly
* [ ] ARM switch works correctly
* [ ] Motor numbering is correct
* [ ] Motor rotation is correct
* [ ] Props Out configuration is correct
* [ ] Failsafe is configured and tested
* [ ] Battery voltage reading is correct
* [ ] No short circuits
* [ ] All screws are secure
* [ ] Motors spin freely

### ⚠️ Motor Testing

**REMOVE ALL PROPELLERS before testing motors.**

Never test motor direction with propellers installed.

---

## 📁 Repository Structure

A suggested repository structure:

```text
5-inch-fpv-drone/
│
├── README.md
│
├── betaflight/
│   └── configuration.txt
│
├── wiring/
│   └── wiring-diagram.png
│
├── photos/
│   ├── build.jpg
│   ├── electronics.jpg
│   └── final-drone.jpg
│
└── videos/
    └── flight-demo.mp4
```

You can modify the structure according to the files you upload to GitHub.

---

## 📸 Build Photos

Add your build photos here:

```markdown
![Drone Build](photos/build.jpg)

![Electronics](photos/electronics.jpg)

![Completed Drone](photos/final-drone.jpg)
```

---

## 🎥 Flight Video

If you upload a flight video to YouTube, you can add it here:

```markdown
[![FPV Drone Flight](https://img.youtube.com/vi/YOUR_VIDEO_ID/maxresdefault.jpg)](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)
```

Replace `YOUR_VIDEO_ID` with your actual YouTube video ID.

---

## 🛠️ Tools & Software

### Software

* **Betaflight Configurator**
* **ExpressLRS**
* RadioMaster / EdgeTX configuration tools

### Hardware Tools

* Soldering iron
* Solder
* Multimeter
* Hex drivers
* Wire cutters
* LiPo battery charger
* Smoke stopper recommended for initial power-up

---

## 📋 Build Specifications

```text
╔══════════════════════════════════════╗
║         5-INCH FPV DRONE             ║
╠══════════════════════════════════════╣
║ Flight Controller : SpeedyBee F405 V4
║ ESC                : SpeedyBee F405 V4
║ Motors             : T-Motor VLOX 2207
║ Motor KV           : 2250KV
║ Propeller Size     : 5 inch
║ Radio Receiver     : ExpressLRS
║ Transmitter        : RadioMaster TX15
║ Firmware           : Betaflight
║ Motor Configuration : Props Out
╚══════════════════════════════════════╝
```

---

## 🚀 Possible Future Improvements

* [ ] Add GPS
* [ ] Configure GPS Rescue
* [ ] Add self-powered buzzer
* [ ] Analyze Blackbox logs
* [ ] Perform custom PID tuning
* [ ] Optimize filters
* [ ] Fine-tune rates
* [ ] Add detailed wiring diagram
* [ ] Document battery and propeller combinations
* [ ] Add flight-performance data
* [ ] Add flight footage

---

## ⚠️ Safety

FPV drones use **high-speed rotating propellers and high-current LiPo batteries**.

Always:

* Remove propellers during bench configuration.
* Keep fingers away from motors.
* Verify motor direction before installing props.
* Configure and test failsafe.
* Inspect LiPo batteries before use.
* Use a suitable LiPo charger.
* Fly in an appropriate open area.
* Keep people, animals, and obstacles away from the flight area.
* Follow local drone regulations.

**Safety first — especially during the first power-up and motor tests.**

---

## 👨‍🔧 About This Project

This is a **custom-built 5-inch FPV drone** assembled and configured using commercially available FPV components.

The project combines:

**SpeedyBee F405 V4 + T-Motor VLOX 2207 2250KV + ELRS + RadioMaster TX15 + Betaflight**

The repository contains the build information, configuration details, wiring documentation, photos, and other resources related to the drone.

---

## ⭐ Support

If you found this project useful or interesting, consider giving the repository a ⭐ on GitHub.

**Build. Configure. Fly. 🚁**
