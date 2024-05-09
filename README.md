# Analysis of Pedestrian Safety in New York City
"Analysis of Pedestrian Safety in NYC" is our Custom Final Project for the class Data Visualization and Machine Learning. In this project, we aim to focus our attention on pedestrian injuries and fatalities for injuries taking place on sidewalks.

Urban environments present complex challenges for pedestrian safety, particularly in densely populated areas like New York City. This study explores the spatial distribution and temporal dynamics of vehicle-pedestrian collisions in New York, focusing on high-risk areas such as sidewalks and crosswalks. Leveraging the high-resolution Tile2Net tool, we map pedestrian infrastructure and integrate it with detailed collision data from the NYPD, as provided by NYC Open Data. This paper contributes a novel integration of semantic segmentation outputs with extensive urban collision records, applying machine learning techniques such as clustering and SARIMAX forecasting to identify patterns and predict collision severities. Our findings highlight significant spatial correlations and temporal trends in collision data, offering insights into risk factors and potential preventive measures. However, limitations due to data completeness and reliance on public datasets are acknowledged. Future work will aim to incorporate additional variables like weather conditions and traffic volume, expand the geographic scope of the study, and develop real-time data analysis capabilities to enhance urban safety planning.

## Methodology
This repository contains the code and miscelleneous files associated with this project. All associated data can be found at our [Google Drive Page](https://drive.google.com/drive/folders/1zV8nrWAy6M-6Nqk79x9HWR8P9WRCwkOM?usp=drive_link), where the zip files include the respective datasets stored by year, or the various versions of the reduced dataset.

### Preprocessing

The work done in preprocessing is contained in the **Data Cleaning** folder. The steps taken in preprocessing are highlighted in _data_readme.txt_. All json files contains pulled information from the GeopPy Nominatim API to allow for quicker processing.

- Proprocessing and Cleaning.ipynb: This notebook contains all preprocessing and cleaning work as described in the paper and the data textfile.

### Exploratory Data Analysis

While the majority of the work done in this section is contained in the dashboard, some preliminary analysis is also done in _Data Cleaning\minimal_eda.ipynb_.

- Exploratory_Dashboard.ipynb: This file contains the code used to create the interactive dashboard for data exploration after cleaning. When run, this dashboard generates at a local url that can be accessed using any browser. An example of the dashboard is given below:
![Exploratory Data Analysis](https://github.com/AradhitaB/pedestrian-crash-visAnalysis/assets/40179298/c8c6e199-d76c-49c5-b9d5-8c4489ece2dc)

### Time Series Analysis

- Time Series Analysis.ipynb: This ipynb file run all the time series analysis for the project, including exploratory data analysis plots, seasonality, stationarity, SARIMAX, and injury prediction
  
![Screenshot 2024-05-08 204319](https://github.com/AradhitaB/pedestrian-crash-visAnalysis/assets/39420775/3b4989ad-92a2-4bfb-b773-303d1e8e8c12)
![Screenshot 2024-05-08 204808](https://github.com/AradhitaB/pedestrian-crash-visAnalysis/assets/39420775/c487e901-3e20-4f03-8718-3dd475a8c25a)

- Injury Prediction Case Study:
![Screenshot 2024-05-08 193004](https://github.com/AradhitaB/pedestrian-crash-visAnalysis/assets/39420775/ff2746c4-8b84-467f-877a-aba8ae247f3d)


### Clustering

The work done in clustering is located in the **Clustering** folder. 

- Dimensionality_Reduction.ipynb: This file contains the code to perform our dimensionality reduction analysis. Some key highlights of our analysis are shown in the image below:
![Dimensionality Reduction](https://github.com/AradhitaB/pedestrian-crash-visAnalysis/assets/40179298/54804a68-72cf-4281-b730-bd23720d7941)
- Clustering_*.ipynb: These files contain the Elbow analysis, MiniBatchKMeans Clustering, Surrogate Model training and SHAP analysis under the three settings described in the report. These settings are 1: All Cleaned Data, 2: All Cleaned Data with at least one Injury, 3: PCA reduced data with at least one injury.
- Visual analysis for the clustering output from setting 1 can be seen at [Our Observable Page](https://observablehq.com/@aradhita-bhandari-ws/project-clustering-visualization#dataloader)

### ArcGIS
  
- Manhattan Topographic Map.vtpk: ArcGIS file of lower Manhattan. The tile2net polygon data is presented in three different colors: coral for road, green for sidewalk, and blue for crosswalk. The collision data is presented with color and size coding: yellow for injuries, red for deaths, and size for the number of people effected in one collision
  ![ArcGIS Map](https://github.com/AradhitaB/pedestrian-crash-visAnalysis/assets/39420775/6ec59406-6c3a-440e-b297-b309a07fbcee)

