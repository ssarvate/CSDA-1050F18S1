## CSDA1050

### Sprint 2


### Purpose of this Module

The objectives of this module are:

1. Implement refinements to the project that have come to light due to the EDA of sprint 1.
2. Consolidate the analytic and modelling techniques to be used in the project. That is consolidate the methodology.
3. Execute the methodology agreed upon.


### Refinements to the Project

After a review of sprint 1, in particular the visual of the red light camera geopoints alongside the accident geopoints on the map of Toronto as well as the plot of the accident geopoints by themselves, the initial general research question posed in the proposal has evolved into a more specific question as follows:

**Do the 77 red light cameras installed around the City of Toronto reduce the number of red light running accidents in the areas surrounding those intersections?**



### Pre-requisites for Running Notebook and Code

The follow packages need to be installed for this sprint:

    OSMnx

    folium

To do this, use the following command at the Anaconda prompt (notice that folium is installed as part of the OSMnx installation):

    conda install -c conda-forge osmnx
    
**Note:** During this process, the following packages will also be installed:

    altair
    
    branca
    
    folium
    
    geographiclib
    
    geopy
    
    vincent


### Data Used in this Analysis

**Red Light Camera Data** – List of red light cameras installed in the city of Toronto. This data can be found in The City of Toronto Open Data Catalogue. 

https://portal0.cf.opendata.inter.sandbox-toronto.ca/dataset/red-light-cameras/

**Red Light Accident Data** - This dataset is a subset of the Killed and Seriously Injured (KSI) dataset from 2008-2018. These events include any serious or fatal collision where red light running played a role in the collision. This dataset is collected by the Toronto Police Service and can be found on The Toronto Police Services Public Safety Data Portal.

http://data.torontopolice.on.ca/datasets/red-light/data

Both data files can be found in the data folder of this project.


### Methodology

We will be using the following methodology:

1. Interactive map visualisation of cameras geopoints alongside accidents geopoints using the folium package in Python. This will allow us to examine the red light cameras with respect to how the accidents are situated around them by drilling down to the intersection level.

2. Calculation of nearest accidents to each camera. We will calculate the distance (Euclidean) between each red light camera and each accident. The returned distance is based on the projection of the points (degrees in WGS84, meters in UTM). We will define a catchment area, which would ideally be decided by our client (in this case The City of Toronto). Accidents for each red light camera with distances that fall within this catchment area will be flagged and the details of these cameras and accidents printed for further review. **The present catchment area is defined as 1km**.



### Findings and Insights

**Note: Please download and run the sprint 2 notebook in order to see the interactive maps.**

Of the 263 red light running accidents, 98 of them are within a distance of 1km of the red light camera intersection, that is 37% of all red light running accidents occur within 1km of the intersection with a red light camera. Out of the 77 red light cameras installed currently, 37 of them had 0 accidents reported in the catchment area. The number of cameras reporting 1-10 accidents is 40. 

By looking at the interactive map of the red light camera markers alongside the accident markers we can clearly see that the downtown core of Toronto is a hotspot for accidents occurring in close vicinity of red lights cameras. In corroboration with the distance calculations we can see 3 important intersections in the downtown core caught in this process are:

**Camera ID 1249 (King & Jarvis)** - 8 accidents within the catchment area.

**Camera ID 1255 (Lower Jarvis & Esplanade)** - 10 accidents within catchment area.

**Camera ID 1259 (York & Lake Shore Blvd W)** - 6 accidents within the catchment area.

These 3 intersections account for almost 25% of the accidents within the defined catchment area.


By reviewing the distance calculations we find more red light camera IDs where 3 or more accidents are flagged within the catchment area:

**Camera ID 1234 (Dupont St Lansdowne Ave)** - 4 accidents within the catchment area.

**Camera ID 1235 (Dundas St E Jarvis St)** - 4 accidents within the catchment area.

**Camera ID 1240 (Eglinton Ave W Spadina Rd)** - 3 accidents within the catchment area.

**Camera ID 1241 (Eglinton Ave E Victoria Park Ave)** - 3 accidents within the catchment area.

**Camera ID 1242 (1242 Ellesmere Rd Kennedy Rd)** - 5 accidents within the catchment area.

**Camera ID 1246 (1246 Islington Ave The Westway)** - 3 accidents within the catchment area.

**Camera ID 1255 (Eglinton Ave W Spadina Rd)** - 3 accidents within the catchment area.

**Camera ID 1291 (Adelaide & Spadina)** - 3 accidents within the catchment area

If we add another intersection to the above list of hotspot intersections, camera id 1242 at Ellesmere Rd & Kennedy Rd with 5 accidents in the catchment area, these 4 intersections would account for almost 30% of the accidents within the defined catchment area.
