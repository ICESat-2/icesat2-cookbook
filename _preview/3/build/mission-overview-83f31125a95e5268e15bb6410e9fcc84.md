# ICESat-2 Mission Overview

## Author(s)

Tyler Sutterley

```{admonition} Existing Tutorials
:class: tip

- [Mission Overview - 2024 ICESat-2 hackweek](https://github.com/ICESAT-2HackWeek/website-2024/blob/main/book/tutorials/mission-overview/icesat-2-mission-overview.ipynb)
- [Mission Overview and Data - 2023 ICESat-2 hackweek](https://icesat-2-2023.hackweek.io/tutorials/mission_overview/index.html)

```

```{admonition} Learning Outcomes

* understand the technology used to acquire ICESat-2 data products and how that
informs data coverage, resolution and frequency

* learn about the hierarchy of data products and the factors influencing 
decisions on which products to use

```


```{div} text-center
:style: "height: 400px; display: flex; align-items: center; justify-content: center;"

# Part 1: Mission and Instrument Overview
```

### ICESat-2 Science Objectives

::::{grid} 1 1 2 2

:::{grid-item}
- Quantify polar ice sheet contributions to current and recent sea level change and the linkages to climate conditions
- Quantify regional signatures of ice sheet changes
  - Assess mechanisms driving recent changes
  - Improve predictive ice sheet models
- Estimate sea ice thickness to examine ice-ocean-atmosphere exchanges of energy, mass and moisture
- Measure vegetation canopy height as a basis for estimating large-scale biomass and biomass change

:::

:::{grid-item} 
```{image} https://zenodo.org/records/15748119/files/ICESAT2_wLasers.png
:width: 50%
:align: center
:alt: ICESat-2 satellite with lasers
```
:::

::::

### Advanced Topographic Laser Altimeter System (ATLAS)

```{figure} https://zenodo.org/records/15748119/files/remotesensing-11-01721-g002.png
---
width: 80%
align: center
name: ATLAS system diagram
---
ICESat-2 beam configuration [(Neuenschwander, 2019)](https://doi.org/10.3390/rs11141721)
```

- Single 10kHz 532nm laser micro-pulse → split into 6 beams
- Detectors sensitive to green light returns at the single photon level
- On-the-ground 3 km spacing between pairs to increase spatial coverage
- On-the-ground 90 m pair spacing for slope determination
- Different beam energies to provide dynamic range for varying surface reflectances
- High-energy beams (4×) for better performance over low-reflectivity targets

### ATLAS Transmitter

```{figure} https://zenodo.org/records/15748119/files/atlas_transmitter.png
---
width: 80%
align: center
name: ATLAS transmitter diagram
---
ATLAS transmitter diagram (ATL03 ATBD)
```

### ATLAS Receiver

```{figure} https://zenodo.org/records/15748119/files/atlas_receiver.png
---
width: 80%
align: center
name: ATLAS receiver diagram
---
ATLAS receiver diagram (ATL03 ATBD)
```

### ATLAS Photon Timing

```{figure} https://zenodo.org/records/15748119/files/atlas_timing.png
---
width: 80%
align: center
name: ATLAS photon timing diagram
---
ATLAS photon timing diagram (ATL03 ATBD)
```

### ICESat-2 Photon Geolocation

#### Photon time of flight
- Measuring the two-way return time of transmitted photons

#### Position of observatory in space
- Precision Orbit Determination (POD) – NASA GSFC
- Based on Ruag GPS receivers
- Verified with Satellite Laser Ranging (SLR)
- Orbit known to < 2 cm radial

#### Pointing vectors for ATLAS laser beams
- Precision Pointing Determination (PPD) – UT Austin Applied Research Lab
- Based on Sodern Star Trackers and Laser Reference System (LRS)
- Verified with cal/val data comparisons with photon returns

```{admonition} Putting the pieces together
Photon TOF + POD + PPD → 
photon return bounce point
```

### ICESat-2 Primary Measurements

```{figure} https://zenodo.org/records/15748119/files/icesat-2-schematic.png
---
width: 80%
align: center
name: ICESat-2 measurement schematic
---
ICESat-2 measurement schematic (ATL02 ATBD)
```

### ICESat-2 Orbits

::::{grid} 1 1 2 2

:::{grid-item}
- 500 km altitude
- 88° S to 88° N
- 15 revolutions/day
- 1387 repeat ground tracks
- 91-day revisit time
:::

