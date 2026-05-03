# Urban Heat Island Analysis — Tondo, Manila

Geospatial UHI analysis workflow for MSF's environmental health response in Tondo, one of Metro Manila's most densely populated districts.

**Internship project** · University of Salzburg · Z_GIS · Geo-Humanitarian Research Group

## What it does

- Maps seasonal UHI hotspots using satellite-derived Land Surface Temperature (LST)
- Fuses multi-sensor thermal data (Sentinel-3 SLSTR / MODIS → 30 m via Landsat regression)
- Builds a heat-exposure vulnerability index (LST + population + built-up + vegetation + health)
- Produces monthly LST time-series, threshold analysis, and barangay-level rankings
- **Fully automated** — change only the AOI bounding box to rerun for any city

## Versions

| Version | Description |
|---------|-------------|
| `v1` | Landsat 9 only, basic UHI + vulnerability |
| `v2` | Landsat 8+9, MODIS fusion, monthly time-series |
| `v3` | Added Sentinel-3 SLSTR via CDSE + MODIS fallback |
| `v4` | **Current** — S3 via fast Nodes API, LST threshold analysis, enhanced statistics |

## Data Sources

- **Landsat 8+9** C02 L2 (30 m, ~8-day) — via Google Earth Engine
- **Sentinel-3 SLSTR** LST (1 km, daily) — via Copernicus Data Space
- **MODIS** Terra+Aqua (1 km, daily) — via GEE (auto-fallback)
- **WorldPop**, GHSL, ESA WorldCover, Google Open Buildings, Healthsites

## Requirements

- Google Earth Engine account + Cloud Project
- Copernicus Data Space account (free, for Sentinel-3)
- Python: `earthengine-api`, `folium`, `pandas`, `matplotlib`, `seaborn`, `xarray`, `netCDF4`

## Quick Start

1. Open `UHI_Analysis_Workflow_v4.ipynb` in Jupyter or Colab
2. Run Cell 0A (install) → Cell 0B (paste your GEE project ID + CDSE credentials)
3. Edit `AOI_BBOX` in the Configuration cell
4. Run All

## License

Open for academic and humanitarian use.
