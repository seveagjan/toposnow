# toposnow

The toposnow project investigates the topographic control on summer snow cover (SSC) in the Dry Andes with Landsat-9 and SRTM elevation data.
It follows the central research question on the relationship between SSC distribution and terrain parameters in arid high mountain areas. The Cordón del Plata mountain range is such a mountain range that is characterized by an arid climate and a spatially fragmented continous snow cover, and will serve as a test site for this project. But why is knowledge about the spatial distribution of snow cover so important?

## Introduction

Seasonal snow cover is a major contributor to the regional hydrological cycle by supplying rivers with meltwater that reach far beyond high-mountain regions. Especially in areas of the world that do not receive that much freshwater through precipitation, such as the Central Cordón del Plata (1000; et al.), snow and ice melt processes have a higher significance for local water supply than else where (Passang et al. 2022). As water is a limited and precious resource in these regions, efficient water management is key. In former studies, it was made evident that topographic parameters like elevation, slope and aspect have a major impact on the spatial distribution of snow cover as they govern the amount of incoming solar radiation (Yadav et al. 2021, Saydi a. Ding 2020). Therefore, a better understanding and prediction of spatio-temporal snow cover dynamics requires information on the impact of regional topography.

In this study, this information was obtained by the GIS-based processing of digital elevation data of a section within the Cordón del Plata mountain range in Western Argentina. Besides the raw elevation data, the following terrain parameters, that have an potential influence on local snow cover, were computed in SAGA GIS: 

- Slope aspect
- Slope gradient
- Topographic Position Index (TPI)
- Topographic Roughness Index (TRI)
- Topographic Convexity Index (TCI)
- Wind Shelter Index (WSI)
- Potential Incoming Solar Radiation (PISR)

The relationship of these terrain parameters with SSC was examined by conducting a correlation analysis with optical satellite data acquired by Landsat-9 from the hemispheric summer season. The following outcomes were expected: 

- SSC, represented by NDSI, shows a correlation with the different terrain parameters, for example: Snow cover is less distributed across South-exposed slopes, in lower elevations as well as in steep terrain.

## GIS workflow

![gisworkflow](https://user-images.githubusercontent.com/130289392/232329687-0880f44f-6b49-4d91-8481-c11c24ca568b.jpg)


## Test site

![toposnow_sa](https://user-images.githubusercontent.com/130289392/232322332-4da06a48-3942-433b-badd-313781c498e0.jpeg)



### Topography

![toposnow_topndsi](https://user-images.githubusercontent.com/130289392/232324638-73313ed9-6e32-46fc-82a7-84513c4816e3.jpeg)


### Summer snow cover extent

![toposnow_ssc](https://user-images.githubusercontent.com/130289392/232328505-5af3bc34-c971-4e18-8a2c-c69e737a99df.jpeg)


## Correlation between SSC and topography

![plot_ndsielevation](https://user-images.githubusercontent.com/130289392/232330086-bf93d2f7-1bbc-42d8-8275-aa8ae207febb.png)


## Discussion

## References

### Data

### Literature
