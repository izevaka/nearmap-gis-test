# nearmap.com GIS Data Manipulation Test
Welcome to nearmap.com technical test. The purpose of this assignment is to test
your ability to source freely avaialble data from the Internet, process it in
a geospatial database, obtain and install the right tools, and deliver processed
results.
## Task

Build a system that can generate geometry for ABS Mesh Block structures from a
geospatial database.

1. Obtain the publicly available ABS Mesh Blocks for NSW for the year 2011.
Hint: it's easier to use shapefile format.

2. Import the Mesh Block definitions into a PostGIS database (that is PostgreSQL
  with PostGIS extensions). Meshblocks must stored in Lat/Lng in EPSG:4326.

3. Write a database query that provides GeoJSON responses to clients. The
requested geometry will be defined by a bounding box, representing the viewport
of the client. The bounding box is as below and is specified using Lat/Lng
co-ordinates in EPSG:4326.

```
151.15340611511192,-33.92660082361348,151.04568860107383,-33.967577088467
```

## Submission Instructions

* A dump of the database table(s) containing the Mesh Blocks. As this is a
large amount of data, limit the number of rows to 100. You may need to copy the
table into another table and limit number of rows to 100 in that new table to
achieve this.
* Database query used to obtain the GeoJSON. If you needed to use
any parameters to psql to run the query, include the command as well.
* Output file that contains the GeoJSON response. It must contain valid
GeoJSON. You can validate it at http://geojson.io
* DO NOT send pull requests against this repository because we don't want other
candidates to see your solution.

## For bonus points:

* Provide steps and commands that you followed to get your environment set
up, import the data and produce results.
* Build in a fail safe that prevents the query from creating a heavy load on
the database given a bounding box that covers the state. (This could prevent
the query from running or minimize the resources used). To put this into
context, imagine this query is generated using parameters from a URL for a
variety of data types. Since the user is at will to contsruct a URL as they
please, the server should be defensive about how to handle those.
* Provide ideas on how queries could still be performed on this data at the
state level. Hint: hanve a look on ABS website for other geographical data sets.
