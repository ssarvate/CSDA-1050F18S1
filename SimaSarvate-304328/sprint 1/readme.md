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

### EDA for Red Light Accident Dataset (KSI)

-	This is a CSV dataset.

-	The dataset has 959 rows.

-	The dataset has 57 columns as follows:

	X             **float64**

	Y             **float64**

	Index_         **int64**

	ACCNUM          **int64**

	YEAR            **int64**

	DATE           **object**

	TIME            **int64**

	Hour            **int64**

	STREET1        **object**

	STREET2        **object**

	OFFSET         **object**

	ROAD_CLASS     **object**

	District       **object**

	LATITUDE      **float64**

	LONGITUDE     **float64**

	LOCCOORD       **object**

	ACCLOC         **object**

	TRAFFCTL       **object**

	VISIBILITY     **object**

	LIGHT          **object**

	RDSFCOND       **object**

	ACCLASS        **object**

	IMPACTYPE      **object**

	INVTYPE        **object**

	INVAGE         **object**

	INJURY         **object**

	FATAL_NO        **int64**

	INITDIR        **object**

	VEHTYPE        **object**

	MANOEUVER      **object**

	DRIVACT        **object**

	DRIVCOND       **object**

	PEDTYPE        **object**

	PEDACT         **object**

	PEDCOND        **object**

	CYCLISTYPE     **object**

	CYCACT         **object**

	CYCCOND        **object**

	PEDESTRIAN     **object**

	CYCLIST        **object**

	AUTOMOBILE     **object**

	MOTORCYCLE     **object**

	TRUCK          **object**

	TRSN_CITY_     **object**

	EMERG_VEH      **object**

	PASSENGER      **object**

	SPEEDING       **object**

	AG_DRIV        **object**

	REDLIGHT       **object**

	ALCOHOL        **object**

	DISABILITY     **object**

	Division       **object**

	Ward_Name     **float64**

	Ward_ID       **float64**

	Hood_ID         **int64**

	Hood_Name     **float64**

	ObjectId        **int64**
	
-	Data is missing for the Ward_Name, Ward_ID, and Hood_Name  columns for all rows.

-	On closer inspection of the data it was found that there are several rows per accident number (ACCNUM). In order to accurately visual counts of accidents for  various attributes duplicates were dropped. There are **263** unique accidents in this dataset.

-	Various visualizations were done with this dataset to get a sense of the accidents (please see notebook):

	**KSI by Year** – The number of red light accidents has generally decreased over the years, the following chart shows the number by year:

	YEAR
	
	2008    	34
	
	2009   		24
	
	2010    	23
	
	2011    	17
	
	2012    	29
	
	2013    	25
	
	2014    	26
	
	2015    	21
	
	2016    	20
	
	2017    	22
	
	2018    	22
	
	**KSI by Hour of Day** – This chart shows a peak  at 4pm and 6pm.
	
	Hour
	
	0     		12
	
	1      		8
	
	2      		4
	
	3     		10
	
	4      		1
	
	5     		10
	
	6      		9
	
	7     		13
	
	8      		8
	
	9     		13
	
	10    		13
	
	11    		16
	
	12    		13
	
	13    		 7
	
	14    		14
	
	15    		18
	
	16    		21
	
	17     		8
	
	18    		21
	
	19     		5
	
	20    		18
	
	21    		10
	
	22     		6
	
	23     		5
	
	**KSI by Age Group (age of the red light runner)** – Here we got some unexpected results. There were counts in outlying age groups. For example, there was 1 accident classified in each of the age groups 0-4, 10-14, and over 95. These could be due to human (data input) error.
	
	AGE GROUP
	
	0 to 4      	 1
	
	10 to 14     	 1
	
	15 to 19   	 12
	
	20 to 24    	 27
	
	25 to 29    	 17
	
	30 to 34   	 17
	
	35 to 39    	 16
	
	40 to 44   	 19
	
	45 to 49   	 26
	
	50 to 54    	 23
	
	55 to 59   	 10
	
	60 to 64   	 22
	
	65 to 69   	 12
	
	70 to 74    	 6
	
	75 to 79    	 7
	
	80 to 84    	 6
	
	85 to 89    	 2
	
	Over 95     	 1
	
	unknown    	 38

	This pandas dataframe was converted to a geopandas dataframe and an extra column was added, geometry, using the LONGITUDE and LATITUDE columns giving us a geopoint for each accident to map on the same shape file used to plot the cameras geopoints. **Please see the notebook for this visualization**. Again, it is mentioned that another more suitable shape file is needed which would allow for a higher degree of insights.










