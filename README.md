# Silver Fox Marketing - Dealership Prospecting Map

**Interactive Google Maps-powered tool for discovering and tracking automotive dealerships across your service areas.**

## Overview

This map combines Silver Fox Marketing's existing client and prospect data with Google Maps and Places API to create a powerful prospecting tool. Unlike standard Google Maps, this filters out all non-dealership businesses and clearly distinguishes between clients, prospects, and potential new opportunities.

## Key Features

### 🎯 Auto-Discovery of Dealerships
- Automatically finds ALL car dealerships in any visible map area
- Uses Google Places API to search in real-time
- Smart grid search covers entire visible region (not just center point)
- Results accumulate as you explore - zoom in/out without losing data

### 🔵 Three-Tier Color System
- **Blue Markers** - Your existing clients (42 dealerships)
- **Red Markers** - Your current prospects (13 dealerships)
- **Yellow Markers** - Other dealerships (auto-discovered potential prospects)

### 🔍 Smart Search & Navigation
- Search any location by city, address, or dealership name
- Click results to jump directly to that location
- Auto-complete suggestions powered by Google Places

### ⚙️ Map Controls (Collapsible Modal)
- **Toggle Layers:** Show/hide clients, prospects, or other dealerships
- **🔄 Refresh:** Find dealerships in current view (accumulates results)
- **🗑️ Clear:** Remove all auto-discovered yellow markers
- **Service Areas:** Toggle 20-mile radius circles around client locations

### 💡 Rich Dealership Info (Google Places Integration)
Click any marker to see:
- Full business name & address
- Phone number (click-to-call)
- Website link
- Google ratings & review count
- Current open/closed status
- "Get Directions" button

### 📱 Responsive Design
- Works on desktop, tablet, and mobile
- Touch-friendly controls
- Collapsible panels save screen space

## How to Use

### Initial Setup
1. Open `index.html` in any web browser
2. Map loads centered on Missouri with all clients/prospects visible

### Finding New Prospects

**Method 1: Regional Discovery**
1. Keep map zoomed out (state-wide view)
2. Click ⚙️ (Settings icon) → Click 🔄 (Refresh)
3. Wait 5-10 seconds while it searches 9 grid points
4. Yellow markers appear across entire visible area
5. Zoom into any city to see details

**Method 2: City-Specific Search**
1. Click 🔍 (Search) → Type city name (e.g., "Chicago, IL")
2. Click search result to jump to that city
3. Click ⚙️ → Click 🔄 to find dealerships in that area
4. Yellow markers appear for all non-client dealerships

**Method 3: Continuous Exploration**
1. Start zoomed out, click 🔄 to get state-wide coverage
2. Zoom into Kansas City
3. Click 🔄 again - adds MORE yellow markers in KC area
4. Pan to St. Louis, click 🔄 - adds STL dealerships too
5. Results accumulate - previous markers stay visible!

### Evaluating Prospects
- Click yellow marker → See Google business details
- Check reviews, website, phone number
- Use "Get Directions" to plan sales routes
- Toggle off clients/prospects to focus only on new opportunities

### Clearing & Resetting
- Click ⚙️ → Click 🗑️ to clear all yellow markers
- Start fresh in a new area

## Files

- `index.html` - Main Google Maps application
- `organizations_with_coordinates.csv` - 102 client dealerships with coordinates
- `geocoded_prospects.csv` - 21 prospect dealerships with verified addresses
- `prospect_dealerships_leads.csv` - Prospect summary for sales team
- `GBP_20_Cities_Summary.csv` - Service area city data

## Technical Details

### Google Maps APIs Used
- **Maps JavaScript API** - Core mapping functionality
- **Places API (Nearby Search)** - Auto-discovery of dealerships
- **Places API (Place Details)** - Business info when clicking markers
- **Places API (Autocomplete)** - Location search suggestions

### API Key Requirements
Requires Google Cloud API key with these APIs enabled:
- Maps JavaScript API
- Places API
- Geocoding API (optional)

Cost: Free tier covers ~28,000 map loads/month + 28,000 place details/month

### Search Algorithm
- **Zoom ≤ 7 (state-level):** 3×3 grid = 9 search points, 50km radius each
- **Zoom 8-10 (regional):** 2×2 grid = 4 search points, 50km radius each
- **Zoom > 10 (city-level):** Single search point, 50km radius
- 500ms delay between requests to avoid rate limits
- Automatic deduplication prevents showing same dealership twice

## Map Legend

| Color | Description | Count |
|-------|-------------|-------|
| 🔵 Blue | Our Client Dealerships | 42 |
| 🔴 Red | Our Prospect Dealerships | 13 |
| 🟡 Yellow | Other Dealerships (Auto-Discovered) | Unlimited |
| ⭕ Blue Circle | Service Area Radius (20 miles) | 42 |

## Key Markets

### Client Concentration
- **St. Louis Metro** - Highest client density (40+ dealerships)
- **Columbia, MO** - 8 clients (Joe Machens group, Honda, KIA, BMW)
- **Jefferson City, MO** - 3 clients (Capital City CDJR, Rusty Drewing group)

### Prospect Opportunities
- **Kansas City, MO** - Cable Dahmer group, Hendrick Chevrolet
- **Springfield, MO** - Reliable, Corwin, Thompson dealerships
- **Joplin, MO** - Fletcher Auto Group, Landers dealerships

### Expansion Markets (High Dealership Density)
Use auto-discovery to find opportunities in:
- Chicago, IL
- Memphis, TN
- Des Moines, IA
- Omaha, NE
- Wichita, KS
- Louisville, KY

## Data Sources

- **Client Data:** Silver Fox Marketing CRM
- **Prospect Data:** Verified via web research (October 2025)
- **Auto-Discovery:** Google Places API (real-time)
- **Geocoding:** Nominatim/OpenStreetMap
- **Business Details:** Google Places API (live data)

## Limitations

- Places API returns max 20 results per search point
- Large metropolitan areas may require multiple zoomed-in searches
- Some dealerships may be missing if not in Google's database
- API rate limits apply (see Google Cloud Console for usage)

## Updates & Maintenance

### To Update Client/Prospect Lists
1. Edit `organizations_with_coordinates.csv` (clients)
2. Edit `geocoded_prospects.csv` (prospects)
3. Update the `clients` and `prospects` arrays in `index.html` (lines 362-421)
4. Refresh browser

### To Change API Key
1. Open `index.html`
2. Find line 721: `src="https://maps.googleapis.com/maps/api/js?key=YOUR_KEY_HERE..."`
3. Replace API key
4. Save and refresh

## Version History

**v2.0 (October 23, 2025)**
- Complete rewrite using Google Maps + Places API
- Auto-discovery of dealerships via grid search
- Accumulating results (no longer clears on zoom)
- Collapsible modal controls
- Rich Google business info on click
- Mobile-responsive design

**v1.0 (October 22, 2025)**
- Initial Folium/Leaflet-based map
- Static client/prospect markers
- Basic search functionality
- Service area circles

## Last Updated

October 23, 2025

---

**Silver Fox Marketing**
3841 Wilmington Ave, St. Louis, MO 63116
314.260.9736 | silverfox@sfoxmarketing.com