:::{grid-item}
```{figure} https://zenodo.org/records/15748119/files/icesat2_orbits_converging.png
---
width: 100%
align: center
name: ICESat-2 orbits
---
ICESat-2 Orbits (NASA Science Visualization Studio)
```
:::

::::

```{tip}
`kml` files with predicted ground tracks available at [https://icesat-2.gsfc.nasa.gov](https://icesat-2.gsfc.nasa.gov)
```

### ICESat-2 Along-Track Sampling

```{figure} https://zenodo.org/records/15748119/files/icesat2_beams.png
---
width: 85%
align: center
name: ICESat-2 beam configuration
---
ICESat-2 beam configuration [(Smith et al., 2019)](https://doi.org/10.1016/j.rse.2019.111352)
```

### Spacecraft Orientation

```{figure} https://zenodo.org/records/15748119/files/ICESat-2_orientation_2022.png
---
width: 85%
align: center
background-color: white
name: ICESat-2 spacecraft orientation
---
ICESat-2 spacecraft orientation (NSIDC)
```

### ICESat-2 Local Coordinate System

::::{grid} 1 1 2 2

:::{grid-item}
- Along-track coordinates, `x_atc`, are measured parallel to each RGT and are in reference to the equator
- Across-track coordinates, `y_atc`, are measured perpendicular to and in reference to the RGT
- Averaging Schemes:
  - Measurements can be averaged over a set along-track distance
  - Measurements can be averaged over a set number of photons and have a variable along-track length

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/ICESat-2_coordinates_2022.png
---
width: 100%
align: center
name: ICESat-2 coordinate system
---
ICESat-2 coordinate system (ATL06 ATBD)
```

:::

::::

```{div} text-center
:style: "height: 400px; display: flex; align-items: center; justify-content: center;"

# Part 2: Data Products
```

### ICESat-2 Data Production

```{image} https://zenodo.org/records/15748942/files/ICESat-2_data_production.png
:alt: ICESat-2 data production workflow
:width: 85%
:align: center
```


```{admonition} Data Production Keywords:
- **ATLAS:** Advanced Topographic Laser Altimeter System
- **ASAS:** ATLAS Science Algorithm Software
- **PGE:** Product Generation Executive
- **SIPS:** Science Investigator-led Processing System
- **SCF:** Science Computing Facility
```

### ICESat-2 Product Chart

```{image} https://zenodo.org/records/15748942/files/ASAS_product_chart.png
:alt: ICESat-2 ASAS product chart
:width: 85%
:align: center
```

### Granule Regions

Each orbit of ICESat-2 data is broken up into 14 granules in order to limit the overall file sizes and to reduce the number of files that need to be processed to create the higher-level science products

```{image} https://zenodo.org/records/15748119/files/ICESat-2_granules_global.png
:alt: ICESat-2 global granule regions
:width: 85%
:align: center
```

```{image} https://zenodo.org/records/15748119/files/ICESat-2_granules_polar.png
:alt: ICESat-2 polar granule regions
:width: 85%
:align: center
```

### File Naming Conventions

```
ATL[xx]_[yyyymmdd][hhmmss]_[tttt][cc][nn]_[rrr]_[vv].h5
```

- `xx`: ATLAS product number
- `yyyymmdd`: year, month and day of data acquisition
- `hhmmss`: start time, hour, minute, and second of data acquisition (UTC)
- `tttt`: Reference Ground Track (RGT, ranges from 1–1387)
- `cc`: Orbital Cycle (91-day period)
- `nn`: Granule number (ranges from 1–14, always 01 for atmosphere products)
- `rrr`: Data release number
- `vv`: Data version number

```{tip}
used for ATL03, ATL04, ATL06, ATL08, ATL09, ATL10, ATL12, ATL13, ATL16, ATL17, ATL19, ATL22 and ATL24
```

### File Naming Conventions: Sea Ice

```
ATL[xx]-[hh]_[yyyymmdd][hhmmss]_[tttt][cc][nn]_[rrr]_[vv].h5
```

- `xx`: ATLAS product number
- `hh`: Sea ice hemisphere flag (01=north, 02=south)
- `yyyymmdd`: year, month and day of data acquisition
- `hhmmss`: start time, hour, minute, and second of data acquisition (UTC)
- `tttt`: Reference Ground Track (RGT, ranges from 1–1387)
- `cc`: Orbital Cycle (91-day period)
- `nn`: Granule number (always 01 for sea ice products)
- `rrr`: Data release number
- `vv`: Data version number

```{tip}
used for ATL07, ATL10, ATL20, and ATL21
```

### ATL03: Global Geolocated Photon Data

::::{grid} 1 1 2 2

:::{grid-item}
**Contains:**
- Geolocation, time and elevation for all photons telemetered from ATLAS
- Photon classifications for each surface type
- Geophysical and atmospheric corrections
- Instrumental parameters

**Advantages:**
- Every photon is there, and every parameter
- Can derive information for all surface types

**Disadvantages:**
- Large and complex product
- Might require applying instrumental corrections

**Use if you want to:**
- Look at surfaces at a scale unresolved in higher-level products
- Look at processes the higher-level products were not designed to observe

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/atl03_photons_yapc.png
---
width: 100%
align: center
name: ATL03 photon data visualization
---
ATL03 photon data and YAPC classification
```

