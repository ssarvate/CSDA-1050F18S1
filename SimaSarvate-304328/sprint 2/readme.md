## CSDA1050

### Sprint 2

### Purpose of this Module
This module contains:
1.	The refinements to the project due to findings of the EDA in sprint 1.
2.	The main analysis and modelling for the project.

## The objectives of this module are:
1. Implement refinements to the project that have come to light due to the EDA of sprint 1.
2. Consolidate the analytic and modelling techniques to be used in the project. That is consolidate the methodology.
3. Execute the methodology agreed upon.

### Refinements to the Project
After a review of sprint 1, in particular the visual of the red light camera geopoints alongside the accident geopoints on the map of Toronto as well as the plot of the accident geopoints by themselves, the initial general research question posed in the proposal has evolved into a more specific question as follows:
Do the 77 red light cameras installed around the City of Toronto reduce the number of red light running accidents in the areas surrounding those intersections?



### Pre-requisites for Running Notebook and Code
The follow packages need to be installed for this sprint:
OSMnx
folium

To do this, use the following command at the Anaconda prompt (notice that folium is installed as part of the OSMnx installation):
conda install -c conda-forge osmnx
Note: During this process, the following packages will also be installed:
altair
branca
folium
geographiclib
geopy
vincent

### Data Used in this Analysis
The following datasets will be initially explored in the EDA:
Red Light Camera Data – List of red light cameras installed in the city of Toronto. This data can be found in The City of Toronto Open Data Catalogue. 
https://portal0.cf.opendata.inter.sandbox-toronto.ca/dataset/red-light-cameras/
Red Light Accident Data - This dataset is a subset of the Killed and Seriously Injured (KSI) dataset from 2008-2018. These events include any serious or fatal collision where red light running played a role in the collision. This dataset is collected by the Toronto Police Service and can be found on The Toronto Police Services Public Safety Data Portal.
http://data.torontopolice.on.ca/datasets/red-light/data

