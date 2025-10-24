# Blood Fibrinogen Tracker

A web-based application for tracking and modeling blood fibrinogen levels during obstetric hemorrhage management, particularly designed for term pregnancy cases.

## Overview

This tool helps clinicians visualize and track fibrinogen levels, blood volume, and blood loss during active hemorrhage management. It models the effects of various blood products on fibrinogen concentration and provides real-time visualization of these changes.

## Features

- **Initial Assessment**: Input initial fibrinogen levels, measured blood loss, and body weight
- **Real-time Tracking**: Visual graph showing fibrinogen concentration, blood volume, and cumulative blood loss
- **Blood Product Administration**: Track the effects of:
  - Fresh Frozen Plasma (FFP)
  - Cryoprecipitate
  - Fibrinogen Concentrate
  - Red Blood Cells (RBC)
- **Product Tally**: Keep count of all products administered
- **Intervention Timeline**: Track up to 30 interventions on a fixed timeline

## How to Use

### Initial Setup

1. Enter the **Initial Clauss Fibrinogen** level (g/L) - Range: 0.3-10
2. Enter the **Measured Blood Loss** (ml) - Range: 0-20000
3. Enter the **Body Weight** (kg) - Range: 30-200
4. Click **Confirm** to proceed to the tracking interface

### During Management

- Click the product buttons to administer:
  - **FFP**: 250ml volume, adds 0.625g fibrinogen
  - **Cryoprecipitate**: 100ml volume, adds 1.25g fibrinogen
  - **Fibrinogen Concentrate**: 50ml volume, adds 1.0g fibrinogen
  - **Red Blood Cells**: 300ml volume (100ml plasma, 200ml cells), no fibrinogen

- Enter **Additional Measured Blood Loss** and click **Add** to update blood loss
- Click **Start Again** to reset and begin a new case

## Clinical Calculations

### Blood Volume
- Total blood volume estimated at **100ml/kg** (reflecting term pregnancy expansion)
- Initial blood loss is subtracted from the estimated blood volume
- Plasma volume is assumed to be **50%** of total blood volume

### Fibrinogen Distribution
- Fibrinogen distributes only in the plasma component
- When blood products are added:
  - Volume and fibrinogen mass are added to the system
  - New concentration = Total fibrinogen mass / Total plasma volume

### Blood Loss Effects
- Blood loss decreases total blood volume
- Plasma is lost proportionally (50% of blood loss)
- Fibrinogen is lost at the current concentration
- **Concentration remains constant** after blood loss (mass decreases proportionally)

### Product Specifications

| Product | Volume | Plasma Component | Fibrinogen Added |
|---------|--------|------------------|------------------|
| FFP | 250ml | 250ml | 0.625g |
| Cryoprecipitate | 100ml | 100ml | 1.25g |
| Fibrinogen Concentrate | 50ml | 50ml | 1.0g |
| Red Blood Cells | 300ml | 100ml | 0g |

## Graph Display

- **Left Y-axis**: Clauss Fibrinogen (0-12 g/L)
- **Right Y-axis**: Volume (0-20000 ml)
- **X-axis**: Intervention number (0-30)

Three lines are displayed:
- 🔴 Red: Fibrinogen concentration
- 🟣 Purple: Cumulative blood loss
- 🔵 Blue: Total blood volume

## Deployment

### GitHub Pages

1. Fork or clone this repository
2. Go to repository Settings → Pages
3. Select the main branch as the source
4. Your app will be available at `https://[username].github.io/fibrinogen-tracker`

### Local Deployment

Simply open `index.html` in any modern web browser. No server or dependencies required.

## Technical Details

- Pure HTML/CSS/JavaScript - no external dependencies
- Uses HTML5 Canvas for graph rendering
- Fully client-side - no data is sent to any server
- Works offline once loaded

## Browser Compatibility

Compatible with all modern browsers:
- Chrome/Edge (recommended)
- Firefox
- Safari
- Opera

## Clinical Disclaimer

⚠️ **This tool is for educational and decision support purposes only.** 

- This calculator provides estimates based on simplified physiological models
- Clinical decisions should always be based on complete patient assessment
- Individual patient factors may significantly affect actual fibrinogen levels
- Laboratory testing should guide definitive management decisions
- This tool does not replace clinical judgment or laboratory monitoring

## Use Case

Designed for obstetric hemorrhage management during:
- Postpartum hemorrhage
- Cesarean section with significant blood loss
- Placental complications (abruption, accreta, etc.)
- Any scenario requiring fibrinogen replacement tracking

## License

This project is open source and available for clinical and educational use.

## Contributing

Contributions, issues, and feature requests are welcome. Please ensure any modifications maintain clinical accuracy and include appropriate documentation.

## Authors

Developed for clinical decision support in obstetric hemorrhage management.

## Version History

- **v1.0.0** - Initial release with core functionality
  - Blood product tracking
  - Real-time fibrinogen modeling
  - Visual graphing interface
  - Support for term pregnancy blood volumes

## Acknowledgments

Built with consideration for:
- Obstetric hemorrhage management protocols
- Fibrinogen replacement guidelines
- Maternal critical care practices
