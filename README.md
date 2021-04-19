Project: Data Modeling with Postgres

A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. They'd like a data engineer to create a Postgres database with tables designed to optimize queries on song play analysis.

Schema for Song Play Analysis
To create the star schema for this analytical goals, firstly, I process and perform ETL on the dataset called song_data to create songs and artists these two dimensional tables. Secondly, I process and perform ETL on the dataset called log_data to create time and users these two dimensional tables as well as songplays this fact table. Using the song and log datasets, I'll need to create a star schema optimized for queries on song play analysis. This includes the following tables.

Fact Table
songplays - records in log data associated with song plays i.e. records with page NextSong
songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
Dimension Tables
users - users in the app
user_id, first_name, last_name, gender, level
songs - songs in music database
song_id, title, artist_id, year, duration
artists - artists in music database
artist_id, name, location, latitude, longitude
time - timestamps of records in songplays broken down into specific units
start_time, hour, day, week, month, year, weekday

The project includes six files:

test.ipynb displays the first few rows of each table to check the database.
create_tables.py drops and creates the tables. Run this file to reset the tables before each time running ETL scripts.
etl.ipynb reads and processes a single file from song_data and log_data and loads the data into the tables. This notebook contains detailed instructions on the ETL process for each of the tables.
etl.py reads and processes files from song_data and log_data and loads them into the tables. 
sql_queries.py contains all sql queries, and is imported into the last three files above.
README.md provides discussion on this project.
