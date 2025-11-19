# Nearby-places-wp-plugin
Displays a map and nearby places using Leaflet and Overpass API
# Nearby Places Map (WordPress Plugin)

A lightweight WordPress plugin that displays nearby places on an interactive map using **Leaflet**, **OpenStreetMap**, and **Overpass API**.  
No Google Maps. No billing. No API keys.

This plugin locates nearby amenities such as restaurants, banks, hospitals, parks, schools, and more based on latitude and longitude stored in the post meta.

---

## Features

### ✔ No Google APIs or billing  
Uses OpenStreetMap + Overpass API for place search and map display.

### ✔ Dynamic nearby places filtering  
Categories include:
- Restaurants  
- Banks  
- Grocery  
- Bars  
- Shopping  
- Hospitals  
- Police  
- Schools  
- Transit  
- Parks  
- Fire stations  
- Places of worship  
- Gyms  

### ✔ Interactive Leaflet map  
- Custom category markers  
- Center marker for main location  
- Click item → map flies to marker  
- Popup with name + distance  
- Auto-centers all markers  
- Hovering highlights both marker and list item  

### ✔ Smart Overpass query system  
- Progressive radius search (5 km → 8 km → 12 km)  
- Avoids returns with empty results  

### ✔ Caching  
Session-based caching (per category + radius) to reduce Overpass load.

### ✔ Fail-safe fallback  
If Overpass or internet fails:
- Shows a friendly offline message  
- Automatically retries  
- Never breaks your layout  

---

## Installation

1. Download the plugin files.  
2. Upload to `/wp-content/plugins/nearby-places-map/`  
3. Activate via **Plugins → Installed Plugins** in WordPress.  
4. Ensure your posts have latitude and longitude stored as custom fields:

## Usage

Insert the shortcode in any WordPress post or page:
[nearby_places]


The plugin will:

1. Read the latitude and longitude from the post  
2. Render an interactive map  
3. Fetch POIs from Overpass API  
4. Display a category selector and matching list  

---

## File Structure

nearby-places-map/
│
├── nearby-places.php # Main plugin file
├── css/
│ └── nearby-places.css # Frontend styling
├── js/
│ └── nearby-places.js # All map + Overpass logic
└── img/ # Marker & filter icons


---

## Requirements

- WordPress 5.0+  
- PHP 7.4+  
- jQuery (bundled in WP)  
- Internet access to Overpass API  

---

## How It Works

### 1. Retrieve post location  
Coordinates are pulled from post meta.

### 2. Map initialization  
Leaflet loads OSM tiles with a center marker.

### 3. Category filters  
User selects a category (restaurants, banks, etc.)

### 4. Progressive radius querying  
Overpass API is queried progressively until it finds results.

### 5. Marker + list rendering  
Each result includes:
- Name  
- Coordinates  
- Distance from center  
- Popup  
- Click events  
- Hover sync  

### 6. State caching  
Each category → radius combination is stored in sessionStorage.

---

## Known Limitations

- Overpass API rate-limits abusive requests.  
- Requires valid lat/lng in post meta.  
- Results depend entirely on OpenStreetMap data quality.  

---

## Roadmap

- Marker clustering  
- Custom subcategory filter buttons  
- Manual radius slider  
- “Search this area” button  
- Directions button inside popup  

---

## License

MIT License.  
Free for personal and commercial use.

---

## Author

**Amit**  
Web Developer & Digital Marketing Specialist  
15+ years of experience in WordPress, design, and performance optimization.
