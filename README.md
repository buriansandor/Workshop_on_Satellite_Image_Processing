# Workshop on Satellite Image Processing
> In this workshop we will talk about [MORE HERE LATER]

## The Basics of Satellite Image Processing 

![](/documentation/images/satellite_physics_fundamentals.png)

When [we get a satellite image](https://gemini.google.com/share/894544f79ee2) we get the fraction of reflectance and radinace, but we are curious about the reflectance (this is a number between 0-1).
$$\rho = \frac{\text{reflectance}}{\text{radiance}}$$

***For research we need rreflectance, because only this makes the data comparable in time and space.***

### Basic concepts
> **pixel**: A pixel is the smallest element of a digital image, a single "picture point". In satellite imagery, one pixel corresponds to a specific area on the surface, so pixel size is directly related to spatial resolution.
>
> **band**: A band is a measurement channel that collects data within a specific wavelength range. The more bands available and the more diverse they are, the better different surface types or materials can be distinguished from one another.
>
> **reflectance/backscatter**: Simply put, this describes how much signal returns to the sensor. In optical data, reflectance relates to reflected light; in radar, backscatter is the portion of the transmitted signal that scatters back—the part of the radar wave that returns toward the satellite.
>
> **spatial-spectral-temporal resolution**: Spatial resolution indicates how much surface area one pixel covers, typically expressed as `meters/pixel`. Spectral resolution refers to how many bands the sensor measures in and what bandwidth each has; temporal resolution describes how frequently new observations are made of the same area.
>
> **optical and radar data**: Optical data is based on measuring radiation reflected from the surface, so it appears more "photograph-like". Radar data, by contrast, is active measurement: the sensor emits its own signal and then measures the returning signal, providing different information that must be interpreted differently.

## Earth Observation Data sources

[![](/documentation/images/satimagesourcepaths.png)](https://gemini.google.com/share/b3a9de9041cd)

[![](/documentation/images/sentinel%20vs%20landsat.png)](https://gemini.google.com/share/ef829d2059a5)

### Landsat images
> #### **Use cases:**
> **Land cover classification and change detection**: Landsat's 30-meter resolution and long historical archive (since 1972) make it ideal for tracking long-term land use changes, deforestation patterns, and urban expansion over decades.
>
> **Agricultural monitoring and crop yield prediction**: The thermal bands in Landsat (Band 10 and 11) provide land surface temperature data that Sentinel lacks, enabling soil moisture assessment and crop stress detection.
>
> **Hydrological studies**: Landsat's thermal infrared capabilities are particularly useful for monitoring water body temperatures, identifying groundwater discharge zones, and studying glacial dynamics.

![](/documentation/images/landsat_data_applications.png)

- https://earthexplorer.usgs.gov/
- https://livingatlas.arcgis.com/landsatexplorer/#mapCenter=19.01111%2C47.51448%2C11.775&mode=dynamic&mainScene=%7CNatural+Color+for+Visualization%7C


### Sentinel images
> #### **Use cases:** 
> **Multispectral monitoring with high revisit frequency**: Sentinel-2's 5-day revisit time (or 2-3 days with both satellites) provides frequent observations ideal for rapid environmental monitoring, vegetation phenology tracking, and near-real-time disaster response without Landsat's 16-day revisit cycle.
>
> **High-resolution multispectral analysis**: Sentinel-2's 10-meter resolution (compared to Landsat's 30-meter) enables detailed urban mapping, infrastructure monitoring, and precise change detection at finer spatial scales.
>
> **Coastal and water quality monitoring**: Sentinel-2's coastal aerosol band (Band 1) and enhanced spectral resolution support improved water quality assessment, harmful algal bloom detection, and coastal ecosystem monitoring.
>
> **Atmospheric correction and standardized products**: Sentinel-2 Level 2A products come pre-processed with atmospheric correction applied, reducing preprocessing requirements and enabling faster analysis workflows compared to raw Landsat data.

![](/documentation/images/sentinel_data_applications.png)

#### Sentinel data from ![Copernicus](https://browser.dataspace.copernicus.eu/assets/copernicus-banner-CaeUPWRx.svg) Browser
1. Go to https://browser.dataspace.copernicus.eu Here is a bit more detailed Introduction video: https://www.youtube.com/watch?v=F0lIn5r6ZWk 
2. [Choose and get the Sentinel Satellite data from Copernicus Browser manually](https://www.youtube.com/watch?v=vgjXk85LIbE)

A detailed short guide to Copernicus Browser: https://www.youtube.com/watch?v=07UNlYZ1SxM
### Other Satellite image data 
<details>
<summary>EPIC</summary>

**EPIC (Earth Polychromatic Imaging Camera)** provides unique advantages for satellite image processing:

- **Full disk imagery**: Captures the entire Earth disk from geostationary orbit, enabling global monitoring
- **High temporal resolution**: Images available every 10-15 minutes, ideal for tracking rapid atmospheric and surface changes
- **UV and visible wavelengths**: Covers unique spectral bands useful for aerosol detection and air quality monitoring
- **Real-time data availability**: Supports time-sensitive applications like weather monitoring and disaster response
- **Complementary data**: Fills gaps between polar-orbiting satellites by providing continuous observations of the same region

This makes EPIC particularly valuable for studying atmospheric dynamics, vegetation phenology, and rapid environmental changes. 

Python example: https://www.kaggle.com/code/sndorburian/discvr-epic-images

</details>

<details>
<summary>GEDI Lidar</summary>

![GEDI Ecosystem Lidar](https://gedi.umd.edu/wp-content/uploads/2023/09/gedi-logo.jpeg)

> This is not an imaging sensor in the traditional sense, but rather a laser rangefinder.
>
> Forest canopy height and biomass estimation. If someone works in environmental protection, this is a mandatory element.
>
> Not raster, but point cloud or dense point series. The geopandas and h5py libraries are required for it.

- NASA GEDI projet main page: https://www.earthdata.nasa.gov/data/instruments/gedi-lidar
- GEDI projects: https://gedi.umd.edu/
- Getting started with GEDI in Python: https://lpdaac.usgs.gov/documents/630/GEDI_L2A_Tutorial.html

</details>

<details>
<summary>MODIS (Terra & Aqua)</summary>

> Before Sentinel-3 was launched, MODIS was the workhorse of research. Although its resolution (250m-1km) lags behind Sentinel, it has over 20 years of continuous data.
>
> Advantages: Long term climate research and daily coverage

- MODIS main page: https://modis.gsfc.nasa.gov/
- MODIS Terra Data: https://terra.nasa.gov/data/modis-data
- MODIS data in python: https://www.linkedin.com/pulse/download-combine-visualize-modis-python-tutorial-code-keyhan-gavahi-nvqkc
- pip package: https://pypi.org/project/octvi/

</details>

<details>
<summary>EnMAP</summary>

![](https://www.enmap.org/_nuxt/img/9ebc66d.png)

> The Environmental Mapping and Analysis Program (EnMAP) is a German hyperspectral satellite mission that monitors and characterizes Earth’s environment on a global scale. EnMAP measures geochemical, biochemical and biophysical variables providing information on the status and evolution of terrestrial and aquatic ecosystems. 

- Main page: https://www.enmap.org/
- Data access portal: https://planning.enmap.org/
- Enamp data prerocessing tool in Python: https://github.com/GFZ/enpt
- Processing EnMAP in MATLAB: https://mres.uni-potsdam.de/2026/04/16/importing-enmap-hyperspectral-images-with-matlab/ 

</details>

<details>
<summary>PlanetScope</summary>

> Although commercial, Planet has an excellent Education and Research program where researchers can access data for free.
>
> It can be usefull while, it has a 3 meter resolution, and a daily coverage.


- Main page for researchers: https://www.planet.com/science/

</details>

## Satellite Image Processing with Python - basics
Install:
```Jupyter Notebook Python
!pip install sentinelhub
!pip install rasterio
!pip install sentinelhub shapely
!pip install numpy
!pip install geopy
```

### Sentinel

### Landsat
- https://pypi.org/project/landsatxplore/

## Types of satellite images, and how to handle them
 
### True Color

### NDWI 
https://www.kaggle.com/code/sndorburian/get-the-shoreline-on-satellite-images

### NDVI 

$$NDVI = \frac{NIR - Red}{NIR + Red}$$

### SAR
- https://www.kaggle.com/code/sndorburian/polsar-data-processing-using-python
- data: https://www.kaggle.com/datasets/sndorburian/saocom-geocoded-subset

## New space constellations

### Analysis Ready Data

### Data cubes 

## Segment Any Model (SAM)

https://livingatlas.arcgis.com/en/browse/?q=dlpk%20detection#d=2&q=dlpk+detection