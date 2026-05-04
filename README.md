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
>
> **Hyperspectral sensors** like EnMAP capture dozens to hundreds of narrow bands, allowing precise material identification and biochemical analysis. 
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

Main page for researchers: https://www.planet.com/science/

**To access the 30 day trial go here:** https://insights.planet.com/sign-up

**To access for regular tasks:**
1. register a free account on: https://eoiam-idp.eo.esa.int/myaccount
2. visit: https://earth.esa.int/eogateway
3. [search for `planetscope`](https://earth.esa.int/eogateway/search?text=planetscope)
4. Go to the Data Archive: https://earth.esa.int/eogateway/catalog/planetscope-full-archive
5. Fill the project proposal form: https://esatellus.service-now.com/csp?id=project_proposal&dataset=PlanetScope.Full.Archive

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

### Landsat
Here are the most common methods to access to Landsat images: 

#### Google Earth Engine
Detailed descriptin in PDF: [gee-kaggle-setup-guide.pdf](/documentation/gee-kaggle-setup-guide.pdf)

1. Register for Google Earth Engine (Free Noncommercial Tier)
enable the Service Usage Consumer and  Earth Engine Resource Writer roles: https://earthengine.google.com/signup
2. create a service account: https://console.cloud.google.com/iam-admin/serviceaccounts
3. Assign roles: Earth Engine Resource Writer and Service usage consumer
4. get the JSON Key

Running example: https://www.kaggle.com/code/sndorburian/using-landsat-images-with-google-earth-engine
Code: [using-landsat-images-with-google-earth-engine.ipynb](/using-landsat-images-with-google-earth-engine.ipynb)

#### Official USGS API
1. Register an USGS account: https://ers.cr.usgs.gov/
2. Get an API key
3. Get Access to the USGS MACHINE interface (this will give access to API to download satellite images). *This can take up to 48 hour or more!*

Example: https://www.kaggle.com/code/sndorburian/usgs-landsat-api

##### `landsatxplore`
https://pypi.org/project/landsatxplore/
1. Register an USGS account: https://ers.cr.usgs.gov/
2. To use `landsatxplore` you will need python3.11 environment, this means you have to probably scale down your system.
3. `pip install landsatxplore`
4. Follow the instructions from the GitHub page of the project: https://github.com/yannforget/landsatxplore 

More: https://medium.com/data-science/downloading-landsat-satellite-images-with-python-a2d2b5183fb7

### Sentinel
1. Create an account: Go to [dataspace.copernicus.eu](https://dataspace.copernicus.eu/) and register (free, EU-based)
2. Open Sentinel Hub Dashboard: After logging in, click on "Sentinel Hub" under your profile icon
3. Register an OAuth client: In the [Dashboard, create a new OAuth client → this will provide your `CLIENT_ID` and `CLIENT_SECRET` values](https://shapps.dataspace.copernicus.eu/dashboard/#/)

Running Example: https://www.kaggle.com/code/sndorburian/sentinel-satellite-image-demo
Code: [sentinel-satellite-image-demo.ipynb](/sentinel-satellite-image-demo.ipynb)

More Code snippet for sentinel hub: https://github.com/eu-cdse/notebook-samples/tree/main

## Types of satellite image channels, and how to handle them

> Satellite images contain multiple spectral bands (channels) that capture different wavelengths of electromagnetic radiation, each revealing different information about Earth's surface. 
>
> **Optical satellites** like Sentinel-2 and Landsat provide bands in visible, near-infrared, and short-wave infrared ranges, enabling applications like vegetation monitoring (NDVI), water detection (NDWI), and land cover classification. 


### Common optical satellite channels include:
- **Blue (B)**: 0.45-0.52 μm - water absorption, atmospheric correction
- **Green (G)**: 0.52-0.60 μm - vegetation reflectance, chlorophyll content
- **Red (R)**: 0.63-0.69 μm - vegetation discrimination, land-water boundaries
- **Near-Infrared (NIR)**: 0.76-0.90 μm - vegetation vigor, water body delineation
- **Short-Wave Infrared (SWIR)**: 1.55-2.30 μm - soil moisture, mineral composition
- **Thermal Infrared (TIR)**: 10-12 μm - land surface temperature (Landsat only)
- **Coastal Aerosol (CA)**: 0.43-0.45 μm - aerosol and coastal water monitoring (Sentinel-2)
- **Vegetation Red Edge (VRE)**: 0.70-0.78 μm - fine vegetation analysis (Sentinel-2)

***Always consider each sensor's spatial, spectral, and temporal resolution when selecting data for your application.***

### Just a few examples:
|      | True Color | NDWI | NDVI |
| ---- | ---------- | ---- | ---- |
| description | RGB composite displaying natural colors (Red, Green, Blue bands) for visual interpretation, appearing like a natural photograph | Normalized Difference Water Index; highlights water bodies by contrasting infrared and near-infrared reflectance | Normalized Difference Vegetation Index; measures vegetation health and density using near-infrared and red band reflectance |
| Equation |        | $NDWI = \frac{(NIR - SWIR)}{(NIR + SWIR)}$ | $NDVI = \frac{NIR - Red}{NIR + Red}$ |
| Example  |        | https://www.kaggle.com/code/sndorburian/get-the-shoreline-on-satellite-images | https://colab.research.google.com/drive/1d2Fkd-OIfSQLeh2B54iTpPRhotzEfvvJ?usp=sharing from the [Postfire biomass recovery based on Earth observation data](https://github.com/buriansandor/Postfire_biomass_and_wildlife_recovery_based_on_Earth_observation_data) project|

> Where:
> - NIR: Near-Infrared band (typically 0.76-0.90 μm)
> - SWIR: Short-Wave Infrared band (typically 1.55-1.75 μm)

### SAR
> **Radar satellites** like Sentinel-1 transmit their own signals and measure backscatter, penetrating clouds and providing data day/night providING A synthetic aperture radar (SAR) data in single or multiple polarizations (VV, VH, HH, HV), useful for change detection, flood mapping, and terrain analysis regardless of cloud cover or daylight conditions.

![](/documentation/images/SAR_satellite_images.png)

#### Comparison: SAR vs. Optical Satellite Resolution

| Aspect | SAR (Radar) | Optical |
| --- | --- | --- |
| **Spatial Resolution** | 1-100 meters (varies by satellite) | 0.3-1000 meters (Sentinel-2: 10-60m, Landsat: 30m) |
| **Temporal Resolution** | 6-12 days (Sentinel-1: 6 days) | 5-16 days (Sentinel-2: 5 days, Landsat: 16 days) |
| **Spectral Resolution** | Single or dual polarization (VV, VH, HH, HV) | Multiple bands (Sentinel-2: 13 bands, Landsat: 11 bands) |
| **Weather Dependency** | Cloud/darkness independent; all-weather | Cloud-limited; daylight required |
| **Data Type** | Backscatter intensity; phase information available | Reflectance/radiance measurements across wavelengths |
| **Best For** | Change detection, flood mapping, terrain analysis, deformation monitoring | Vegetation monitoring, water quality, land cover classification, thermal analysis |

- Demo code: https://www.kaggle.com/code/sndorburian/polsar-data-processing-using-python
- Data for the demo: https://www.kaggle.com/datasets/sndorburian/saocom-geocoded-subset

## New space constellations
> New Space satellite image providers are valuable because they make Earth observation faster, more flexible, and more accessible. Compared with traditional public missions, they often offer higher revisit frequency, quicker data delivery, and commercial services tailored to specific user needs.
>
> They are especially useful for applications that require near-real-time monitoring, such as agriculture, disaster response, infrastructure tracking, and environmental change detection. Their constellations can capture the same area more often, which helps researchers and companies detect short-term changes that might be missed by less frequent acquisitions.
>
> ![](/documentation/images/newspace_imagery.png)
>
> Another major advantage is usability. Many New Space providers offer analysis-ready products, cloud-based platforms, and APIs, which reduce the technical barrier for users who do not want to build a full remote sensing pipeline from scratch. This makes satellite data easier to integrate into research, business, and decision-making workflows.

### Analysis Ready Data
> ARD commonly includes steps such as geometric correction or orthorectification, atmospheric correction, cloud masking, and sometimes re-gridding or harmonization. The goal is that data from different dates, seasons, viewing conditions, or sensors can be compared more reliably
>
> **Why it matters**
ARD is especially useful for time-series analysis, machine learning, and large-scale monitoring because it removes much of the repetitive setup work that would otherwise be needed before analysis.

### [Data cubes](https://www.perplexity.ai/apps/7c6a365b-34f8-41ea-ab55-7ab6a90f2065) 
> **What:** Data cubes are a way to organize satellite and geospatial data as one multidimensional structure instead of many separate image files. In Earth observation, they usually stack data by space and time, and often also by spectral band, so the same location can be analyzed across many dates in one consistent framework.

[![](/documentation/images/datacubes.png)](https://www.perplexity.ai/apps/7c6a365b-34f8-41ea-ab55-7ab6a90f2065)

> **Why:** Data cubes are useful because they shift analysis from a file-by-file workflow to a query-based workflow, which is much better for large time series and repeated monitoring. They are commonly built from analysis-ready data, so users can focus more on analysis and less on repeated preprocessing.

Running Example: https://www.kaggle.com/code/sndorburian/landsat-ndvi-data-cube-margaret-island-bud
Code: [landsat-ndvi-data-cube-margaret-island-bud.ipynb](/landsat-ndvi-data-cube-margaret-island-bud.ipynb)

## Segment Any Model (SAM)

> The landscape of satellite image segmentation has shifted from labor-intensive manual labeling to the era of **Foundation Models**. At the forefront is [Meta’s Segment Anything Model (SAM)](https://medium.com/@beeilab.yt/segment-anythin-model-sam-for-satellite-image-segmentation-part-1-39f17e6eb2b3), which acts as a "Swiss Army knife" for identifying objects. Unlike traditional architectures like U-Net or DeepLabV3+, which require thousands of domain-specific training samples to recognize a "building" or a "tree," SAM is zero-shot. This means it understands the concept of "objectness" out of the box, allowing researchers to extract features using simple prompts like points or bounding boxes.
>
> For specialized Earth Observation (EO) workflows, tools like sam-geo have adapted these capabilities to handle geospatial coordinates and GeoTIFF formats directly. While SAM excels at rapid discovery and interactive mapping, traditional supervised models still hold their ground:
>
> > **[U-Net](https://github.com/reachsumit/deep-unet-for-satellite-image-segmentation) & [DeepLabV3+](https://learnopencv.com/deeplabv3-ultimate-guide/):** The reliable workhorses for specific, repetitive tasks (e.g., global road extraction) where a lightweight, highly-specialized model is more efficient than a massive transformer.
> 
> > [**SegFormer:**](https://github.com/NVlabs/SegFormer) A middle ground that utilizes hierarchical Transformers to capture both fine details and global context, often outperforming older CNNs in complex urban environments.
>
> > [**SAM 2:**](https://ai.meta.com/research/sam2/) The latest evolution, extending these capabilities to the temporal dimension—perfect for tracking changes across a time-series or "video" of satellite acquisitions.

***Research Tip:*** *Choose SAM when you need to map a new area quickly without a training dataset. Choose U-Net or DeepLab when you have ample labels and need a production-ready pipeline for a single specific class.*

**Other related models:** 
- https://livingatlas.arcgis.com/en/browse/?q=dlpk%20detection#d=2&q=dlpk+detection