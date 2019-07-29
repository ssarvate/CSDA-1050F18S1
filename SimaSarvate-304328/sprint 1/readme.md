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

### Findings and Insights

### EDA for Red Light Cameras Dataset

-	This is a GeoJSON dataset.

-	The dataset has 77 rows (1 row for each red light camera installed in Toronto).

-	The dataset has 11 columns as follows:

	_id - unique row identifier for Open Data database, **int64**
  
	INTERSECTION_ID – intersection id, **int64** 
  
	LINEAR_NAME_FULL_1 – name of first street of intersection, **object** 
  
	LINEAR_NAME_FULL_2 – name of second street of intersection , **object**
  
	ID  - **int64**        
  
	X - **object** 
  
	Y - **object**
  
  LONGITUDE – longitude, **float64**  
  
	LATITUDE  - latitude, **float64**   
  
	OBJECTID – **int64**         
  
	geometry – coordinate data point, **object (shapely.geometry.point.Point)**
  
-	The columns  that are important for our analysis are:

INTERSECTION_ID

LINEAR_NAME_FULL_1

LINEAR_NAME_FULL_2

LONGITUDE

LATITUDE

geometry

-	There is some missing data but only in the X and Y columns. These columns are not important for our analysis.  

-	The geopoints for each camera is plotted on a street map of Toronto (obtained from the open data portal of The City of Toronto). **Please see the notebook for this visualization**. This gives a visual representation of all the red light cameras around the city. However, the shape file used in this visualization does not show the level of detail that would be preferred in this situation. A little more detail and interactivity at the intersection level is required in this analysis. A search is currently underway to find a better shape file for The City of Toronto.





