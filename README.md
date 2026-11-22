# Agronomic Intelligence

A small WebGIS for screening land in Indonesia. Click any point on the map, or paste coordinates, to see:

- the soil profile from HWSD v2 (soil class, texture, pH, organic carbon, CEC, and more, by layer),
- the 1991–2020 monthly rainfall normal,
- a six-month outlook for rainfall, temperature, humidity, and vapor-pressure deficit (ECMWF SEAS5),
- a rule-based fertility screen with management suggestions.

Live site: https://alfasisurya.github.io/agronomic-intelligence/

It is a single static page (`index.html`) with no build step. Everything runs in the browser with Leaflet, sql.js, GeoTIFF.js, and Chart.js.

This is a screening tool built on coarse global datasets. It does not replace a field survey or a laboratory soil test.

## Data and licenses

| File or service | Source | License |
| --- | --- | --- |
| `data/hwsd2_idn.sqlite`, `data/hwsd2_idn.tif` | Indonesian subset of the Harmonized World Soil Database v2.0, FAO & IIASA (2023), https://doi.org/10.4060/cc3823en | CC BY-NC-SA 3.0 IGO (non-commercial, share-alike) |
| `data/provinces.geojson`, `data/neighbours.geojson` | Natural Earth admin-1 boundaries, simplified | Public domain |
| Satellite basemap | Sentinel-2 cloudless 2016 by EOX IT Services GmbH (contains modified Copernicus Sentinel data 2016), https://s2maps.eu | CC BY 4.0 |
| Place names (city, district, province) | OpenStreetMap Nominatim reverse geocoding, one request per map click | ODbL; usage limited to ~1 req/s |
| Historical climate and seasonal forecast | Open-Meteo Historical Weather API (ERA5) and Seasonal Forecast API (ECMWF SEAS5) | CC BY 4.0, free for non-commercial use |

Because the soil data is CC BY-NC-SA, this project as a whole is for non-commercial use.

## Run locally

```
python -m http.server 8000
```

Then open http://localhost:8000/.

## Author

Marcelinus Alfasisurya Setya Adhiwibawa, M.Stat. — https://alfasisurya.github.io/portfolio/
