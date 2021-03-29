## Data Modeling with Cassandra

### Purpose of the project

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analysis team is particularly interested in understanding what songs users are listening to. Currently, there is no easy way to query the data to generate the results, since the data reside in a directory of CSV files on user activity on the app.

### Results achieved

Three different tables were modelled based on below queries.

#### 1. The below query gives us the artist, song title and song's length in the music app history that was heard during sessionId = 338, and itemInSession  = 4 and a table music_app_hist is modelled based on the query.
>SELECT artist_name,title,length 
FROM music_app_hist 
WHERE sessionId = 338 AND itemInSession = 4

#### 2. The below query gives us the name of artist, song (sorted by itemInSession) and user (first and last name) for userid = 10, sessionid = 182 and table music_app_hist1 is modelled based on the query.
>SELECT artist_name,title,firstname,lastname
FROM music_app_hist1 
WHERE userid = 10 AND sessionid = 182

#### 3. The below query gives us every user name (first and last) in my music app history who listened to the song 'All Hands Against His Own'
>SELECT firstname,lastname
FROM music_app_hist1 
WHERE title = 'All Hands Against His Own'

### Files Description

> Data_modelling_with_Cassandra.ipynb - 1. ETL pipeline to preprocess csv files in event_data folder and create event_datafile_new.csv file as single input file 2. Create table based on modelled queries in the notebook 

