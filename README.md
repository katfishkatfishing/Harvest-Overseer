# Harvest-Overseer 🌱
>Built for third space Hack Club! - Week 1️⃣  
_It all started when two unemployed dudes stumbled upon a third, equally unemployed dude. Unburdened by 9-to-5s (erm but we have 9-5s for school) and fuelled by sheer ambition, the trio set off to blaze new trails, conquering land, sea, and hardware. Day and night they grind towards their goal — will they pull it off? Only fate can tell._

A stationary, comprehensive agricultural monitor that measures soil pH, moisture levels, nutrient concentrations (NPK), and light intensity. It displays the data of the plant and soil's health on an OLED screen to let you easily know what your plant needs.

## 💠 Project Overview 💠
**Harvest-Overseer** is an all-in-one agricultural monitor designed to take the guesswork out of plant care. Stationed directly in your garden bed or potted plant, it will continuously track essential environmental and soil parameters — displaying real-time health diagnostics on an integrated OLED screen so you always know exactly what your plants need to thrive.

### Key Features 🗝️
🥖**Soil pH & Nutrients Tracking:** Monitors pH balance and NPK (_Nitrogen, Phosphorus, Potassium_) concentrations.\
💧**Moisture Detection:** Measures active soil hydration levels to prevent over or under-watering.\
☀️**Light Intensity:** Tracks daily ambient light exposures to ensure optimal photosynthesis conditions.\
👁️**One-Glance Display:** Instant visual updates through a 7-pin SPI lcd.\
🔋**Battery Powered:** Fully portable design powered by a rechargeable Li-ion battery with integrated power management.  

## 🍰 PCB & Hardware Architecture 🥯
Harvest-Overseer uses a modular architecture consisting of a central **Master Unit (Main Brain)** for processing and display, and one or more remote **Sensor Node(s)** designed for low-power battery operation.
### Master Unit — The Core 🍎
The Master Unit receives sensor data, handles system logic, and drives the local OLED status display.
+ <ins>**The BRAIN**</ins>🧠 **ESP32-S3-WROOM-1-N16R8** to handle calculations, sensor input processing, and screen rendering.
+ <ins>**The FACE**</ins>🥶 14-pin socket (Conn_01x14_Socket) featuring dedicated connections for a **7-Pin SPI lcd** (_SDO, LED, SCK, SDI, DC/RS, RESET, CS_)
+ <ins>**The HEART**</ins>🫀 An  integrated footprint of **TP4056充电源模块板** or **TP4056 charging power module board** for safe USB-C power delivery and Li-ion battery charging, and a **TPS7133Q** (a low dropout voltage regulator) that converts 4.2V to 3.3V for a clean and stable voltage rail for the ESP32-S3 and other sensitive logic pins.

### Sensor Node — The Limbs or something 🐙
The Sensor Node is an autonomous, ultra-low-power unit stationed in the soil bed to read pH, moisture, light, and NPK levels, transmitting readings wirelessly back to the Core.

#### Components & Silicon 💎
+ <ins>**The BRAIN_1**</ins> **ESP32-C3-WROOM-02** (compact RISC-V Wi-Fi/BLE MCU) for reading sensors and beaming data to the Main Brain
+ <ins>**Power Management Thing**</ins> **MCP73871-2CC**, an advanced LiPo/Li-ion charge manager with automatic power path management, allowing simultaneous solar/USB power supply and battery charging.
+ <ins>**A Timer**</ins> **TPL5110**, a nano-power system timer that completely cuts power to the entire node until a scheduled wake interval, drastically reducing standby drain to nano-amps for a long-term outdoor deployment.
+ <ins>**Another High-Efficiency Power Management Thing**</ins>, the **DMG3415U** (P-Channel MOSFET) used to physically power down high-draw soil sensors when the node is sleeping.
+ <ins>**Voltage Regulation (LDO)**</ins> **HT7333** (Low quiescent current 3.3V regulator for logic and sensor rails)

#### Connectors & Peripherals 🖇️
+ <ins>**USB-C Interface**</ins> a **USB4085** GCT 16-pin USB-C receptacle is used for charging.
+ <ins>**Sensor Terminal Blocks**</ins> **WAGO 233 Series**, a tool-less spring-cage terminals (2x08 and 2x04) for easy wiring of soil sensors (pH, NPK, moisture, light)
+ <ins>**Some random button and stuff (unsure of its usage)** `B3U-1000P` tactile switch, `0603` status LEDs, filtering capacitors, and precision SMD resistor networks.