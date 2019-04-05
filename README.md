# Udacity_project_1: Log Analysis
The project let the user find on a newspaper database which are the top 3 articles, the top 3 authors and the days in which the percentage of requests that lead to errors is grater than 1%.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

First, install vagrant VM on your local machine. This will give you the environment need to run the project. Then bring *VAGRANT UP* and log into your VM with *VAGRANT SSH*. 

### Installing

Download the zip file containing the newsdata.sql database and unzip it. Move this file into your vagrant directory, in order to share it with your VM. 
To check if you did everything correctly, try connecting to the database with *psql news* and run the following queries:

```
\dt
\d articles
select * from articles
```

To run correctly the project requires some predefined views. You need to run the following code to create them:

1) This view query the DB to get the number of 404 NOT FOUND requests on each day of the month
```
create view wrong_per_day as select count(status) as num_wrong, (time::date) from log where status = '404 NOT FOUND' group by (time::date);
```

2) This view query the DB to get the total number of requests on each day of the month
```
create view total_per_day as select count(*) as num_total, (time::date) from log group by (time::date);
```
3) This view query the DB to get the percentage of 4040 NOT FOUND requests on each day of the month
```
create view calculate_percentage as select CAST(num_wrong as float)/CAST(num_total as float)*100.0 as percent, to_char(total.time, 'FMMonth FMDD, yyyy') from (select * from wrong_per_day) as wrong JOIN 
(select * from total_per_day) as total on wrong.time=total.time;
```

## Running the tests

Try running the following queries to test if the views are created correctly:
```
select * from wrong_per_day

select * from total_per_day

select * from calculate_percentage
```

## Running the program

FInally, from your VM directory, run **python project_1_db.py** to run the program. It will create a text file called results.txt in the same directory. Open this file in order to see the results of the queries.
