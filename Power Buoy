# Triple-Source Power Buoy Monitoring System

[![Arduino](https://img.shields.io/badge/Arduino-R4%20WiFi-00979D?style=flat&logo=arduino)](https://www.arduino.cc/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Active-success.svg)]()

A robust, triple-redundant power monitoring system designed for autonomous marine buoy applications. This system combines dual solar power, Faraday wave energy generation, and intelligent power management with real-time WiFi monitoring.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Hardware Requirements](#hardware-requirements)
- [System Architecture](#system-architecture)
- [Installation](#installation)
- [Wiring Diagram](#wiring-diagram)
- [Configuration](#configuration)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Troubleshooting](#troubleshooting)
- [Maintenance](#maintenance)
- [License](#license)

## 🌊 Overview

This project implements a **triple-redundant power generation system** for autonomous marine buoys, featuring:

1. **Dual Solar Power Systems** - Two independent 5V solar panels with DFRobot SP110 charge controllers
2. **Faraday Wave Energy Generator** - Electromagnetic induction system powered by wave motion
3. **Intelligent Power Management** - Automatic source switching based on availability and battery status
4. **WiFi Monitoring** - Real-time data access via JSON API
5. **Bluetooth Connectivity** - Alternative monitoring interface

### Power Source Priority

The system automatically selects the optimal power source:

```
Priority 1: Faraday Wave Generator (renewable, wave-powered)
Priority 2: Solar Power (dual redundant systems)
Priority 3: Battery Reserve (automatic cutoff protection)
```

## ✨ Features

- ⚡ **Triple Power Generation**
- Dual solar panels with independent charge controllers
- Faraday electromagnetic wave energy harvesting
- Intelligent automatic source switching

- 🔋 **Advanced Battery Management**
- Real-time voltage and percentage monitoring
- Overcharge protection (4.2V cutoff)
- Deep discharge prevention (3.0V minimum)
- Automatic charging threshold (20% trigger)

- 📊 **Comprehensive Monitoring**
- Individual power source tracking
- Cumulative energy generation (Wh)
- Battery health status
- Charging state indicators

- 🌐 **Connectivity**
- WiFi web server with JSON API
- Bluetooth serial interface (HC-05)
- Serial monitor output (115200 baud)

- 🔄 **Redundancy & Reliability**
- Three independent power sources
- Automatic failover switching
- Continuous operation capability

## 🛠️ Hardware Requirements

### Main Components

| Component | Quantity | Specifications | Purpose |
|-----------|----------|----------------|---------|
| **Arduino R4 WiFi** | 1 | Main microcontroller with WiFi | System controller and data processor |
| **DFRobot Solar Power Manager (SP110)** | 2 | I2C interface, MPPT charging | Solar charge controllers |
| **5V Solar Panels** | 2 | 5V output, weather-resistant, 5-10W recommended | Primary solar power generation |
| **Li-ion Batteries (Solar)** | 2 | 3.7V nominal, 2000-5000mAh | Solar system energy storage |
| **Li-ion Battery (Main)** | 1 | 3.7V nominal, 5000-10000mAh | Main system battery |
| **Neodymium Magnets** | 8 | N52 grade, 10-15mm diameter | Faraday generator magnets |
| **Copper Wire Coil** | 1 | 8 feet, 26-30 AWG, ~1000 turns | Faraday electromagnetic coil |
| **PVC Tube** | 1 | 1-2" diameter, 6-12" length | Faraday generator housing |
| **HC-05 Bluetooth Module** | 1 | Serial UART interface | Bluetooth connectivity |
| **Voltage Dividers** | 2 | For A0 and A1 analog inputs | Battery voltage sensing |
| **MOSFETs or Relays** | 2 | For pins 7 and 8 | Charging control switches |

### Faraday Wave Generator Components

The Faraday generator converts wave motion into electrical energy:

```
┌─────────────────────────────────────┐
│     FARADAY WAVE GENERATOR          │
│                                     │
│  ┌─────────────────────────────┐   │
│  │   PVC Tube (Housing)        │   │
│  │                             │   │
│  │  ┌──┐  ┌──┐  ┌──┐  ┌──┐   │   │
│  │  │M │  │M │  │M │  │M │   │   │ M = Neodymium
│  │  └──┘  └──┘  └──┘  └──┘   │   │     Magnet
│  │  ┌──┐  ┌──┐  ┌──┐  ┌──┐   │   │
│  │  │M │  │M │  │M │  │M │   │   │
│  │  └──┘  └──┘  └──┘  └──┘   │   │
│  │                             │   │
│  │  ╔═══════════════════════╗ │   │
│  │  ║ Copper Coil (~1000    ║ │   │
│  │  ║ turns, 8ft wire)      ║ │   │
│  │  ╚═══════════════════════╝ │   │
│  │                             │   │
│  └─────────────────────────────┘   │
│           │                         │
│           ▼                         │
│    Rectifier Bridge                 │
│    (AC to DC conversion)            │
│           │                         │
│           ▼                         │
│    To Arduino A1 Pin                │
└─────────────────────────────────────┘
```

### Additional Materials

- **Enclosure**: Waterproof IP67+ rated enclosure for electronics
- **Connectors**: Marine-grade waterproof connectors
- **Wiring**: 18-22 AWG stranded wire, marine grade
- **Rectifier Bridge**: Full-wave rectifier for Faraday AC output
- **Smoothing Capacitors**: 100-1000µF for Faraday output stabilization
- **Mounting Hardware**: Stainless steel or marine-grade fasteners
- **Cable Glands**: Waterproof cable entry points
- **Heat Shrink Tubing**: For connection protection
- **Silica Gel Packets**: Moisture control inside enclosure

### Optional Components

- **SD Card Module**: For data logging
- **RTC Module**: Real-time clock for timestamping
- **Temperature Sensors**: Monitor ambient and battery temperature
- **Status LEDs**: Visual system status indicators
- **GPS Module**: Location tracking for mobile buoys
- **LoRa Module**: Long-range communication backup

## 🏗️ System Architecture

```
┌──────────────────────────────────────────────────────────────────┐
│                  TRIPLE-SOURCE POWER BUOY SYSTEM                  │
├──────────────────────────────────────────────────────────────────┤
│                                                                   │
│  ┌──────────────┐              ┌──────────────┐                 │
│  │ Solar Panel 1│              │ Solar Panel 2│                 │
│  │    (5V)      │              │    (5V)      │                 │
│  └──────┬───────┘              └──────┬───────┘                 │
│         │                              │                         │
│         ▼                              ▼                         │
│  ┌──────────────┐              ┌──────────────┐                 │
│  │   SP110 #1   │              │   SP110 #2   │                 │
│  │  (Addr 0x10) │              │  (Addr 0x11) │                 │
│  └──────┬───────┘              └──────┬───────┘                 │
│         │                              │                         │
│         │         ┌──────────┐         │                         │
│         ├─────────┤ Arduino  ├─────────┤                         │
│         │   I2C   │ R4 WiFi  │   I2C   │                         │
│         │         │          │         │                         │
│         │         │ A0  A1   │         │                         │
│         │         │ │   │    │         │                         │
│         │         │ │   │    │         │                         │
│         ▼         │ ▼   ▼    │         ▼                         │
│  ┌──────────────┐ │ │   │    │  ┌──────────────┐                │
│  │  Battery 1   │ │ │   │    │  │  Battery 2   │                │
│  │   (3.7V)     │ │ │   │    │  │   (3.7V)     │                │
│  └──────────────┘ │ │   │    │  └──────────────┘                │
│                   │ │   │    │                                   │
│                   │ │   │    │  ┌─────────────────────────────┐ │
│                   │ │   │    │  │  Faraday Wave Generator     │ │
│                   │ │   │    │  │  ┌──────────────────────┐   │ │
│                   │ │   │    │  │  │ 8 Neodymium Magnets  │   │ │
│                   │ │   │    │  │  │ Copper Coil (8ft)    │   │ │
│                   │ │   │    │  │  │ PVC Tube Housing     │   │ │
│                   │ │   │    │  │  └──────────┬───────────┘   │ │
│                   │ │   │    │  │             │               │ │
│                   │ │   │    │  │        Rectifier            │ │
│                   │ │   └────┼──┼─────────────┘               │ │
│                   │ │        │  └─────────────────────────────┘ │
│                   │ │        │                                   │
│                   │ │        │  ┌─────────────┐                 │
│                   │ └────────┼──┤ Main Battery│                 │
│                   │          │  │   (3.7V)    │                 │
│                   │          │  └─────────────┘                 │
│                   │          │                                   │
│                   │          ▼                                   │
│                   │    ┌──────────┐                             │
│                   │    │  WiFi    │                             │
│                   │    │  Server  │                             │
│                   │    └──────────┘                             │
│                   │                                              │
│                   │    ┌──────────┐                             │
│                   └────┤ Bluetooth│                             │
│                        │  HC-05   │                             │
│                        └──────────┘                             │
│                                                                   │
└──────────────────────────────────────────────────────────────────┘
```

## 📥 Installation

### 1. Software Setup

#### Install Arduino IDE
Download and install the latest Arduino IDE from [arduino.cc](https://www.arduino.cc/en/software)

#### Install Required Libraries

Open Arduino IDE and navigate to **Tools → Manage Libraries**, then search and install:

1. **DFRobot_SP110** - Solar Power Manager library
2. **WiFiS3** - WiFi library for Arduino R4 (pre-installed)
3. **ArduinoJson** - JSON serialization library
4. **Wire** - I2C communication (pre-installed)

#### Install Arduino R4 WiFi Board Support

1. Go to **Tools → Board → Boards Manager**
2. Search for "Arduino UNO R4"
3. Install "Arduino UNO R4 Boards"

### 2. Build Faraday Wave Generator

#### Materials Needed
- PVC tube (1-2" diameter, 6-12" length)
- 8 neodymium magnets (N52 grade, 10-15mm)
- Copper wire (26-30 AWG, 8 feet)
- End caps for PVC tube
- Rectifier bridge (1A, 50V)
- Smoothing capacitor (470µF, 16V)

#### Assembly Steps

1. **Prepare Magnet Assembly**
 - Arrange 8 magnets in alternating polarity (N-S-N-S-N-S-N-S)
 - Secure magnets inside PVC tube with non-conductive spacers
 - Ensure magnets can move freely within tube

2. **Wind Copper Coil**
 - Wrap copper wire around outside of PVC tube (~1000 turns)
 - Keep windings tight and uniform
 - Leave 6-8 inches of wire on each end for connections

3. **Add Rectifier Circuit**
 - Connect coil output to full-wave rectifier bridge
 - Add smoothing capacitor across DC output
 - Connect positive output to Arduino A1 through voltage divider
 - Connect negative to Arduino GND

4. **Seal and Waterproof**
 - Install end caps on PVC tube
 - Apply marine sealant to all joints
 - Protect coil with heat shrink or waterproof coating

### 3. Hardware Assembly

#### Step 1: Configure SP110 Modules

1. SP110 #1: Leave at default address (0x10)
2. SP110 #2: Change address to 0x11 (refer to SP110 documentation)

#### Step 2: Connect I2C Bus

```
Arduino R4 WiFi → SP110 #1 & SP110 #2
SDA → SDA (both modules)
SCL → SCL (both modules)
GND → GND (both modules)
5V → VCC (both modules, if needed)
```

#### Step 3: Connect Analog Inputs

```
A0 → Main Battery Voltage (through voltage divider)
A1 → Faraday Generator Output (through voltage divider)
```

**Voltage Divider Circuit for 3.3V ADC:**
```
Battery+ ──┬── 10kΩ ──┬── A0/A1
         │          │
        GND     ──  3.3kΩ ──┬── GND
                             │
```

#### Step 4: Connect Control Pins

```
Pin 7 → Solar Charging Control (MOSFET/Relay)
Pin 8 → Faraday Charging Control (MOSFET/Relay)
```

#### Step 5: Connect Bluetooth Module

```
Arduino R4    HC-05
Pin 2 (RX) → TX
Pin 3 (TX) → RX
5V → VCC
GND → GND
```

#### Step 6: Power Connections

- Solar Panel 1 → SP110 #1 Solar Input
- Solar Panel 2 → SP110 #2 Solar Input
- Battery 1 → SP110 #1 Battery Output
- Battery 2 → SP110 #2 Battery Output
- Main Battery → Charging control circuit
- Faraday Generator → Rectifier → A1 Pin

### 4. Upload Code

1. Open the provided `.ino` file in Arduino IDE
2. Update WiFi credentials in code:
 ```cpp
 const char* ssid = "YOUR_WIFI_SSID";
 const char* password = "YOUR_WIFI_PASSWORD";
 ```
3. Select **Tools → Board → Arduino UNO R4 WiFi**
4. Select correct **Port** under **Tools → Port**
5. Click **Upload** button
6. Wait for "Done uploading" message

## 🔌 Wiring Diagram

### Complete System Wiring

```
┌─────────────────────────────────────────────────────────────────┐
│                     ARDUINO R4 WIFI                              │
│                                                                  │
│  SDA ───────┬─────────── SP110 #1 (SDA)                         │
│  SCL ───────┼─────┬───── SP110 #1 (SCL)                         │
│  GND ───────┼─────┼─┬─── SP110 #1 (GND)                         │
│  5V  ───────┼─────┼─┼─── SP110 #1 (VCC)                         │
│             │     │ │                                            │
│             └─────┼─┼─── SP110 #2 (SDA)                         │
│                   └─┼─── SP110 #2 (SCL)                         │
│                     ├─── SP110 #2 (GND)                         │
│                     └─── SP110 #2 (VCC)                         │
│                                                                  │
│  A0 ─────── Main Battery (via voltage divider)                  │
│  A1 ─────── Faraday Generator (via voltage divider)             │
│                                                                  │
│  Pin 7 ──── Solar Charging Control (MOSFET)                     │
│  Pin 8 ──── Faraday Charging Control (MOSFET)                   │
│                                                                  │
│  Pin 2 (RX) ── HC-05 (TX)                                       │
│  Pin 3 (TX) ── HC-05 (RX)                                       │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

## ⚙️ Configuration

### WiFi Settings

Update your WiFi credentials in the code:

```cpp
const char* ssid = "YOUR_NETWORK_NAME";
const char* password = "YOUR_PASSWORD";
```

### Battery Parameters

Adjust for your specific battery:

```cpp
const float maxBatteryVoltage = 4.2;  // Li-ion max voltage
const float minBatteryVoltage = 3.0;  // Li-ion min voltage
const float batteryThreshold = 20.0;  // Charging trigger percentage
```

### Faraday Generator Settings

Calibrate based on your generator output:

```cpp
const float faradayMinVoltage = 2.0;  // Minimum voltage for charging
```

### Update Intervals

```cpp
const unsigned long CHECK_INTERVAL = 5000;  // 5 seconds (demo)
const unsigned long WIFI_UPDATE_INTERVAL = 60000;  // 1 minute
```

For production deployment, increase `CHECK_INTERVAL` to 30000-60000ms.

## 🖥️ Usage

### Starting the System

1. Connect Arduino R4 WiFi to computer via USB
2. Open **Tools → Serial Monitor** in Arduino IDE
3. Set baud rate to **115200**
4. System will initialize all components
5. Note the IP address displayed for WiFi access

### Serial Monitor Output

```
========================================
Triple-Source Power Buoy System
========================================

Initializing Solar Power Managers...
✓ Solar Manager 1 initialized
✓ Solar Manager 2 initialized
Connecting to WiFi: YourNetwork
✓ WiFi connected
IP address: 192.168.1.100

✓ System Ready!
========================================

╔════════════════════════════════════════════════════════╗
║          TRIPLE-SOURCE POWER BUOY STATUS              ║
╚════════════════════════════════════════════════════════╝

┌─── MAIN BATTERY ───────────────────────────────────────┐
│ Voltage: 3.85 V
│ Level: 70.8 %
│ Status: NORMAL
│ Primary Source: FARADAY
└────────────────────────────────────────────────────────┘

┌─── SOLAR SYSTEM 1 ─────────────────────────────────────┐
│ Panel: 5.12 V @ 245.3 mA
│ Power: 1.25 W
│ Battery: 3.92 V (76.7%)
│ Energy: 0.125 Wh
│ Status: CHARGING
└────────────────────────────────────────────────────────┘

┌─── SOLAR SYSTEM 2 ─────────────────────────────────────┐
│ Panel: 5.08 V @ 238.1 mA
│ Power: 1.21 W
│ Battery: 3.88 V (73.3%)
│ Energy: 0.118 Wh
│ Status: CHARGING
└────────────────────────────────────────────────────────┘

┌─── FARADAY WAVE GENERATOR ─────────────────────────────┐
│ Voltage: 2.45 V
│ Power: 0.245 W
│ Energy: 0.032 Wh
│ Status: ACTIVE
│ Charging: ON
└────────────────────────────────────────────────────────┘

┌─── COMBINED SYSTEM ────────────────────────────────────┐
│ Total Power: 2.71 W
│ Total Energy: 0.275 Wh
│ Uptime: 325 seconds
└────────────────────────────────────────────────────────┘
```

## 📡 API Documentation

### WiFi JSON API

Access real-time data by navigating to the Arduino's IP address in a web browser or making HTTP requests.

**Endpoint:** `http://[ARDUINO_IP]/`

**Method:** GET

**Response Format:** JSON

#### Example Response

```json
{
"main_battery": {
  "voltage": 3.85,
  "percentage": 70.8,
  "status": "NORMAL"
},
"solar1": {
  "voltage": 5.12,
  "current": 0.245,
  "power": 1.25,
  "energy": 0.125,
  "charging": true
},
"solar2": {
  "voltage": 5.08,
  "current": 0.238,
  "power": 1.21,
  "energy": 0.118,
  "charging": true
},
"faraday": {
  "voltage": 2.45,
  "power": 0.245,
  "energy": 0.032,
  "active": true
},
"system": {
  "primary_source": "FARADAY",
  "solar_active": false,
  "faraday_active": true,
  "uptime": 325
}
}
```

#### Status Codes

| Status | Description |
|--------|-------------|
| CRITICAL | Battery ≤ 10% |
| LOW | Battery ≤ 30% |
| NORMAL | Battery 30-90% |
| FULL | Battery ≥ 90% |

### Bluetooth Interface

Connect via HC-05 Bluetooth module at 9600 baud to receive the same JSON data stream.

## 🔧 Troubleshooting

### Solar Manager Issues

**Problem:** "Solar Manager X failed to initialize"

**Solutions:**
1. Check I2C wiring (SDA, SCL, GND)
2. Verify I2C addresses (0x10 and 0x11)
3. Ensure SP110 modules are powered
4. Try external 4.7kΩ pull-up resistors on SDA/SCL

### Faraday Generator Issues

**Problem:** Faraday voltage always reads 0V

**Solutions:**
1. Check rectifier circuit connections
2. Test coil continuity with multimeter
3. Verify magnet polarity alternates correctly
4. Ensure magnets can move freely in tube
5. Check voltage divider to A1 pin
6. Test by shaking generator vigorously

**Problem:** Faraday voltage unstable or noisy

**Solutions:**
1. Add larger smoothing capacitor (1000µF)
2. Add RC filter on ADC input
3. Increase number of coil turns
4. Use stronger magnets (N52 grade)

### WiFi Connection Issues

**Problem:** Cannot connect to WiFi

**Solutions:**
1. Verify SSID and password are correct
2. Check if network is 2.4GHz (R4 WiFi doesn't support 5GHz)
3. Move closer to WiFi router
4. Check router allows new device connections

**Problem:** WiFi keeps disconnecting

**Solutions:**
1. Improve WiFi signal strength
2. Use WiFi extender or access point
3. Check for network congestion
4. Verify power supply is stable

### Battery Charging Issues

**Problem:** Main battery not charging

**Solutions:**
1. Check MOSFET/relay connections on pins 7 and 8
2. Verify charging logic in serial output
3. Test Faraday generator output voltage
4. Check solar panel voltages
5. Verify battery isn't already full (4.2V)

### Power Source Selection Issues

**Problem:** System doesn't switch to Faraday when available

**Solutions:**
1. Check `faradayMinVoltage` threshold setting
2. Verify Faraday voltage reading on A1
3. Test pin 8 output with LED
4. Check charging control circuit

## 🔄 Maintenance

### Daily Checks (Automated via Monitoring)

- [ ] Monitor battery voltage levels
- [ ] Check power generation from all sources
- [ ] Verify WiFi connectivity
- [ ] Review charging status

### Weekly Checks

- [ ] Inspect solar panels for dirt or debris
- [ ] Check Faraday generator for mechanical issues
- [ ] Verify all cable connections
- [ ] Check enclosure seals
- [ ] Test Bluetooth connectivity

### Monthly Maintenance

- [ ] Clean solar panels with fresh water
- [ ] Inspect Faraday generator magnets and coil
- [ ] Check battery health and capacity
- [ ] Verify mounting hardware is secure
- [ ] Replace silica gel packets
- [ ] Download and backup monitoring data
- [ ] Test all three power sources individually

### Quarterly Maintenance

- [ ] Disassemble and inspect Faraday generator
- [ ] Test battery capacity with load test
- [ ] Check for corrosion on all connections
- [ ] Verify rectifier and smoothing capacitors
- [ ] Update firmware if available
- [ ] Calibrate voltage sensors

### Annual Maintenance

- [ ] Replace batteries if capacity degraded >20%
- [ ] Rebuild Faraday generator if performance degraded
- [ ] Apply anti-corrosion treatment
- [ ] Replace worn cable glands
- [ ] Full system performance test
- [ ] Update all documentation

## 🌐 Future Enhancements

### Hardware Upgrades

- **MPPT Controller for Faraday**: Maximize power extraction from wave motion
- **Larger Faraday Generator**: Increase coil turns and magnet count
- **GPS Module**: Location tracking for mobile buoys
- **LoRa Communication**: Long-range data transmission
- **Solar Panel Tracking**: Motorized solar panel orientation

### Software Enhancements

- **Machine Learning**: Predict optimal power source based on weather
- **Cloud Integration**: Upload data to AWS/Azure IoT
- **Mobile App**: Dedicated monitoring application
- **Data Analytics**: Historical performance analysis
- **Alert System**: Email/SMS notifications for critical conditions
- **Web Dashboard**: Real-time visualization with charts

### System Improvements

- **Load Management**: Automatic load shedding based on battery level
- **Energy Forecasting**: Predict available power based on weather
- **Adaptive Charging**: Optimize charging algorithms
- **Multi-Buoy Network**: Coordinate multiple buoys
- **Remote Firmware Updates**: OTA (Over-The-Air) updates

## 📝 Technical Specifications

### Power Generation Capacity

| Source | Voltage | Current | Power | Notes |
|--------|---------|---------|-------|-------|
| Solar Panel 1 | 5V | 0-2A | 0-10W | Weather dependent |
| Solar Panel 2 | 5V | 0-2A | 0-10W | Weather dependent |
| Faraday Generator | 0-5V | 0-0.5A | 0-2.5W | Wave motion dependent |
| **Total** | - | - | **0-22.5W** | Combined maximum |

### Battery Specifications

| Parameter | Value | Notes |
|-----------|-------|-------|
| Chemistry | Li-ion 18650 | Standard cells |
| Nominal Voltage | 3.7V | Per cell |
| Charge Voltage | 4.2V | Maximum |
| Discharge Cutoff | 3.0V | Minimum safe |
| Capacity | 5000-10000mAh | Main battery |
| Cycle Life | 500-1000 cycles | Typical |

### Environmental Ratings

| Parameter | Rating | Notes |
|-----------|--------|-------|
| Operating Temperature | -10°C to 50°C | Electronics |
| Storage Temperature | -20°C to 60°C | Without batteries |
| Humidity | 0-95% RH | Non-condensing |
| Water Resistance | IP67 | With proper enclosure |
| Salt Spray | 1000 hours | With marine-grade components |

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 👥 Authors

- Triple-source power system design
- Faraday wave energy integration
- WiFi and Bluetooth monitoring implementation

## 🙏 Acknowledgments

- DFRobot for SP110 Solar Power Manager
- Arduino community for development tools
- Marine renewable energy researchers
- Electromagnetic induction pioneers

## 📞 Support

For questions or issues:

- Open an issue on GitHub
- Check troubleshooting section
- Consult component datasheets
- Arduino R4 WiFi documentation

---

**⚠️ Safety Warning**: 

This system involves:
- Electrical components and batteries
- Electromagnetic fields from Faraday generator
- High-energy neodymium magnets (pinch hazard)
- Marine deployment hazards

Always follow proper safety procedures. Use appropriate protective equipment. For marine applications, follow all relevant maritime safety regulations.

**🌊 Marine Deployment Note**: 

Ensure all components are properly waterproofed and rated for marine environments. The Faraday generator must be securely mounted to capture wave motion while preventing damage from excessive movement. Regular maintenance is critical for reliable operation in harsh marine conditions.

**🧲 Magnet Safety**: 

Neodymium magnets are extremely powerful and can cause serious injury:
- Keep away from pacemakers and electronic devices
- Prevent finger pinching between magnets
- Store magnets safely when not in use
- Handle with care during assembly

---

*Last Updated: November 2025*  
*Version: 2.0.0 - Triple-Source Edition*
