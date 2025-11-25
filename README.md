# Colorado Cities Map

An interactive map visualization of Colorado cities with demographic data, built with MapLibre GL JS.

## Features

- **Interactive Map**: Explore Colorado cities with detailed boundary overlays
- **Demographic Data**: View population, density, income, housing, and poverty statistics
- **Multiple Views**: Toggle between population and density visualizations
- **Interactive Charts**: Click on cities to see detailed demographic comparisons
- **Dark Theme**: Modern dark-themed map style using OpenMapTiles

## Technology Stack

- **MapLibre GL JS**: Open-source mapping library (no API keys required)
- **PMTiles**: Efficient vector tile format for base map
- **ApexCharts**: Interactive charts for demographic data
- **Python**: Simple HTTP server with PMTiles support

## Running the Application

1. **Start the development server:**
   ```bash
   python serve.py
   ```

2. **Open in browser:**
   ```
   http://localhost:8000
   ```

The server includes custom handlers for:
- CORS support
- Range requests for PMTiles
- Serving files from the `public/` directory

## Project Structure

```
colorado-cities-map-chart/
├── public/
│   ├── index.html          # Main HTML file
│   ├── css/
│   │   └── style.css       # Application styles
│   ├── js/
│   │   └── map.js          # Map and chart logic
│   └── styles/
│       └── maplibre-openmaptiles-pmtiles.json  # Map style
├── scripts/
│   ├── make_colorado_geojson.py       # Convert shapefiles to GeoJSON
│   └── enrich_with_demographics.py   # Add census data to GeoJSON
├── serve.py                # Development server
└── requirements.txt        # Python dependencies
```

## Data Sources

### Base Map
- **PMTiles**: Hosted at `https://data.storypath.studio/pmtiles/colorado.pmtiles`
- **Source**: OpenMapTiles schema with Colorado-specific data

### City Data
- **GeoJSON**: Hosted at `https://data.storypath.studio/geojson/colorado-cities-enriched-detailed-app.geojson`
- **Boundaries**: TIGER/Line Shapefiles from US Census Bureau (2024)
- **Demographics**: American Community Survey (ACS) 5-Year Data (2023)

## Development

### Python Environment

The project uses Python for data processing and the development server:

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

### Data Processing Scripts

1. **make_colorado_geojson.py**: Converts TIGER/Line shapefiles to GeoJSON
2. **enrich_with_demographics.py**: Adds ACS demographic data to the GeoJSON

These scripts were used to generate the hosted data files and are included for reference.

## License

Data sources:
- City boundaries: US Census Bureau TIGER/Line Shapefiles (Public Domain)
- Demographic data: US Census Bureau ACS 5-Year Estimates (Public Domain)
- Base map tiles: OpenStreetMap contributors (ODbL)
