# Harvest-Overseer 🪴
>Built for third space Hack Club! - Week 1  
_It all began when two unemployed dudes found another dude-man that was also unemployed, together they set their trails ablaze, conquering both land and sea. Day and night they worked towards their goal, will they make it? Only fate can tell._

A stationary, comprehensive agricultural monitor that measures soil pH, moisture levels, nutrient concentrations (NPK), and light intensity. It displays the data of the plant and soil's health on an OLED screen to let you easily know what your plant needs.

## 🔴Project Overview🔴
**Harvest-Overseer** is an all-in-one agricultural monitor designed to take the guesswork out of plant care. Stationed directly in your garden bed or potted plant, it continuously tracks essential environmental and soil parameters -- displaying real-time health diagnostics on an integrated OLED screen so you always know exactly what your plants need to thrive.

### 🗝️Key Features
🥖**Soil pH & Nutrients Tracking:** Monitors pH balance and NPK (_Nitrogen, Phosphorus, Potassium_) concentrations.\
💧**Moisture Detection:** Measures active soil hydration levels to prevent over or under-watering.\
☀️**Light Intensity:** Tracks daily ambient light exposures to ensure optimal photosynthesis conditions.\
👁️**One-Glance Display:** Instant visual updates through a _7 pin SPI lcd_.\
🔋**Battery Powered:** Fully portable design powered by a rechargeable Li-ion battery with integrated power management.

## 🍰PCB & Hardware Architecture🥯
The custom PCB was designed to handle low-power battery operation and reliable SPI sensor communication in a compact form factor.\
+ <ins>**The BRAIN**</ins> ESP32-S3-WROOM-1-N16R8\
+ <ins>**The FACE**</ins> 14-pin socket (Conn_01x14_Socket) featuring dedicated connections for a 7-Pin SPI OLED Display (SDO,LED,SCK,SDI,DC/RS,RESET,CS)\
+ <ins>**The HEART**</ins> TP4056充电源模块板 or TP4056 charging power module board\