:::

### ATL04 and ATL09: Atmospheric Backscatter Profiles

**Contains:**
- Atmospheric layer heights and optical properties

**Advantages:**
- Much larger height window provided from the atmospheric data channel

**Disadvantages:**
- Relatively large file sizes

**Use if you want to:**
- Want to investigate cloud or suspended particle optical depths
- Visualize cloud returns or Antarctic blowing snow
- Want to try to understand atmospheric effects on photon ground returns

```{figure} https://zenodo.org/records/15748119/files/ess2920-fig-0011.jpg
---
width: 80%
align: center
name: Atmospheric backscatter profile
---
Atmospheric backscatter profiles from [Palm et al. (2021)](https://doi.org/10.1029/2020ea001470)
```

### ATL06: Land Ice Height Data

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- Overlapping 40-meter linear segments fit to land and land-ice photons
- Height error and segment quality estimates

**Advantages:**
- Lighter product than ATL03
- Provides estimated surface heights with cm-level corrections

**Disadvantages:**
- 40 meters is too coarse for some applications
- Only designed for single surface returns

**Use if you want to:**
- Make large-scale repeatable measurements of glaciers and ice sheets

:::

:::{grid-item}
```{figure} https://zenodo.org/records/15748119/files/ATL06_segment_model.png
---
width: 100%
align: center
name: ATL06 segment model
---
ATL06 segment model [(Smith et al., 2019)](https://doi.org/10.1016/j.rse.2019.111352)
```
:::


### ATL11: Slope-Corrected Land Ice Height Time Series

::::{grid} 1 1 2 2 

:::{grid-item}

**Contains:**
- 120-meter along-track segments for each beam pair corrected for across-track slope
- Crossover estimates from ATL06 at reference points

**Advantages:**
- Contains data for all cycles with along-track data following the Reference Ground Tracks (RGTs)
- Easy calculation of height change through time

**Disadvantages:**
- 120-m resolution is too coarse for some applications
- May not work well over complex surfaces

**Use if you want to:**
- Make large-scale estimates of glacier and ice sheet height change

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/ATL11_048311_006_pt2.png
---
width: 100%
align: center
name: ATL11 height time series
---
ATL11 height time series at an Antarctic grounding zone
```

:::

### ATL14 and ATL15: Gridded Land Ice Height and Height Change

**Contains:**
- ATL14: gridded digital elevation model (DEM) and height uncertainty at 100m posting
- ATL15: gridded land ice height change estimates at 1km, 10km, 20km, and 40km posting

**Advantages:**
- Gridded product combining all available along-track ATL11 data
- Simplifies volume change calculations using ICESat-2 data

**Disadvantages:**
- ATL14 estimates degrade where measurements are unavailable
- Quarter-annual temporal sampling might not be high enough for certain applications

**Use if you want to:**
- Use gridded estimates of height change for ice sheet models
- Start creating land ice mass balance estimates from ICESat-2
- Extract land ice height change estimates along transects

::::{grid} 1 1 2 2

:::{grid-item}
```{image} https://zenodo.org/records/15748119/files/Felikson_glacier0001_map.png
:alt: ATL15 glacier height change map
```
:::

:::{grid-item}
```{image} https://zenodo.org/records/15748119/files/Felikson_glacier0001_transect.png
:alt: ATL15 glacier height change transect
:width: 83%
```
:::

::::

`IS2view` *display of ATL15 height change data and extracted transect using glacier flowlines from [Felikson et al. (2020)](https://doi.org/10.5281/zenodo.4284759).*

### ATL07: Sea Ice Height Data

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- Along-track heights for sea ice and leads

**Advantages:**
- High precision (~2 cm) height retrievals from 150-photon aggregates
- Classifications for varying surface types (e.g. open water leads, sea ice)
- Provides auxiliary information such as surface roughness and retrieval quality flags

**Disadvantages:**
- Surface retrievals have varying length scales
- Surface type flagging is still in development

**Use if you want to:**
- Have base level surface heights for freeboard or surface process studies

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/kwok_2019_figure_2.jpg
---
width: 100%
align: center
name: ATL07 sea ice height data
---
ATL07 sea ice heights from [Kwok et al. (2019)](https://doi.org/10.1029/2019JC015486)
```
:::

