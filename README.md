# 🌞 Advanced Sunsynk Home Assistant Dashboard

A comprehensive, feature-rich Home Assistant dashboard for Sunsynk/Deye inverters with advanced monitoring, analytics, and system programming capabilities.

![Dashboard Preview](https://img.shields.io/badge/Dashboard-Ready-brightgreen) ![Home Assistant](https://img.shields.io/badge/Home%20Assistant-Compatible-blue) ![Maintenance](https://img.shields.io/badge/Maintained-Yes-green)

## ✨ Features

### 🏠 Core Monitoring
- **Real-time Power Flow**: Live solar, battery, grid, and load monitoring
- **Energy Analytics**: Daily, weekly, and monthly energy tracking
- **System Status**: Comprehensive inverter and component health monitoring
- **Temperature Monitoring**: Multi-point temperature tracking with alerts

### ⏰ Advanced System Programming (Steps 11-13)
- **System Timer Programming**: Visual 6-slot programming interface with real-time status
- **Individual Appliance Monitoring**: Dedicated tracking for pool pump, geyser, and AC units
- **Monthly Analytics**: 6-month trend analysis with advanced filtering
- **Financial Dashboard**: ROI calculations, cost analysis, and savings projections

### 📊 Data Visualization
- **Plotly Graphs**: Interactive real-time and historical data visualization
- **Pie Charts**: Energy source and consumption breakdowns
- **Efficiency Analytics**: System performance metrics and optimization insights
- **Responsive Design**: Mobile-friendly layout with multiple breakpoints

### 💰 Financial Tracking
- **Cost Analysis**: Real-time grid cost tracking and solar value calculations
- **ROI Monitoring**: Investment payback period and long-term savings projections
- **Monthly Projections**: Automated financial forecasting
- **Savings Reports**: Daily, monthly, and annual savings summaries

## 📁 Project Structure

```
Sunsync/
├── README.md                                      # Project documentation
├── working configs/                               # Dashboard configurations
│   ├── step1-with-plotly.yaml                   # Basic plotly implementation
│   ├── step2-two-plotly.yaml                    # Dual plotly graphs
│   ├── step3-with-flex.yaml                     # Flex horseshoe cards
│   ├── step4-two-flex.yaml                      # Multiple flex cards
│   ├── step5-with-battery.yaml                  # Battery monitoring
│   ├── step6-with-solar-forecast.yaml           # Solar forecasting
│   ├── step7-with-pie-charts.yaml               # Energy pie charts
│   ├── step8-with-temperature-monitoring.yaml    # Temperature tracking
│   ├── step9-with-system-efficiency-analytics.yaml # Efficiency analytics
│   ├── step10-with-financial-dashboard.yaml      # Financial tracking
│   ├── step11-13-comprehensive-enhancement.yaml  # Complete feature set ⭐
│   └── home.yaml                                 # Production configuration
└── Templates/                                    # Template configurations
    ├── Dashboard.yaml                            # Template dashboard
    └── ESPHome-1P-Sunsynk-Deye.yaml            # ESPHome configuration
```

## 🚀 Quick Start

### Prerequisites
- Home Assistant with ESPHome integration
- Sunsynk/Deye inverter with Modbus communication
- Required HACS integrations and cards (see Installation section)

### Required HACS Cards:

- [Flexible Horseshoe Card](https://github.com/AmoebeLabs/flex-horseshoe-card)
- [Sunsynk Power Flow Card](https://github.com/slipx06/Sunsynk-Home-Assistant-Power-Flow-Card)
- [Layout Card](https://github.com/thomasloven/lovelace-layout-card)
- [Plotly Graph Card](https://github.com/dbuezas/lovelace-plotly-graph-card)

### Required Integrations:
- [Load Shedding](https://github.com/wernerhp/ha.integration.load_shedding)
- [Solcast Solar Forecast](https://github.com/rany2/ha-open-meteo-solar-forecast)

## 🎯 Dashboard Evolution

### Progressive Enhancement Steps:

| Step | Configuration File | Features Added |
|------|-------------------|----------------|
| **1** | `step1-with-plotly.yaml` | Basic Sunsynk card + single plotly graph |
| **2** | `step2-two-plotly.yaml` | Dual plotly graphs layout |
| **3** | `step3-with-flex.yaml` | Flex horseshoe cards integration |
| **4** | `step4-two-flex.yaml` | Multiple flex cards layout |
| **5** | `step5-with-battery.yaml` | Battery monitoring |
| **6** | `step6-with-solar-forecast.yaml` | Solar forecasting |
| **7** | `step7-with-pie-charts.yaml` | Energy pie charts |
| **8** | `step8-with-temperature-monitoring.yaml` | Temperature tracking |
| **9** | `step9-with-system-efficiency-analytics.yaml` | Efficiency analytics |
| **10** | `step10-with-financial-dashboard.yaml` | Financial tracking |
| **11-13** | `step11-13-comprehensive-enhancement.yaml` | ⭐ **Complete Feature Set** |

### Step 11-13 Complete Enhancement Features:
- **Step 11**: System Timer Programming with 6-slot visual interface
- **Step 12**: Individual Appliance Monitoring (pool, geyser, AC)
- **Step 13**: Monthly Analytics with 6-month trend analysis
- **Advanced Layout**: 10-column responsive grid system
- **Enhanced Monitoring**: Comprehensive system oversight

## 📱 Responsive Design

The dashboard includes three responsive breakpoints:

- **Desktop** (>1300px): 10-column advanced grid layout
- **Tablet** (800-1300px): 3-column optimized layout  
- **Mobile** (<800px): Single-column stacked layout

## 🔧 System Requirements

### Hardware Requirements:
- Sunsynk/Deye single-phase inverter
- ESP32/ESP8266 for Modbus communication (see hardware guide below)
- Home Assistant server (minimum 4GB RAM recommended)

### Software Dependencies:
- Home Assistant 2024.1+
- ESPHome integration
- HACS (Home Assistant Community Store)

## Screenshots


![image](https://github.com/user-attachments/assets/49c5b645-4472-440e-aeb9-4a99f3158974)
![image](https://github.com/user-attachments/assets/a3ed68f1-3a4d-4dd8-9c04-0dd1a604eb11)
![image](https://github.com/user-attachments/assets/fc85912b-46c4-4f8c-a17d-a5119e9cf619)
![image](https://github.com/user-attachments/assets/bc98f175-a63c-4287-b395-f2df76c6df9a)


## Installation
Data can be collected from the inverter using the RS485 port. There are a number of different ways to do this but I'm using an ESP32 chip running ESPHome. See **Hardware and Wiring Guide** below and [ESPHome-1P-Sunsynk-Deye.yaml](https://github.com/slipx06/Sunsynk-Home-Assistant-Dash/blob/main/ESPHome-1P-Sunsynk-Deye.yaml)

Create a new view on your current Dashboard and set the view type to Panel (1 card) as shown below:

![image](https://user-images.githubusercontent.com/7227275/223527428-b4508e6c-cf2d-473a-b63c-ffad11d2630d.png)


You can then edit the Dashboard (using the code editor) and paste the contents of the Dashboard.
You'll need to adjust all the sensor names to match yours and install the necessary custom components. 

## Demo

![layout_card](https://github.com/user-attachments/assets/f44a7c36-72dc-47ae-bf40-84419f4b3dfc)

## Hardware and Wiring Guide

> Disclaimer: Proceed with caution. Working with electrical equipment carries inherent risks. If you are unsure about any step, consult a qualified professional. The author is not responsible for any damage to equipment or injury. ALWAYS consult your specific inverter's manual and VERIFY ALL voltages and polarities with a multimeter before making connections.

### Required Components & Tools:

 - ESP-based board (e.g., [AtomS3 Lite M5 Stack](https://shop.m5stack.com/products/atoms3-lite-esp32s3-dev-kit))
 - RS485 to TTL Converter (e.g., [M5Stack Tail485](https://shop.m5stack.com/products/atom-tail485), which accepts 12V)
 - Standard Ethernet Patch Cable (Cat5e or Cat6)
 - Tools: Wire strippers, wire cutters, small screwdriver (for terminal blocks), multimeter (essential for voltage/polarity checks).

### Powering Your ESP Board & RS485 Converter:

 - The M5Stack AtomS3 Lite with Tail485 converter example accepts 12V input.
 - Many inverters provide an onboard 12V DC power source.
 - Consult your inverter's manual to locate a suitable 12V DC output and its Ground (GND) terminal. BEFORE CONNECTING ANYTHING: Use a multimeter to verify the output is indeed 12V DC (or the voltage your converter expects). Confirm the correct polarity of the 12V (+) and GND (-) terminals. Incorrect voltage or polarity can permanently damage your components.

### Preparing the Ethernet Cable for RS485 Data:

 - Connect one end of the Ethernet cable to your inverter's RS485 port (this might be labeled RS485, BMS, Meter, etc. – check your manual).
 - Consult your inverter's manual to identify which pins on its port correspond to RS485 A+, RS485 B- as well as the pins for +12V (or other voltage) and GND. Note these down.
 - Carefully cut off the connector from the other end of the Ethernet cable.
 - Strip back about 1-2 inches (2-5 cm) of the outer jacket to expose the 4 twisted pairs of wires.
 - Using a standard Ethernet cable pinout diagram (e.g., T568B, easily found online) and the pin information from your inverter's manual, identify the colored wires that correspond to your inverter's RS485 A+, RS485 B- signals.

### Connecting to the RS485 Converter (e.g., Tail485):
 - Connect the wire you identified as RS485 A+ (from the Ethernet cable) to the 'A' (or 'A+') terminal on your RS485 converter.
 - Connect the wire you identified as RS485 B- (from the Ethernet cable) to the 'B' (or 'B-') terminal on your RS485 converter.
 - Connect dedicated wires from the inverter's verified 12V and GND terminals to the VIN and GND of the RS485 converter.

### Example Wiring: Solark 15K Inverter

Pinout

![image](https://github.com/user-attachments/assets/539d831b-27da-40ab-a908-aa70a9f9d1f1)

![image](https://github.com/user-attachments/assets/579cb6e6-b261-4e1f-99ed-fc28e4fc7737)

From the above picture, port 15 goes to the 12V port on the tail485, while port 16 goes to the Gnd.

![InverterWiringDiagram](https://github.com/user-attachments/assets/44aa39ba-df9d-460b-af20-b9518f267d64)

## Additional Info
Added remaining battery time. You will need to add the following template sensor

```
- platform: template
  sensors:
    battery_cap:
      friendly_name: "Battery Capacity"
      value_template: >
        {% set grid_online = states('binary_sensor.sunsynk_grid_connected_status') %}
        {% if grid_online  == 'off'%}
          {{ states('sensor.sunsynk_battery_capacity_shutdown') | int }}
        {% else %}
          {% set now = strptime(as_timestamp(now()) | timestamp_custom('%H:%M'), '%H:%M') %}
          {% set sellTime1 = strptime(states('sensor.sunsynk_time_slot_1'), '%H:%M') %}
          {% set sellTime2 = strptime(states('sensor.sunsynk_time_slot_2'), '%H:%M') %}
          {% set sellTime3 = strptime(states('sensor.sunsynk_time_slot_3'), '%H:%M') %}
          {% set sellTime4 = strptime(states('sensor.sunsynk_time_slot_4'), '%H:%M') %}
          {% set sellTime5 = strptime(states('sensor.sunsynk_time_slot_5'), '%H:%M') %}
          {% set sellTime6 = strptime(states('sensor.sunsynk_time_slot_6'), '%H:%M') %}
          {% if now >= sellTime1 and now < sellTime2 %}
            {{ states('number.sunsynk_prog1_capacity') | int }}
          {% elif now >= sellTime2 and now < sellTime3 %}
            {{ states('number.sunsynk_prog2_capacity') | int }}
          {% elif now >= sellTime3 and now < sellTime4 %}
            {{ states('number.sunsynk_prog3_capacity') | int }}
          {% elif now >= sellTime4 and now < sellTime5 %}
            {{ states('number.sunsynk_prog4_capacity') | int }}
          {% elif now >= sellTime5 and now < sellTime6 %}
            {{ states('number.sunsynk_prog5_capacity') | int }}
          {% elif now >= sellTime6 or now < sellTime1 %}
            {{ states('number.sunsynk_prog6_capacity') | int }}
          {% else %}
            {{ states('sensor.sunsynk_battery_capacity_shutdown') | int }}
          {% endif %}
        {% endif %}
    soc_battery_time_left:
      friendly_name: "Battery Depletion Seconds"
      unit_of_measurement: Seconds
      value_template: >
        {% set state = states('sensor.sunsynk_battery_power') | int %}
        {% set cap = states('sensor.battery_cap') | float %}
        {% if state == 0 -%}
        {{ ((((states('sensor.sunsynk_battery_soc') | float - cap) /100) * 15960) / (1) * 60 * 60 ) | timestamp_custom('%s', 0) }}
        {%- else -%}
        {{ ((((states('sensor.sunsynk_battery_soc') | float - cap) /100) * 15960) / (states('sensor.sunsynk_battery_power') | float) * 60 * 60 ) | timestamp_custom('%s', 0) }}
        {%- endif %}
    soc_battery_time_left_friendly:
      friendly_name: "Battery Depletion Time"
      value_template: >
        {% set state = states('sensor.sunsynk_battery_power') | int %}
        {% if state > 0 -%}
        {%- set time = states('sensor.soc_battery_time_left') | int %}
        {%- set minutes = ((time % 3600) // 60) %}
        {%- set minutes = '{} minutes'.format(minutes) if minutes > 0 else '' %}
        {%- set hours = ((time % 86400) // 3600) %}
        {%- set hours = '{} hours, '.format(hours) if hours > 0 else '' %}
        {%- set days = (time // 86400) %}
        {%- set days = '{} day, '.format(days) if days > 0 else '' %}
        {{ 'Less than 1 minute' if time < 60 else days + hours + minutes }}
        {%- else -%}
        {{ 'Charging' }}
        {%- endif %}
    battery_charging_time_left:
      friendly_name: "Battery Charging Time Left"
      unit_of_measurement: Seconds
      value_template: >
        {% set power = states('sensor.sunsynk_battery_power') | float %}
        {% set soc = states('sensor.sunsynk_battery_soc') | float %}
        {% set cap = states('sensor.battery_cap') | float %}
        {% if power < 0 %}
          {% if soc < cap %}
            {{ ((((cap - soc) / 100) * 15960) / (-power) * 60 * 60) | int }}
          {% else %}
            {{ ((((100 - soc) / 100) * 15960) / (-power) * 60 * 60) | int }}
          {% endif %}
        {% else %}
          0
        {% endif %}
    battery_charging_time_left_friendly:
      friendly_name: "Battery Charging Time"
      value_template: >
        {% set state = states('sensor.sunsynk_battery_power') | int %}
        {% if state < 0 -%}
          {%- set time = states('sensor.battery_charging_time_left') | int %}
          {%- set minutes = ((time % 3600) // 60) %}
          {%- set minutes = '{} min'.format(minutes) if minutes > 0 else '' %}
          {%- set hours = ((time % 86400) // 3600) %}
          {%- set hours = '{} hrs, '.format(hours) if hours > 0 else '' %}
          {%- set days = (time // 86400) %}
          {%- set days = '{} day, '.format(days) if days > 0 else '' %}
          {{ 'Floating' if time < 60 else days + hours + minutes }}
        {%- else -%}
          {{ 'Discharging' }}
        {%- endif %}
    markdown_battery_charge_time_left:
      friendly_name: "Markdown Battery Charging Time"
      value_template: >
        {% if states('sensor.sunsynk_battery_soc') | float < states('sensor.battery_cap') | float %}
          {{ states('sensor.battery_cap') | float | round(0) }}
        {% else %}
          100
          {% endif %}
    markdown_discharge_time:
      friendly_name: "Markdown Discharge Time"
      value_template: >
        {% set now = as_timestamp(now()) %}
        {% set add = states('sensor.soc_battery_time_left') | int %}
        {% set future_time = now + add %}
          {{ future_time | timestamp_custom('%H:%M') }}
    markdown_charge_time:
      friendly_name: "Markdown Charging Time"
      value_template: >
        {% set now = as_timestamp(now()) %}
        {% set add = states('sensor.battery_charging_time_left') | int %}
        {% set future_time = now + add %}
          {{ future_time | timestamp_custom('%H:%M') }}
```
15960 is battery size in Wh. You will need to adjust for your system

20 is the minimum battery SOC before shutdown

## Change Inverter Settings
These following example cards can be used to set system timer settings

### Example 1

![image](https://github.com/slipx06/Sunsynk-Home-Assistant-Dash/assets/7227275/2c665082-1d12-4a26-ba19-def6ffdd7780)

```
type: vertical-stack
cards:
  - type: tile
    entity: switch.sunsynk_toggle_system_timer
    icon: mdi:timer-outline
    vertical: true
  - type: horizontal-stack
    cards:
      - type: entities
        entities:
          - entity: select.sunsynk_energy_pattern
            name: Energy Pattern
        state_color: true
      - type: entities
        entities:
          - entity: select.sunsynk_work_mode
            name: Work Mode
        state_color: true
  - type: entities
    entities:
      - entity: switch.sunsynk_prog1_grid_charge
        type: custom:multiple-entity-row
        name: Program 1
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_time_slot_1
            name: From
          - entity: sensor.sunsynk_time_slot_2
            name: To
          - entity: number.sunsynk_prog1_capacity
            name: SOC
            format: precision0
      - entity: switch.sunsynk_prog2_grid_charge
        type: custom:multiple-entity-row
        name: Program 2
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_time_slot_2
            name: From
          - entity: sensor.sunsynk_time_slot_3
            name: To
          - entity: number.sunsynk_prog2_capacity
            name: SOC
            format: precision0
      - entity: switch.sunsynk_prog3_grid_charge
        type: custom:multiple-entity-row
        name: Program 3
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_time_slot_3
            name: From
          - entity: sensor.sunsynk_time_slot_4
            name: To
          - entity: number.sunsynk_prog3_capacity
            name: SOC
            format: precision0
      - entity: switch.sunsynk_prog4_grid_charge
        type: custom:multiple-entity-row
        name: Program 4
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_time_slot_4
            name: From
          - entity: sensor.sunsynk_time_slot_5
            name: To
          - entity: number.sunsynk_prog4_capacity
            name: SOC
            format: precision0
      - entity: switch.sunsynk_prog5_grid_charge
        type: custom:multiple-entity-row
        name: Program 5
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_time_slot_5
            name: From
          - entity: sensor.sunsynk_time_slot_6
            name: To
          - entity: number.sunsynk_prog5_capacity
            name: SOC
            format: precision0
      - entity: switch.sunsynk_prog6_grid_charge
        type: custom:multiple-entity-row
        name: Program 6
        toggle: true
        state_header: Charge
        state_color: true
        icon: mdi:timer
        entities:
          - entity: sensor.sunsynk_time_slot_6
            name: From
          - entity: sensor.sunsynk_time_slot_1
            name: To
          - entity: number.sunsynk_prog6_capacity
            name: SOC
            format: precision0
    state_color: true
view_layout:
  grid-area: a
```
### Example 2
![image](https://github.com/slipx06/Sunsynk-Home-Assistant-Dash/assets/7227275/ff40ea09-0aa3-4987-abb4-69fd195f5286)


```
type: custom:layout-card
layout_type: custom:grid-layout
cards:
  - type: custom:mushroom-title-card
    title: Sunsynk System Mode
    alignment: center
    view_layout:
      grid-area: header
  - type: horizontal-stack
    cards:
      - type: entities
        entities:
          - entity: switch.sunsynk_toggle_system_timer
            name: System Timer
        state_color: true
      - type: entities
        entities:
          - entity: select.sunsynk_energy_pattern
            name: Energy Pattern
        state_color: true
      - type: entities
        entities:
          - entity: select.sunsynk_work_mode
            name: Work Mode
        state_color: true
    view_layout:
      grid-area: system
  - type: vertical-stack
    cards:
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Program 1
            secondary: >-
              {{ states("sensor.sunsynk_time_slot_1") }} - {{
              states("sensor.sunsynk_time_slot_2") }}
            icon: mdi:timer
            multiline_secondary: false
            badge_icon: mdi:lightning-bolt
            icon_color: blue
            badge_color: green
            fill_container: true
          - type: entities
            entities:
              - entity: select.sunsynk_prog1_charge_option
                name: Option
            state_color: true
      - type: entities
        entities:
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog1_capacity
            name: Battery SOC
            hide_state: false
            grow: true
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog1_power
            name: Power
            hide_state: false
            grow: true
    view_layout:
      grid-area: prog1
  - type: vertical-stack
    cards:
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Program 2
            secondary: >-
              {{ states("sensor.sunsynk_time_slot_2") }} - {{
              states("sensor.sunsynk_time_slot_3") }}
            icon: mdi:timer
            multiline_secondary: false
            badge_icon: mdi:lightning-bolt
            icon_color: blue
            badge_color: green
            fill_container: true
          - type: entities
            entities:
              - entity: select.sunsynk_prog2_charge_option
                name: Option
            state_color: true
      - type: entities
        entities:
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog2_capacity
            name: Battery SOC
            hide_state: false
            grow: true
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog2_power
            name: Power
            hide_state: false
            grow: true
    view_layout:
      grid-area: prog2
  - type: vertical-stack
    cards:
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Program 3
            secondary: >-
              {{ states("sensor.sunsynk_time_slot_3") }} - {{
              states("sensor.sunsynk_time_slot_4") }}
            icon: mdi:timer
            multiline_secondary: false
            badge_icon: mdi:lightning-bolt
            icon_color: blue
            badge_color: green
            fill_container: true
          - type: entities
            entities:
              - entity: select.sunsynk_prog3_charge_option
                name: Option
            state_color: true
      - type: entities
        entities:
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog3_capacity
            name: Battery SOC
            hide_state: false
            grow: true
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog3_power
            name: Power
            hide_state: false
            grow: true
    view_layout:
      grid-area: prog3
  - type: vertical-stack
    cards:
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Program 4
            secondary: >-
              {{ states("sensor.sunsynk_time_slot_4") }} - {{
              states("sensor.sunsynk_time_slot_5") }}
            icon: mdi:timer
            multiline_secondary: false
            badge_icon: mdi:lightning-bolt
            icon_color: blue
            badge_color: green
            fill_container: true
          - type: entities
            entities:
              - entity: select.sunsynk_prog4_charge_option
                name: Option
            state_color: true
      - type: entities
        entities:
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog4_capacity
            name: Battery SOC
            hide_state: false
            grow: true
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog4_power
            name: Power
            hide_state: false
            grow: true
    view_layout:
      grid-area: prog4
  - type: vertical-stack
    cards:
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Program 5
            secondary: >-
              {{ states("sensor.sunsynk_time_slot_5") }} - {{
              states("sensor.sunsynk_time_slot_6") }}
            icon: mdi:timer
            multiline_secondary: false
            badge_icon: mdi:lightning-bolt
            icon_color: blue
            badge_color: green
            fill_container: true
          - type: entities
            entities:
              - entity: select.sunsynk_prog5_charge_option
                name: Option
            state_color: true
      - type: entities
        entities:
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog5_capacity
            name: Battery SOC
            hide_state: false
            grow: true
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog5_power
            name: Power
            hide_state: false
            grow: true
    view_layout:
      grid-area: prog5
  - type: vertical-stack
    cards:
      - type: horizontal-stack
        cards:
          - type: custom:mushroom-template-card
            primary: Program 6
            secondary: >-
              {{ states("sensor.sunsynk_time_slot_6") }} - {{
              states("sensor.sunsynk_time_slot_1") }}
            icon: mdi:timer
            multiline_secondary: false
            badge_icon: mdi:lightning-bolt
            icon_color: blue
            badge_color: green
            fill_container: true
          - type: entities
            entities:
              - entity: select.sunsynk_prog6_charge_option
                name: Option
            state_color: true
      - type: entities
        entities:
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog6_capacity
            name: Battery SOC
            hide_state: false
            grow: true
          - type: custom:slider-entity-row
            entity: number.sunsynk_prog6_power
            name: Power
            hide_state: false
            grow: true
    view_layout:
      grid-area: prog6
layout:
  grid-template-columns: 2fr 2fr 2fr 2fr
  grid-template-rows: auto
  grid-template-areas: |
    ". header header ."
    ". system system ."
    ". prog1 prog2 ."
    ". prog3 prog4 ."
    ". prog5 prog6 ."
  mediaquery:
    '(max-width: 800px)':
      grid-template-columns: auto
      grid-template-areas: |
        "header"
        "system"
        "priority"
        "prog1"
        "prog2"
        "prog3"
        "prog4"
        "prog5"
        "prog6"
```

