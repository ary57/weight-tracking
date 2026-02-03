# Weight Tracker

A minimal, privacy-focused daily weight tracking application built as a single HTML file. No server required, no data collection, completely offline-capable.

## About

This application was written by Claude (Anthropic) on February 3, 2026, based on user requirements for a simple, self-contained weight tracking solution.

## Features

- **Daily Weight Logging**: Log your weight for today with a single tap
- **Visual Progress Chart**: See your weight trend over time with an interactive chart
- **Unit Toggle**: Switch between pounds (lb) and kilograms (kg)
- **Data Management**: 
  - Export your data as JSON for backup
  - Import previously exported data
  - Delete all data when needed
- **Progressive Web App (PWA)**: Install on your phone's home screen for an app-like experience
- **Complete Privacy**: All data stored locally in your browser, nothing sent to any server
- **Offline Capable**: Works without internet connection
- **Cross-Platform**: Works on iOS, Android, and all modern desktop browsers

## Installation

### Desktop
1. Download `weight-tracker.html`
2. Open it in any modern web browser (Chrome, Firefox, Safari, Edge)
3. Bookmark it for easy access

### iOS (iPhone/iPad)
1. Open `weight-tracker.html` in Safari
2. Tap the Share button (square with arrow)
3. Scroll down and tap "Add to Home Screen"
4. Tap "Add"
5. The app icon will appear on your home screen

### Android
1. Open `weight-tracker.html` in Chrome
2. Tap the menu (three dots)
3. Tap "Add to Home Screen" or "Install app"
4. Tap "Add" or "Install"
5. The app icon will appear on your home screen

## Usage

### Logging Weight
1. Enter your weight in the input field
2. Tap "Log Weight"
3. The entry is automatically saved for today's date

### Changing Units
1. Tap the ⚙️ settings icon (top right)
2. Under "Unit", select either "lb" or "kg"
3. All existing entries and the chart will automatically convert

### Managing Data

#### Export Data
1. Tap the ⚙️ settings icon
2. Tap "Export Data"
3. A JSON file will download with the format: `weight-tracker-YYYY-MM-DD.json`
4. Save this file for backup or to transfer to another device

#### Import Data
1. Tap the ⚙️ settings icon
2. Tap "Import Data"
3. Select a previously exported JSON file
4. Confirm the import
5. Data will be merged (newer entries replace older ones for the same date)

#### Delete All Data
1. Tap the ⚙️ settings icon
2. Tap "Delete All Data"
3. Confirm twice (this action cannot be undone)

### Deleting Individual Entries
1. Find the entry in the "Recent Entries" list
2. Tap "Delete" next to that entry
3. Confirm deletion

## Technical Details

### Technology Stack
- **HTML5**: Structure
- **CSS3**: Styling and responsive design
- **Vanilla JavaScript**: All functionality (no frameworks)
- **Canvas API**: Chart rendering
- **LocalStorage API**: Data persistence
- **Service Worker**: PWA offline capability

### Browser Compatibility
- Chrome/Edge: 90+
- Firefox: 88+
- Safari: 14+
- Mobile browsers: iOS Safari 14+, Chrome Mobile 90+

### Data Storage
All data is stored in the browser's `localStorage` under these keys:
- `weightEntries`: JSON array of weight entries
- `weightUnit`: Current unit preference ('lb' or 'kg')
- `installPromptDismissed`: Whether user dismissed the install prompt

### Data Format
Each weight entry is stored as:
```json
{
  "date": "2026-02-03",
  "weight": 180.5,
  "unit": "lb"
}
```

Export files include:
```json
{
  "entries": [...],
  "unit": "lb",
  "exportDate": "2026-02-03T12:00:00.000Z"
}
```

## Maintenance & Troubleshooting

### Common Issues

**Data not saving**
- Check if localStorage is enabled in your browser
- Ensure you're not in private/incognito mode
- Check browser storage quota

**Chart not displaying**
- Ensure you have at least one entry logged
- Try resizing the browser window
- Check browser console for errors

**Import failing**
- Verify the JSON file is from a valid export
- Check the file hasn't been corrupted
- Ensure the file uses the correct format

### Updating the Application

Since this is a single-file application:
1. Save your data using "Export Data"
2. Replace the HTML file with the new version
3. Open the new version
4. Use "Import Data" to restore your data

### Customization

The application can be customized by editing the HTML file:

**Change Colors**
- Theme color: Search for `#007bff` (primary blue) and replace
- Background: Search for `#f5f5f5` and replace

**Modify Chart Appearance**
- Find the `renderChart()` function
- Adjust padding, line width, colors, etc.

**Add Features**
- All logic is contained in the `<script>` section
- Data is stored in the `entries` array
- Use the existing save/load pattern for new features

## Privacy & Security

- **No tracking**: Zero analytics or tracking code
- **No external requests**: Everything runs locally (except Service Worker registration)
- **No accounts**: No sign-up, no passwords
- **Your data stays yours**: Only stored on your device
- **Export anytime**: Full data portability

## File Structure

```
weight-tracker.html (single file containing):
├── HTML structure
├── CSS styles (embedded)
├── JavaScript logic (embedded)
└── PWA manifest (data URI)
```

## License

This application was created by Claude (Anthropic) for a user requesting a minimal weight tracking solution. The code is provided as-is for personal use.

## Support

This is a standalone application with no official support channel. For issues:
1. Check the Troubleshooting section above
2. Verify browser compatibility
3. Try exporting/importing data
4. Use browser developer tools to debug

## Version History

- **v1.0** (February 3, 2026)
  - Initial release
  - Daily weight logging
  - lb/kg unit toggle
  - Chart visualization
  - PWA support
  - Export/Import/Delete functionality
  - iOS and Android home screen installation

## Future Enhancement Ideas

Potential features for future versions:
- Goal weight setting and progress indicator
- Weekly/monthly average calculations
- BMI calculator integration
- Notes/tags for each entry
- Multiple weight entries per day
- Dark mode
- Data visualization improvements (trend lines, predictions)
- Reminder notifications
- Body measurements tracking (waist, chest, etc.)

---

**Built with**: HTML5 + CSS3 + Vanilla JavaScript  
**Created by**: Claude (Anthropic)  
**Date**: February 3, 2026  
**File**: Single HTML file, ~15KB  
**Dependencies**: None
