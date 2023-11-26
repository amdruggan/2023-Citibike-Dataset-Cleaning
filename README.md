# 2023-Citibike-Dataset-Cleaning
Process to merge and clean monthly CitiBike datasets into clean CSVs storing ride and station info separately for easy DB/Tableau implementation. 

### Starting files:
The starting files, which retain the naming convention from the CitiBikeNYC System Data page (https://citibikenyc.com/system-data) are included in the repository.

### Data Processing:
Data processing was complete using the pandas and glob libraries. This was done in the Jupyter notebook titled 'citi_bike_merge.ipynb'. 

All data was pulled in and merged into a dataframe, which then was used to generate stations_df and ride_df DataFrames respectively. Those dataframes have the following columns:

stations_df:
* station_ID (PK, varchar)
* name (varchar)
* station_lat (float)
* station_lng (float)

ride_df:
* ride_ID (PK, varchar)
* rideable_type (varchar)
* start_time (datetime)
* end_time (datetime)
* start_station_id (varchar, FK -> stations_df.station_ID)
* end_station_id (varchar, FK -> stations_df.station_ID)
* member (varchar)

These are then exported to the two remaining CSV files in the repository, namely ride_df to 'citibike_rides_2023.csv' and stations_df to 'citibike_stations_2023.csv'.