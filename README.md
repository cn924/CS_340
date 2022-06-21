# Data Aggregation Pipeline

We imported the database with:

```mongoimport --port <number> --db=<db name> --collection=<col name> --file=<location and name.json>```  

From the shell, we can see that the database appears.  

![](show_dbs.PNG)>

Next we can run a couple of tests to verify the load.  

```db.research.find({"name" : "AdventNet"})```
![](advent.gif)>



```db.research.find({"founded_year" : 1996},{"name" : 1}).limit(10)```
![](founded.gif)>



