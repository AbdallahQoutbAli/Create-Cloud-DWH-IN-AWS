# Data-Engineer-Nanodegree-Projects-Udacity
Projects done in the [Data Engineer Nanodegree by Udacity.com](https://www.udacity.com/course/data-engineer-nanodegree--nd027)

## Course 2: Cloud Data Warehouses
### Introduction to the Data Warehouses
- Understand Data Warehousing architecture
- Run an ETL process to denormalize a database (3NF to Star)
- Create an OLAP cube from facts and dimensions
- Compare columnar vs. row oriented approaches

### Introduction to the Cloud with AWS
- Understand cloud computing
- Create an AWS account and understand their services
- Set up Amazon S3, IAM, VPC, EC2, RDS PostgreSQL

### Implementing Data Warehouses on AWS
- Identify components of the Redshift architecture
- Run ETL process to extract data from S3 into Redshift
- Set up AWS infrastructure using Infrastructure as Code (IaC)
- Design an optimized table by selecting the appropriate distribution style and sorting key


### Project  Introduction 
<pr>
A music streaming startup, Sparkify, has grown their user base and song database and want to move their processes and data onto the cloud. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

As their data engineer, you are tasked with building an ETL pipeline that extracts their data from S3, stages them in Redshift, and transforms data into a set of dimensional tables for their analytics team to continue finding insights into what songs their users are listening to.
</pr>

![image](https://user-images.githubusercontent.com/47276503/220912403-e8721f79-310f-423c-82dd-c368663f6f29.png)



# STG Datasets : 

### Song Dataset

The first dataset is a subset of real data from the Million Song Dataset. Each file is in JSON format and contains metadata about a song and the artist of that song. The files are partitioned by the first three letters of each song's track ID. For example, here are file paths to two files in this dataset.
example of what a single song file, TRAABJL12903CDCF1A.json, looks like.

~~~ sql
{"num_songs": 1, "artist_id": "ARJIE2Y1187B994AB7", "artist_latitude": null, "artist_longitude": null, "artist_location": "", "artist_name": "Line Renaud", "song_id": "SOUPIRU12A6D4FA1E1", "title": "Der Kleine Dompfaff", "duration": 152.92036, "year": 0} 
~~~

### Log Dataset
The second dataset consists of log files in JSON format generated by this event simulator based on the songs in the dataset above. These simulate app activity logs from an imaginary music streaming app based on configuration settings.

And below is an example of what the data in a log file 
 ![image](https://user-images.githubusercontent.com/47276503/220912697-993c2d91-0903-4949-bc87-a5a88a35680e.png)




# DWH Schema 

 **Fact Table**
  - **songplays**:  Columns: *songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent*
- **Dimension Tables**
  - **users**: users in the app. Columns: *user_id, first_name, last_name, gender, level*
  - **songs**: songs in music database. Columns: *song_id, title, artist_id, year, duration*
  - **artists**: artists in music database. Columns: *artist_id, name, location, latitude, longitude*
  - **time**: timestamps of records in songplays broken down into specific units. Columns: *start_time, hour, day, week, month, year, weekday*

#  The project template
   
The project template includes four files:

 **create_table.py** :*is where you'll create your fact and dimension tables for the star schema in Redshift.* <br>
 **etl.py** :*is where you'll load data from S3 into staging tables on Redshift and then process that data into your analytics tables on Redshift.*  <br>
 **sql_queries.py** :*is where you'll define you SQL statements, which will be imported into the two other files above.* <br>
 **README.md** :*is where you'll provide discussion on your process and decisions for this ETL pipeline.* <br>
  
# How To run Project 

-1 Load your AWS Information into file dwh.cfg <br>
-2 Run Create_tables.py <br>
-3 Run etl.py  <br>
-4 run Result_check.py <br>
