# 🔧 Dashboard Troubleshooting Guide

## 🚨 Common Dashboard Errors & Fixes

### 1. **Sunsynk Power Flow Card Errors**

**Error**: `Please include the attribute and entity ID e.g: pv1_power_186: sensor.example`

**Solution**: The Sunsynk card requires specific entity mappings. Here's the complete list:

```yaml
entities:
  # Essential Power Flow
  solar_power: sensor.deye_home_sunsynk_solar_power
  battery_soc_184: sensor.deye_home_sunsynk_battery_soc
  battery_power_190: sensor.deye_home_sunsynk_battery_power
  grid_power_169: sensor.deye_home_sunsynk_grid_power
  essential_power: sensor.deye_home_sunsynk_essential_power_1
  
  # PV Strings (required for 3 MPPT setup)
  pv1_power_186: sensor.deye_home_sunsynk_pv1_power
  pv2_power_187: sensor.deye_home_sunsynk_pv2_power
  pv3_power_188: sensor.deye_home_sunsynk_pv3_power
  pv1_voltage_109: sensor.deye_home_sunsynk_pv1_voltage
  pv2_voltage_110: sensor.deye_home_sunsynk_pv2_voltage
  pv3_voltage_111: sensor.deye_home_sunsynk_pv3_voltage
  
  # Battery Details
  battery_voltage_183: sensor.deye_home_sunsynk_battery_voltage
  battery_current_191: sensor.deye_home_sunsynk_battery_current
  battery_temperature_182: sensor.deye_home_sunsynk_battery_temperature
  
  # Grid & System
  grid_connected_status_194: binary_sensor.deye_home_sunsynk_grid_connected_status
  inverter_voltage_154: sensor.deye_home_sunsynk_inverter_voltage
  load_frequency_192: sensor.deye_home_sunsynk_load_frequency
  inverter_current_164: sensor.deye_home_sunsynk_inverter_current
  
  # Temperature Monitoring
  dc_transformer_temperature_90: sensor.deye_home_sunsynk_dc_transformer_temperature
  radiator_temperature_91: sensor.deye_home_sunsynk_radiator_temperature
  
  # Daily Energy
  day_battery_charge_70: sensor.deye_home_sunsynk_day_battery_charge
  day_battery_discharge_71: sensor.deye_home_sunsynk_day_battery_discharge
  day_load_energy_84: sensor.deye_home_sunsynk_day_load_energy
  day_grid_import_76: sensor.deye_home_sunsynk_day_grid_import
  day_pv_energy_108: sensor.deye_home_sunsynk_day_pv_energy
  
  # System Controls
  use_timer_248: switch.deye_home_sunsynk_toggle_system_timer
  priority_load_243: switch.deye_home_sunsynk_toggle_priority_load
```

### 2. **Flex Horseshoe Card Errors**

**Error**: `No layout defined`

**Solution**: All flex-horseshoe-cards need a layout definition:

```yaml
- type: custom:flex-horseshoe-card
  layout:
    hlines:
      - id: 0
        xpos: 50
        ypos: 42
        length: 40
      - id: 1
        xpos: 50
        ypos: 50
        length: 40
  entities:
    - entity: sensor.your_entity
      name: Display Name
```

### 3. **Plotly Graph Card Errors**

**Error**: `Card didn't load` / `waiting for loading`

**Solutions**:
1. **Simplify the configuration**:
```yaml
- type: custom:plotly-graph
  title: Simple Graph
  entities:
    - entity: sensor.deye_home_sunsynk_solar_power
      name: Solar
      line:
        color: rgb(255, 155, 48)
  hours_to_show: 6
  layout:
    height: 300
```

2. **Remove complex functions**:
   - Avoid `$fn` functions initially
   - Remove complex transforms
   - Start with basic line graphs

3. **Check entity availability**:
   - Verify entities exist in Developer Tools → States
   - Ensure entities have data history

### 4. **Mushroom Card Conflicts**

**Error**: `the name "mushroom-select" has already been used`

**Solutions**:
1. **Use standard entity cards instead**:
```yaml
- type: entity
  entity: sensor.your_entity
  name: Display Name
  icon: mdi:your-icon
```

2. **Or use simple template cards**:
```yaml
- type: custom:template-entity-row
  name: "Display Name"
  state: "{{ states('sensor.your_entity') }}"
  icon: mdi:your-icon
```

### 5. **Layout Card Issues**

**Error**: Grid template errors

**Solution**: Use simpler layouts:
```yaml
type: custom:layout-card
layout_type: custom:grid-layout
layout:
  grid-template-columns: 1fr 1fr 1fr
  grid-template-areas: |
    "card1 card2 card3"
    "card4 card4 card4"
```

## 🔍 **Entity Validation Checklist**

Before using any entity, check:

1. **Developer Tools → States**:
   - Search for your entity
   - Verify it exists and has recent data
   - Check the state value format

2. **History**:
   - Go to History tab
   - Search for entity
   - Verify data is being recorded

3. **Entity naming**:
   - Replace `deye_home_sunsynk_` with your actual prefix
   - Check exact entity names in your system

## 🛠️ **Step-by-Step Debugging**

1. **Start Simple**:
   - Begin with basic entity cards
   - Add one complex card at a time
   - Test each addition

2. **Check Browser Console**:
   - Press F12 → Console tab
   - Look for red error messages
   - Fix errors one by one

3. **Test Individual Cards**:
   - Create a test dashboard
   - Add one problematic card
   - Fix configuration until it works

## 📋 **Required HACS Installations**

Ensure these are properly installed:

```
thomasloven/lovelace-layout-card
dbuezas/lovelace-plotly-graph-card
AmoebeLabs/flex-horseshoe-card
slipx06/sunsynk-power-flow-card
piitaya/lovelace-mushroom (optional)
```

## 🔄 **Recovery Steps**

If dashboard is completely broken:

1. **Backup current config**
2. **Use the fixed configuration** (`deye-home-fixed-dashboard.yaml`)
3. **Replace entity names** with your actual entities
4. **Test page by page**
5. **Add complexity gradually**

## ⚡ **Quick Fix Summary**

- ✅ **Use fixed configuration** with complete entity mappings
- ✅ **Add layout definitions** to all flex-horseshoe cards
- ✅ **Simplify plotly graphs** initially
- ✅ **Replace mushroom cards** with entity cards if conflicts occur
- ✅ **Verify all entities** exist in your system
- ✅ **Test incrementally** rather than implementing everything at once

The fixed configuration should eliminate most common errors and provide a stable foundation for your multi-page dashboard.
