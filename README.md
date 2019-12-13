# ETL_Project
ETL Project with Historical Military Data



We discovered our data source through Kaggle. We found an extremely comprehensive dataset with historical military data from 1600 - 1973 AD. Specifically, we wanted to explore weather data and its impact on battle wins, if any. 

We cleaned and merged three csv files - battles.csv, battle_actors.csv, and weather.csv. We needed to drop all columns we did not need, transform all NaN values to integers, and delete all duplicates. We deleted duplicate battle IDs because these duplicates contained start and end date weather information if battles went on for more than one day. We kept only start date weather information. We could not import the data  into pgAdmin without deleting these because the battle ID was our primary key. We merged the data into one dataframe on the battle IDs (ISQNO) that were common across all csv files.

Each battle had at least two actors but can have up to four - thus, there are inevitably some null values in our csv files. To work around this problem, we used the command DEFAULT ‘NULL’ to place a ‘null’ in any blank space in the table. We then manually imported the csv file. 
