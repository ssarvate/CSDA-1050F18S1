## CSDA1050

### Sprint 1

This module contains the Exploratory Data Analysis for this project.

### Purpose of this Module

The objectives of this module are:
1. Gather data that is pertinent to the analysis of the research question.
2. Prepare data for exploratory data analysis.
3. Do exploratory data analysis and report findings and insights.

### Pre-requisites for Running Notebook and Code

Python v3

The following packages must be installed for this project:

rtree

gdal

fiona

shapely

geopandas

pysal

missingno

**Note:** Installation should be done in the order listed above as the installation of some packages depend on other packages already being installed.

### Data Used in this Analysis

The following datasets will be initially explored in the EDA:

Red Light Camera Data – List of red light cameras installed in the city of Toronto. This data can be found in The City of Toronto Open Data Catalogue. 

https://portal0.cf.opendata.inter.sandbox-toronto.ca/dataset/red-light-cameras/

Red Light Accident Data - This dataset is a subset of the Killed and Seriously Injured (KSI) dataset from 2008-2018. These events include any serious or fatal collision where red light running played a role in the collision. This dataset is collected by the Toronto Police Service and can be found on The Toronto Police Services Public Safety Data Portal.

http://data.torontopolice.on.ca/datasets/red-light/data

Other datasets that may be considered for the EDA after the initial EDA of the above 2 datsets include the following subsets of the KSI (Killed and Seriously Injured) dataset:

Automobile

Speeding

Pedestrians

Cyclist

Aggressive Driving

Passenger

Fatal Collisions

In addition, a shape file along with its associated files are being used in order to plot the camera and accident geopoints on a street map of Toronto. 

All data files can be found in the data folder of this project.




