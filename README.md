# An analysis of sex ratios using a biodiversity data cube from GBIF mobilised data

This notebook provides an analysis of sex ratios in bird species across Europe, using data downloaded from the Global Biodiversity Information Facility (GBIF). The dataset includes over 4 million occurrence records from nearly 5,000 datasets provided by 230 publishers. This analysis focuses on a specific subset of the data, filtering records based on quality checks and examining patterns in sex ratios over time and space.

Also see: Groom, Q. J., & Trekels, M. (2024, July 22). An analysis of sex ratios using a biodiversity data cube. [https://doi.org/10.37044/osf.io/9kcfx](https://doi.org/10.37044/osf.io/9kcfx)

## Overview

The notebook performs the following tasks:

1. **Data Import and Cleaning:**
   - The data is read from a tab-separated CSV file.
   - Records are filtered based on data quality criteria, including removing entries with problematic coordinates or verification issues.
   - Latitude and longitude values are extracted from custom cell codes for spatial analysis.

2. **Data Preparation:**
   - The dataset is transformed into a GeoDataFrame with geographic coordinates for spatial analysis.
   - Sex-specific counts (male, female, hermaphrodite) are calculated for each species and location.

3. **Spatial Analysis:**
   - Sex ratios are analyzed across grid cells in Europe, with data aggregated by species and location.
   - Geographic distributions of sex ratios are visualized using maps.
   - Kriging interpolation is used to visualize patterns in sex ratios and assess spatial heterogeneity.

4. **Temporal Analysis:**
   - Changes in sex ratios are examined over time, aggregated by decade.
   - Species with the highest and lowest proportions of sex-specific records are identified.

5. **Visualization:**
   - Various plots are generated to visualize the distribution of sex ratios, the total number of observations, and the geographic distribution of selected species.
   - A kriging interpolation map is created to visualize the spatial structure in the sex ratio data.

## How to Use

1. **Environment Setup:**
   - This notebook requires Python with the following packages: `pandas`, `geopandas`, `numpy`, `matplotlib`, `seaborn`, `shapely`, and `pykrige`.
   - The analysis also requires the shapefile of country boundaries, which should be downloaded separately from [Natural Earth Data](https://www.naturalearthdata.com/downloads/50m-cultural-vectors/).

2. **Data Import:**
   - Ensure the GBIF download CSV file is in the working directory with the name `0083528-240321170329656.csv`.
   - The shapefile for country boundaries should be available in the working directory as `ne_50m_admin_0_countries.shp`.

3. **Running the Notebook:**
   - The notebook is designed to be run sequentially. Run each cell step-by-step, ensuring that data is loaded and processed correctly.
   - Modify the input parameters as needed, especially the species taxon key for specific analyses.

4. **Visualization and Output:**
   - Maps and plots will be displayed inline.
   - Key outputs are saved as high-resolution JPG images in the working directory.

## Note

The current analysis assumes each occurrence record represents an individual organism, ignoring the `dwc:individualCount` field. Future analyses should consider incorporating this field for more accurate population estimates.
