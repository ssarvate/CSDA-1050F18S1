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

**Note:** Installation should be done in the order listed above as the installation of some packages depend on other packages already being installed.

### Data Used in this Analysis

The following datasets will be initially explored in the EDA:

Red Light Camera Data – List of red light cameras installed in the city of Toronto. This data can be found in The City of Toronto Open Data Catalogue. 

https://portal0.cf.opendata.inter.sandbox-toronto.ca/dataset/red-light-cameras/

Red Light Accident Data - This dataset is a subset of the Killed and Seriously Injured (KSI) dataset from 2008-2018. These events include any serious or fatal collision where red light running played a role in the collision. This dataset is collected by the Toronto Police Service and can be found on The Toronto Police Services Public Safety Data Portal.

http://data.torontopolice.on.ca/datasets/red-light/data

In addition, a shape file along with its associated files are being used in order to plot the camera and accident geopoints on a street map of Toronto. This is the centerline map of Toronto.

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

-	The geopoints for each camera is plotted on a street map of Toronto (obtained from the open data portal of The City of Toronto). **Please see the notebook for this visualization**. This gives a visual representation of all the red light cameras around the city. 

### EDA for Red Light Accident Dataset (KSI)

-	This is a CSV dataset.

-	The dataset has 959 rows.

-	The dataset has 57 columns as follows:

	X - Latitude, **float64**

	Y - Longitude, **float64**

	Index_ - Unique Identifier, **int64**

	ACCNUM - Accident Number, **int64**

	YEAR - Year Accident Occurred, **int64**
	
	DATE - Date Accident Occurred, **object**

	TIME - Time Accident Occurred, **int64**

	Hour - Hour Accident Occurred, **int64**

	STREET1 - Street Accident Occurred, **object**

	STREET2 - Street Accident Occurred, **object**

	OFFSET - Distance and direction of the accident, **object**

	ROAD_CLASS - Road Classification, **object**

	District - City District, **object**

	LATITUDE - Latitude, **float64**
	
	LONGITUDE - Longitude, **float64**

	LOCCOORD - Location Coordinate, **object**

	ACCLOC - Accident Location, **object**

	TRAFFCTL - Traffic Control Type, **object**

	VISIBILITY - Environment Condition, **object**

	LIGHT - Light Condition, **object**

	RDSFCOND - Road Surface Condition, **object**

	ACCLASS - Classification of Accident, **object**

	IMPACTYPE - Initial Impact Type, **object**

	INVTYPE - Involvement Type, **object**

	INVAGE - Age of Involved Party, **object**

	INJURY - Severity of Injury, **object**

	FATAL_NO - Sequential Number, **int64**

	INITDIR - Initial Direction of Travel, **object**

	VEHTYPE - Type of Vehicle, **object**

	MANOEUVER - Vehicle Manouever, **object**

	DRIVACT - Apparent Driver Action, **object**

	DRIVCOND - Driver Condition, **object**

	PEDTYPE - Pedestrian Crash Type - detail, **object**

	PEDACT - Pedestrian Action, **object**

	PEDCOND - Condition of Pedestrian, **object**

	CYCLISTYPE - Cyclist Crash Type - detail, **object**

	CYCACT - Cyclist Action, **object**

	CYCCOND - Cyclist Condition, **object**

	PEDESTRIAN - Pedestrian Involved In Collision, **object**

	CYCLIST - Cyclists Involved in Collision, **object**

	AUTOMOBILE - Driver  Involved in Collision, **object**

	MOTORCYCLE - Motorcyclist  Involved in Collision, **object**

	TRUCK - Truck Driver  Involved in Collision, **object**

	TRSN_CITY_ - Transit or City Vehicle  Involved in Collision, **object**

	EMERG_VEH - Emergency Vehicle  Involved in Collision, **object**

	PASSENGER - Passenger Involved in Collision, **object**

	SPEEDING - Speeding Related Collision, **object**

	AG_DRIV - Aggressive and Distracted Driving Collision, **object**

	REDLIGHT - Red Light Related Collision, **object**

	ALCOHOL - Alcohol Related Collision, **object**

	DISABILITY - Medical or Physical Disability Related Collision, **object**

	Division - Police Division, **object**

	Ward_Name - City Ward, **float64**

	Ward_ID - City Ward Identificator, **float64**

	Hood_ID - Neighbourhood Identificator, **int64**

	Hood_Name - Neighbourhood Name, **float64**

	ObjectId - Object ID (Unique Identifier), **int64**
	
