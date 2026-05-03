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
### Landsat images

### Sentinel data from ![Copernicus](https://browser.dataspace.copernicus.eu/assets/copernicus-banner-CaeUPWRx.svg) Browser
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

This makes EPIC particularly valuable for studying atmospheric dynamics, vegetation phenology, and rapid environmental changes. https://www.kaggle.com/code/sndorburian/discvr-epic-images

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