# Logs Analysis Tool
Logs Analysis project for the database portion of the Udacity full-stack nanodegree

The purpose is to provide a simple script which allows consumers to learn about a couple key insights based on the analysis of the avaiable logs data. Those insights are: the top 3 most viewed articles, which authors have the most views, and which days had errors in excess of 1% of total requests.

Each insight can accessed by providing a second command line argument to the logs-analyzer.py script. The program was built in this way in order to very easily be able to add new insights at a later time. A simple `make_query` function is utilized so that the only concern of each insight block is to provide the SQL query block and the logic for formatting the output. The `make_query` function is to abstract the common functionality required each time the script is run, namely connecting to the database, making a cursor, executing the provided query then closing the cursor and connection.


## Examples inputs and output:

### Top 3 most viewed articles

input:
```
$ python logs-analyzer.py top-3-articles
```

output:
```
"Candidate is jerk, alleges rival" - 338647 views
"Bears love berries, alleges bear" - 253801 views
"Bad things gone, say good people" - 170098 views
```
### Top authors by views

input:
```
$ python logs-analyzer.py top-authors
```

output:
```
Ursula La Multa - 507594 views
Rudolf von Treppenwitz - 423457 views
Anonymous Contributor - 170098 views
Markoff Chaney - 84557 views
```

### Days with more than 1% of errors

input:
```
$ python logs-analyzer.py failure-days
```

output:
```
Jul 17, 2016 - 2.26% errors
```
