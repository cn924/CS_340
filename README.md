# Data Aggregation Pipeline

We imported the database with:

```mongoimport --port <number> --db=<db name> --collection=<col name> --file=<location and name.json>```  

From the shell, we can see that the database appears.  

![](show_dbs.PNG)>  

# Verify Load  

Next we can run a couple of tests to verify the load.      

```db.research.find({"name" : "AdventNet"})``` 
&nbsp;
-
![](advent.PNG)>

AND.  

```db.research.find({"founded_year" : 1996},{"name" : 1}).limit(10)``` 
&nbsp;
-
![](founded.PNG)>



# Running Queries 

List only the first 20 names of companies founded after the year 2010, ordered alphabetically.  

```db.research.find({"founded_year": {"$gt": 2010}}, {"name": 1}).sort({"name": 1}).limit(20)```

![](founded_year.PNG)>


List only the first 20 names of companies with offices in either California or Texas, ordered by the number of employees and sorted largest to smallest.

```db.research.find({"offices.state_code": {"$in": ["CA", "TX"]}}, {"name": 1, "number_of_employees": 1}).sort({"number_of_employees": -1}).limit(20).pretty()```

![](noOfemp.gif)>




# MongoDB Aggregation Pipeline  

Design and implement a MongoDB aggregation pipeline to show the total number of employees by state for all companies that have offices in the United States. Be sure that you account for the fact that some companies have offices in several states.

![](Animation.gif)>