::::

### ATL10: Sea Ice Freeboard Data

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- Along-track sea ice freeboard and surface heights
- Surface type flagging and ancillary information

**Advantages:**
- Lighter product than ATL07 with higher level freeboard and surface types

**Disadvantages:**
- Higher levels of missing/invalid data than ATL07 (low ice concentration, near-coastal)
- Varying length scales of retrievals
- Summer sea ice retrievals still under investigation (July 2022 field campaign)

**Use if you want to:**
- Use along-track freeboard retrievals
- Use a highly accurate product (3 cm or better over 25 km length scales)

:::

:::{grid-item}


```{figure} https://zenodo.org/records/15748119/files/april2019_gridded_cropped.png
---
width: 100%
align: center
name: ATL10 sea ice freeboard data
---
ATL10 sea ice freeboards from [Petty et al. (2020)](https://doi.org/10.1029/2019JC015764)
```
:::

::::

### ATL20: Gridded Sea Ice Freeboard Data

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- 25 km gridded sea ice freeboard at daily to monthly resolution

**Advantages:**
- Gridded product that is lighter than ATL10

**Disadvantages:**
- Coarse length scale, averages out the high resolution of the ICESat-2 data

**Use if you want to:**
- Look at gridded sea ice freeboard data for large-scale determination of sea ice change
- Merge with other coarse-resolution data such as passive microwave products

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/ATL20.png
---
width: 100%
align: center
name: ATL20 gridded freeboard data
---
ATL20 gridded freeboard from [Kwok et al. (2019)](https://doi.org/10.1029/2019JC015486)
```
:::

::::

### ATL21: Gridded Polar Sea Surface Height Data

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- 25 km gridded sea surface height anomalies for sea ice covered regions

**Advantages:**
- Gridded product that is lighter than ATL10
- Uses a sophisticated sea surface height retrieval algorithm to detect leads in polar oceans

**Disadvantages:**
- Coarse length scale, averages out the high resolution of the ICESat-2 data
- Only data from center strong beam available due to time and spatially varying biases

**Use if you want to:**
- Look at large-scale gridded sea surface height anomalies or derive dynamic ocean topography in polar regions

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/ATL21_cropped.png
---
width: 100%
align: center
name: ATL21 sea surface height data
---
ATL21 sea surface heights from [Bagnardi et al. (2021)](https://doi.org/10.1029/2021GL093155)
```

:::

::::

### ATL08: Land and Vegetation Height Data

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- Terrain surface and canopy heights from land photons

**Advantages:**
- Can handle surfaces with multiple returns (such as vegetated canopies)
- Provides photon-level classifications from the ATL08 algorithm

**Disadvantages:**
- Can produce less reliable results over sloping surfaces

**Use if you want to:**
- Detect multiple surfaces, such as vegetated canopies or supraglacial lakes
- Look at vegetated terrain and need to detect the ground

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/ATL08.png
---
width: 100%
align: center
name: ATL08 vegetation height data
---
ATL08 vegetation heights (recreated a figure from Amy Neuenschwander, UT Austin)
```
:::

::::

### ATL18: Gridded Land and Vegetation Height (in development)

**Contains:**
- Terrain and relative canopy heights at 1km resolution

**Advantages:**
- Uses EASE2.0 grids for compatibility with other datasets
- Will be updated annually

**Disadvantages:**
- Low spatial resolution limits creating a temporal change product

**Use if you want to:**
- Analyze large-scale vegetation and land surface change

```{figure} https://zenodo.org/records/15748119/files/ATL18_2024.png
---
width: 80%
align: center
name: ATL18 gridded vegetation height
---
ATL18 gridded vegetation height (provided by Amy Neuenschwander, UT Austin)
```

### ATL12: Ocean Surface Height Data

::::{grid} 1 1 2 2 

:::{grid-item}

**Contains:**
- Sea surface heights for oceans deeper than 10m
- Harmonic coefficients and statistics for waves
- Geophysical (e.g. sea state bias) corrections

**Advantages:**
- Average height estimates reduce the effects of correlated noise due to waves
- Also provides sea surface heights with cm-level corrections at spatial resolutions up to 10m

**Disadvantages:**
- Does not represent the sea surface in ice covered areas

**Use if you want to:**
- Detect the instantaneous sea surface height

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/grl62359-fig-0003-m.jpg
---
width: 100%
align: center
name: ATL12 ocean surface height comparison
---
Comparison of ATL12 and JASON-3 from [Buzzanga et al. (2021)](https://doi.org/10.1029/2020GL092327)
```
:::

::::

### ATL19 and ATL23: Gridded Dynamic Ocean Topography

::::{grid} 1 1 2 2

:::{grid-item}

**Contains:**
- Rasterized DOT at ¼° (mid-latitudes) and 25 km (polar) spatial resolution
- Monthly (ATL19) and tri-monthly (ATL23) temporal resolution

**Advantages:**
- Lighter product than ATL12
- Includes individual beam averages

**Disadvantages:**
- Lower temporal resolution than ATL12

**Use if you want to:**
- Calculate the average DOT over time
- Look at large-scale oceanographic features

:::

:::{grid-item}

```{figure} https://zenodo.org/records/15748119/files/moris4-220601-020-large.png
---
width: 100%
align: center
name: ATL19 dynamic ocean topography
---
ATL19 dynamic ocean topography
```

```{figure} https://zenodo.org/records/15748119/files/moris5-220601-020-large.png
---
width: 100%
align: center
name: ATL23 dynamic ocean topography
---
ATL23 dynamic ocean topography 
```

ATL19 and ATL23 DOT from Figures 4 and 5 of [Morison et al. (2022)](https://doi.org/10.1109/OCEANS47191.2022.9977076)


:::

::::

### Product Information at the National Snow and Ice Data Center (NSIDC)

- The NSIDC DAAC is the primary data manager for ICESat-2 data
  - On-prem data stores
  - Cloud-based data stores (AWS s3)
- Mission landing page for ICESat-2 → [https://nsidc.org/data/icesat-2](https://nsidc.org/data/icesat-2)
- Product landing pages (e.g. ATL03) → [https://nsidc.org/data/atl03](https://nsidc.org/data/atl03)

```{admonition} Each product landing page includes:
:class: tip

- User Guides
- Algorithm Theoretical Basis Documents (ATBDs)
- Data Dictionaries
- List of Known Issues
- Information for Data Access
```

```{div} text-center
:style: "height: 400px; display: flex; align-items: center; justify-content: center;"

# Part 3: Mission Status and Future
```

### ICESat-2 Mission Status

#### Future Mission Outlook
- Current Status: **Nominal**
- Performance metrics remain nominal and within mission requirements
- Over **2000** days in orbit
- Over **2 trillion** laser pulses fired
- Life-limiting factor is on-board fuel → dependent on solar activity

#### Mission Product Development
- Release-07 of along-track products to be released in mid-2025
- Along-Track Coastal and Nearshore Bathymetry (ATL24) released in 2025
- Gridded Land and Vegetation Height product (ATL18) in development
- Gridded Sea Ice Freeboard Quicklook product (ATL20-QL) in development
- Possible future standard products are under development

::::{grid} 1 1 2 2

:::{grid-item}
```{image} https://zenodo.org/records/15748119/files/ICESat-2_EOL_Nov2024.png
:width: 100%
:alt: ICESat-2 end of life projection
```
:::

:::{grid-item}
```{image} https://zenodo.org/records/15748119/files/ICESat-2_Propellant_Usage_Nov2024.png
:width: 85.4%
:alt: ICESat-2 propellant usage
```
:::

::::


```{admonition} Links
:class: tip

- **Website:** [https://icesat-2.gsfc.nasa.gov](https://icesat-2.gsfc.nasa.gov)
- **Data:** [https://nsidc.org/data/icesat-2](https://nsidc.org/data/icesat-2)
- **GitHub:** [https://github.com/icesat-2](https://github.com/icesat-2)
```
