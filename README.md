<h1> Citibike Analytics <br> (Tableau Demonstration) </h1>

#### Overview:
This project utilized Tableau to analyze and discover phenomena contained within data from New York City's citi bike program.
The data is publicly available in the form of large CSV files (some with over 3 million rows each) on their website.
As each file contained only a single month's worth of trip information it was necessary to combine several together to uncover any meaningful information.
This, however, presented several challenges:
+ Citi bike changed the layout of their CSV files midyear so they could not be unioned together easily.
+ The data files often contained thousands of rows with incomplete or missing data.
+ There were many stations with incorrect latitudes and longitudes or station identifiers.
+ There were many stations that had more than one identifier associated with it.
+ Some bikes were rented and then later returned, but there was no information on where they were returned.
+ The amount of data for a full year's analysis was too large for Tableau Public to handle. 

Before beginning the analysis with Tableau, I decided to create a jupyter notebook to clean and correct some of the challenges in the trip data CSV files.
For the midyear format change, the notebook was able to transform files in either the old format or the new format into a modified more compact version of the newer format.
For stations with missing and/or incorrect station information, the notebook adjusted their identifiers, names, latitudes, and longitudes to match corresponding entries in a JSON file downloaded from citibike's station information API.
For the bikes with unknown return locations, the notebook assumed they were returned to the same stations they were rented from.

Because of the Tableau Public size limit, I constrained my analysis to only 6 months of data (January to June 2021).
My workbook contains one story, 3 dashboards, a station map, and 8 visualizations, all of which are fully interactive to allow user exploration.

The phenomena that was uncovered was not unexpected:
+ The bikes are used more in the higher rent areas of Manhattan and near to transportation hubs and tourist destinations.
+ The bikes are used more in warmer months than colder months.
+ The bikes are used more during daytime hours and significantly more during the evening commute / dinner delivery hours.
+ The average trip time and duration is small (probably because riders are penalized for keeping a bike longer than 30 minutes).
+ The percentage of rentals by Pay Per Trip riders is small, but it steadily increases as the months get warmer.

To examine the final analysis, access the Tableau workbook at the following link:  
https://public.tableau.com/views/CitiBikeAnalytics_16433147918130/CitiBikeStory?:language=en-US&publish=yes&:display_count=n&:origin=viz_share_link

To examine some of the cleaned data files that were used and/or the data cleaning jupyter notebook, their locations in this repository are indicated in the tree below:

#### Files/Folders:

+ *"citi_bike_tripdata_csv_file_cleanup.ipynb"* (program for cleaning raw citibike trip data csv files and converting them into a single format)
+ **"Image Files"** (this folder contains some image files used by the Tableau workbook) <br>
	- *"citibike-logo.png"*  <br>
	- *"citi-bike-station-bikes.jpg"* <br>
* **"Data Files"** (this folder contains some sample cleaned trip data files) <br>
	- *"JC-202101-citibike-tripdata-cleaned.csv"*
	- *"JC-202102-citibike-tripdata-cleaned"*
	- *"station_information.csv"*
	- *"station_information.json"*

(Please do not delete, move, rename, or alter!)

#### Screenshots:
<img src="Image Files/StationMap.jpg">
<img src="Image Files/BusiestStations.jpg">
<img src="Image Files/BusiestTimes.jpg">
<img src="Image Files/FarLong.jpg">
 
