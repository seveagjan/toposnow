# toposnow

The toposnow project investigates the topographic control on summer snow cover (SSC) in the Dry Andes with Landsat-9 and SRTM elevation data.
It follows the central research question on the relationship between SSC distribution and terrain parameters in arid high mountain areas. The Cordón del Plata in the Central Andes is such a mountain range that is characterized by an arid climate and a spatially fragmented continuous snow cover, and will serve as a test site for this project. But why is knowledge about the spatial distribution of snow cover so important?

## Introduction

Seasonal snow cover is a major contributor to the regional hydrological cycle by supplying rivers with meltwater that reach far beyond high-mountain regions. Especially in areas of the world that do not receive that much freshwater through precipitation, such as the Cordón del Plata arc (about 500 mm/a; Trombotto-Liaudat et al. 2020), snow and ice melt have a higher significance for river discharge and water supply than else where (Passang et al. 2022). As water is a limited and precious resource in these regions, efficient water management is key. In former studies, it was made evident that topographic parameters like elevation, slope and aspect have a major impact on the spatial distribution of snow cover as they govern the amount of incoming solar radiation (Singh Yadav et al. 2021, Saydi a. Ding 2020, Shaw et al. 2020). Therefore, a better understanding and prediction of spatio-temporal snow cover dynamics requires information on the impact of regional topography.

Here, this information was obtained by the GIS-based processing of digital elevation data of a section within the Cordón del Plata mountain range in Western Argentina. Besides the raw elevation data, the following terrain parameters, that have a potential influence on local snow cover, were computed in SAGA GIS: 

- Slope aspect
- Slope gradient
- Topographic Position Index (TPI)
- Potential Incoming Solar Radiation (PISR)

The relationship of these terrain parameters with SSC was explored by conducting a correlation analysis with optical satellite data acquired by Landsat-9 from the hemispheric summer season. The following outcomes were expected: 

- SSC, represented by the Normalized Difference Snow Index (NDSI), shows a correlation with the different terrain parameters, for example: Snow cover is less distributed across south-exposed slopes, in lower elevations as well as in steep terrain.

## Test site

The test site, with a size of about 1500 sqkm, is located in the Andes of Mendoza characterized by a highly complex terrain with elevations ranging from 2000 to over 5700m a.s.l.. The extensive winter snow cover usually vanishes with the onset of the summer season making snow patches only remaining in topographically preferable sites (Trombotto-Liaudad et al. 2020).

![toposnow_sa](https://user-images.githubusercontent.com/130289392/232322332-4da06a48-3942-433b-badd-313781c498e0.jpeg)


## GIS workflow

The NDSI calculation of the Landsat data was conducted in QGIS in the raster calculator. To exclude glacierized areas from the analysis, respective outlines taken from the Randolph Glacier Inventory (RGI) were taken as a mask and applied to all used data. The automatic computation of the before mentioned terrain indices was done in SAGA GIS based on the built-in terrain analysis tools that also provides a spatial computation of terrain-meteorological parameters like PISR or WSI. In QGIS, the NDSI data was resampled to 30 meters pixel resolution to match the SRTM data. After that, a 200x200m point grid was produced that collects samples from pixels of NDSI and terrain indices. Sample points covering areas below 4000m a.s.l. were removed as this was observed to be the altitudinal limit of SSC within the study region (based on interpretation of the NDSI data). In the end the correlation data consisted of 1262 samples from snow covered and snow free pixels.      

![gisworkflow](https://user-images.githubusercontent.com/130289392/232329687-0880f44f-6b49-4d91-8481-c11c24ca568b.jpg)

For the correlation analysis, the sample values for the terrain indices were individually plotted against corresponding NDSI values. This was done using the QGIS plugin 'DataPlotly'. In a next step, spatial statistics were extracted from the snow covered areas for each terrain index. Snow covered areas were defined by NDSI values above 0.3 and were polygonized in QGIS as a base for the extraction of zonal statistics. 

## Results

### Topography

![toposnow_topndsi](https://user-images.githubusercontent.com/130289392/232324638-73313ed9-6e32-46fc-82a7-84513c4816e3.jpeg)


### Summer snow cover extent

![toposnow_ssc](https://user-images.githubusercontent.com/130289392/232328505-5af3bc34-c971-4e18-8a2c-c69e737a99df.jpeg)


### Correlation between SSC and topography

The plotting of NDSI against terrain indices revealed no correlation for a majority of the cases, except elevation that explained up to 43 percent of the variability in NDSI above 4000m a.s.l (see Figure below).

![plot_ndsielevation](https://user-images.githubusercontent.com/130289392/232330086-bf93d2f7-1bbc-42d8-8275-aa8ae207febb.png)

The statistical analysis showed that snow-covered areas were found on average on slopes with south to south-west orientation. Mean slope gradient of snow-covered areas was at about 29 degrees and elevation average at 4920m a.s.l. TPI showed an average of 0.05 corresponding to rather straight slopes, PISR was at 7.62 kWh/sqm on average.  

## Conclusion

The project aimed to explore the potential evidence of topographic control on SSC in an arid high-mountain region with Landsat and SRTM elevation data by combining geoprocessing tools of SAGA and QGIS. It was shown that the investigated terrain parameters were not able to derive the relationship between snow cover and topography as stated in other research. This might be attributed to the fact that spatio-temporal snow cover dynamics are very complex and governed by other factors that are hardly inferable with remote sensing alone, such as redistribution processes through wind or micro-meteorology. However, topographic parameters remain limiting factors of SSC extent and should be included in future investigations of snow cover dynamics.  

## References

### Data

Landsat-9 OLI/TIRS C2 Level-2 product (LC09_L2SP_232083_20230103_20230315_02_T1_SR and SRTM 1 Arc-Second Global DEM data were downloaded from the USGS EarthExplorer website (https://earthexplorer.usgs.gov).

Glacier outlines were obtained from the Randolph Glacier Inventory (RGI) version 6.0.0 via the NSIDC (https://daacdata.apps.nsidc.org/pub/DATASETS/nsidc0770_rgi_v6/). 

### Literature

Passang, S., Schmidt, S., Nüsser, M. Topographical Impact on Snow Cover Distribution in the Trans-Himalayan Region of Ladakh, India. Geosciences (2022), 12(8).

Saydi, M., Ding, J.-l. Impacts of topographic factors on regional snow cover characteristics. Water Science and Engineering (2020), 13(3).

Shaw, T.E., Deschamps-Berger, C., Gascoin, S., McPhee, J. Monitoring Spatial and Temporal Differences in Andean Snow Depth derived from Satellite Tri-Stereo Photogrammetry. Frontiers in Earth Science (2020), 8.

Singh Yadav, J., Misra, A., Dobhal, D.P., Yadav, R.B.S., Upadhyay, R. Snow cover mapping, topographic controls and integration of meteorological data sets in Din-Gad Basin, Central Himalaya.

Trombotto-Liaudat, D., Bottegal, E. Recent evolution of the active layer in the Morenas Coloradas rock glacier, Central Andes, Mendoza, Argentina and its relation with kinematics. Geographical Research Letters (2020), 46(1).
