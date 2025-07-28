# 📄 Multi-Page Sunsynk Dashboard Guide

This guide explains how to break down your comprehensive Sunsynk dashboard into organized subpages for better navigation and performance.

## 🎯 Dashboard Structure Overview

The multi-page structure organizes your Sunsynk system into logical sections:

### 📋 Page Breakdown

| Page | Path | Purpose | Key Features |
|------|------|---------|--------------|
| **Overview** | `/overview` | Main system status | Power flow, live data, daily summary |
| **Analytics** | `/analytics` | Energy analysis | Historical data, pie charts, efficiency |
| **Programming** | `/programming` | System timer settings | 6-slot programming, schedule visualization |
| **Appliances** | `/appliances` | Individual device monitoring | Pool, geyser, AC tracking |
| **Financial** | `/financial` | Cost analysis & ROI | Savings, projections, payback period |
| **System Health** | `/system-health` | Temperature & diagnostics | Alerts, maintenance, system status |

## 🚀 Implementation Steps

### Step 1: Create New Dashboard

1. In Home Assistant, go to **Settings** → **Dashboards**
2. Click **+ ADD DASHBOARD**
3. Choose **Create new dashboard**
4. Set **Title**: `Sunsynk Solar System`
5. Set **URL**: `sunsynk-solar` ⚠️ **Must contain a hyphen (-)**
6. Set **Icon**: `mdi:solar-power`
7. **Save**

### Step 2: Configure Dashboard Structure

1. Go to your new dashboard
2. Click the **pencil icon** (Edit Dashboard)
3. Click **⋮** (three dots) → **Raw Configuration Editor**
4. **Delete all existing content**
5. **Copy and paste** the content from `multi-page-dashboard.yaml`
6. **Save**

### Step 3: Update Entity Names

⚠️ **Important**: You'll need to replace all entity names with your specific sensor names.

**Find and replace these prefixes:**
- `deye_home_sunsynk_` → `your_inverter_prefix_`
- `sensor.borehole_switch_` → `sensor.your_pool_pump_`
- `sensor.water_pump_` → `sensor.your_geyser_`
- `sensor.ac_switch_` → `sensor.your_ac_`

**Example entity mapping:**
```yaml
# Replace:
sensor.deye_home_sunsynk_solar_power
# With your entity:
sensor.sunsynk_solar_power
```

### Step 4: Navigation Setup

The dashboard creates a tab-based navigation:
- **Overview** - Main landing page
- **Analytics** - Data analysis
- **Programming** - Timer settings
- **Appliances** - Device monitoring
- **Financial** - Cost tracking
- **System Health** - Diagnostics

## 📱 Mobile Responsiveness

Each page includes responsive layout configurations:

```yaml
layout:
  grid-template-columns: 1fr 1fr 1fr
  # Mobile breakpoint
  mediaquery:
    '(max-width: 800px)':
      grid-template-columns: auto
      grid-template-areas: |
        "card1"
        "card2"
        "card3"
```

## 🎨 Customization Options

### Changing Page Icons

Update the `icon` field for each view:
```yaml
- title: Analytics
  icon: mdi:chart-line  # Change this icon
```

### Adding New Pages

To add a new page:
```yaml
- title: New Page
  path: new-page
  icon: mdi:new-icon
  type: custom:layout-card
  layout_type: custom:grid-layout
  cards:
    - type: your-card-type
```

### Modifying Grid Layouts

Adjust the grid structure:
```yaml
layout:
  grid-template-columns: 1fr 2fr 1fr  # Change column ratios
  grid-template-areas: |
    "sidebar main info"     # Customize layout areas
    "sidebar main info"
```

## 🔧 Required HACS Cards

Ensure these are installed:
- **Layout Card**: `thomasloven/lovelace-layout-card`
- **Plotly Graph**: `dbuezas/lovelace-plotly-graph-card`
- **Mushroom Cards**: `piitaya/lovelace-mushroom`
- **Flex Horseshoe**: `AmoebeLabs/flex-horseshoe-card`
- **Sunsynk Power Flow**: `slipx06/Sunsynk-Home-Assistant-Power-Flow-Card`

## 📊 Page-Specific Features

### Overview Page
- Real-time power flow visualization
- Live power graphs with 6-hour history
- Daily energy summary cards
- Key system metrics

### Analytics Page
- 7-day daily energy bar charts
- 30-day trend analysis
- Energy source pie charts
- System efficiency metrics

### Programming Page
- Visual 6-slot timer interface
- Color-coded program status
- SOC target settings
- 24-hour schedule visualization

### Appliances Page
- Individual device monitoring
- 7-day energy consumption
- Power status indicators
- Monthly comparison charts

### Financial Page
- Daily cost/savings calculations
- Monthly projections
- ROI analysis with payback period
- 6-month financial performance

### System Health Page
- Temperature monitoring graphs
- System status indicators
- Alert notifications
- Maintenance reminders

## 🚨 Troubleshooting

### Common Issues

1. **Dashboard URL Error**: URL path must contain a hyphen (-). Use `sunsynk-solar` not `sunsynk`
2. **Blank Pages**: Check entity names match your system
3. **Missing Cards**: Verify HACS cards are installed
4. **Layout Issues**: Check grid template syntax
5. **No Data**: Confirm sensors are available and recording

### Entity Validation

Test entities in **Developer Tools** → **States**:
```yaml
# Check if entity exists
sensor.your_solar_power
sensor.your_battery_soc
```

### Performance Tips

- Each page loads independently (better performance)
- Remove unused cards to reduce load time
- Use `hours_to_show` limits on graphs
- Consider entity availability for conditionals

## 📈 Benefits of Multi-Page Structure

1. **Improved Performance**: Pages load faster with fewer cards
2. **Better Organization**: Logical grouping of related functions
3. **Mobile Friendly**: Easier navigation on tablets/phones
4. **Maintenance**: Easier to update specific sections
5. **User Experience**: Cleaner, more focused interface
6. **Scalability**: Easy to add new pages as needed

## 🔄 Migration from Single Page

If migrating from a single large dashboard:

1. **Backup** your existing dashboard configuration
2. **Identify** which cards belong to which logical section
3. **Copy** relevant cards to appropriate pages
4. **Test** each page individually
5. **Verify** all entity names are correct
6. **Update** bookmarks to new page URLs

## 📝 Next Steps

After implementation:
1. Test all pages on different screen sizes
2. Customize colors and themes to match your preference
3. Add or remove cards based on your specific needs
4. Consider adding automation triggers for alerts
5. Set up notifications for system health issues

This multi-page structure provides a professional, scalable foundation for your Sunsynk monitoring system while maintaining all the advanced features from your comprehensive dashboard.