-	Data is missing for the Ward_Name, Ward_ID, and Hood_Name  columns for all rows.

-	On closer inspection of the data it was found that there are several rows per accident number (ACCNUM). In order to accurately visualize counts of accidents for  various attributes duplicates were dropped. There are **263** unique accidents in this dataset.

-	Various visualizations were done with this dataset to get a sense of the accidents **(please see notebook)**:

	**KSI by Year** – The number of red light accidents has generally decreased over the years, the following chart shows the number by year:

	YEAR
	
	2008------------34
	
	2009------------24
	
	2010------------23
	
	2011------------17
	
	2012------------29
	
	2013------------25
	
	2014------------26
	
	2015------------21
	
	2016------------20
	
	2017------------22
	
	2018------------22
	
	**KSI by Hour of Day** – This chart shows a peak  at 4pm and 6pm. There is a higher number of accidents at these times during the day.
	
	Hour
	
	0--------------12
	
	1---------------8
	
	2---------------4
	
	3--------------10
	
	4---------------1
	
	5--------------10
	
	6---------------9
	
	7--------------13
	
	8---------------8
	
	9--------------13
	
	10-------------13
	
	11-------------16
	
	12-------------13
	
	13--------------7
	
	14-------------14
	
	15-------------18
	
	16-------------21
	
	17--------------8
	
	18-------------21
	
	19--------------5
	
	20-------------18
	
	21-------------10
	
	22--------------6
	
	23--------------5
	
	**KSI by Age Group (age of involved party)** – Here we are looking at the age of the parties involved in the red light running accidents. There are peaks in the 20-24 and 45-49 age groups. But clearly traffic accidents effect all age groups from infants and toddlers to seniors, and red light running is no different.
	
	AGE GROUP
	
	0 to 4-----------1
	
	10 to 14---------1
	
	15 to 19--------12
	
	20 to 24--------27
	
	25 to 29--------17
	
	30 to 34--------17
	
	35 to 39--------16
	
	40 to 44--------19
	
	45 to 49--------26
	
	50 to 54--------23
	
	55 to 59--------10
	
	60 to 64--------22
	
	65 to 69--------12
	
	70 to 74---------6
	
	75 to 79---------7
	
	80 to 84---------6
	
	**KSI by Impact Type** – Approximately half of the red light running accidents are classified as angle impact type accidents, as we would expect. The turning movement category could also fall into this bucket.
	
	IMPACT TYPE
	
        Angle--------------------129
	
        Approaching----------------1
	
        Cyclist Collisions--------15
	
        Pedestrian Collisions-----58
	
        Rear End-------------------4
	
        Turning Movement----------56
	
	**KSI by Injury** – 80 out of the 263 red light running accidents resulted in either fatalities or serious injury. This is 30% of the total accidents, which is not an insignificant percentage looking at the cost of human life in these situations.
	
	INJURY
	
        Not Recorded------34
	
        Fatal-------------17
	
        Major-------------63
	
        Minimal-----------22
	
        Minor-------------31
	
        None--------------96
	
- 	This pandas dataframe was converted to a geopandas dataframe and an extra column was added, geometry, using the LONGITUDE and LATITUDE columns giving us a geopoint for each accident to map on the same shape file used to plot the cameras geopoints. **Please see the notebook for this visualization**. 
	
### EDA for Red Light Accident Dataset (KSI) and Red Light Camera Data

-	**Please see visualization in the notebook** of the camera geopoints along with the accident geopoints at the same time on the map of Torono.  By just looking at this plot, we can see that most of the accident sites are at intersections that don’t have red light cameras. However, there are some sites that are quite close to intersections that have red light cameras installed. 
