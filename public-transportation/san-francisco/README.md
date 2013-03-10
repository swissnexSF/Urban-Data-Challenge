Scheduled arrivals, actual arrivals, and passenger counts are provided as separate files. The common identifier that allows for joining the data sets is TRIP_ID.

The network's routes and stops are available as

* ESRI Shapefile
* GeoJSON
* [TopoJSON](https://github.com/mbostock/topojson/)


# scheduled-arrivals.csv

| Column  | Meaning |
| ------- | ----------- |
| PUBLIC_ROUTE_NAME | Name of route (i.e. 1 = 1 California) |
| TRIP_ID | ID number of trip |
| BLOCK_NAME | |
| LONGITUDE | Location of data point |
| LATITUDE | Location of data point |
| SCHEDULED_ARRIVAL_TIME | Scheduled arrival time at data point |
￼

# realtime-arrivals.csv

| Column  | Meaning |
| ------- | ----------- |
| PUBLIC_ROUTE_NAME | Name of route (i.e. 1 = 1 California) |
| NEXTBUS_VEHICLE_ASSIGNMENT | Vehicle ID |
| TRIP_ID | ID number of trip |
| BLOCK_NAME | |
| IS_TWO_CAR | One car ("N") or two car ("Y") train |
| CAR_NUMBER | 0 = 1 car train/bus, 1 = first train car, 2 = second train car |
| STOP_ID | ID number of transit stop |
| LONGITUDE | Location of data point |
| LATITUDE | Location of data point |
| NEXTBUS_ARRIVAL_TIME | Actual arrival time at data point |

# passenger-count.csv

| Column        | Meaning |
| -------       | ----------- |
| STOP_SEQ      | Sequential stop order for a given trip |
| STOP_ID       | ID number of transit stop |
| STOP_NAME     | Transit stop name |
| ON            | Boardings at transit stop |
| OFF           | Alightings at transit stop |
| LOAD          | Estimated load on vehicle |
| MO            | Month (October) |
| DAY           | Day |
| YR            | Year |
| ROUTE         | Route number (5xx = xx limited route, 6xx = owl routes, 7xx = xx express route, 8xx = xx BX express route, 9xx = xx AX express route) |
| LATITUDE      | Location of data point |
| LONGITUDE     | Location of data point |
| TRIP_ID       | ID number of trip |
| DIR           | Direction (1 = inbound, 0 = outbound) | 
| VEHNO         | Vehicle number |
| TIMESTOP      | Time vehicle stops and opens doors |
| TIMEDOORCLOSE | Time that the doors close |
| TIMEPULLOUT   | Time that the vehicle starts rolling after doors close (maybe the same time as DOORCLOSE) |
| TRIPCODE      | Unique identifier code for a specific vehicle on a specific date and time |
| TRIPSTOP      | STOP_SEQ plus 1000 concatenated with STOP_NAME |
| DOORDWELL     | Time the doors are open (TIMEDOORCLOSE - TIMESTOP) | 
| WAITDWELL     | Time between vehicle rolling and doors close (TIMEPULLOUT - TIMEDOORCLOSE) | 

# Correlating Schedule with Arrivals:

The three files starting with *rotation* contain information about the schedules including the trip IDs used in the passenger and arrival data. Below is an example provided by Chris Pangilinan (SFMTA).

## Example

If you look at Column “M” from the passenger data set, you’ll see a trip ID.  Let’s walk through an example:

Within *passenger-count.csv*, for the 1-California route, you’ll see Trip ID 758 for the inbound direction in Column “M”.  This means that for this specific trip on any weekday, it is scheduled to leave its outermost terminal (Geary/33rd) at 7:58 AM.  Now look at the Rotations Weekday file.  At Cell H-93, you’ll see the 7:58 departure for the inbound 1-California and its subsequent scheduled arrivals at various time points along the route. California/6th Ave at 8:09 AM, California/Presidio at 8:15 AM, etc.  To mine the data within the Rotation CSV’s, you’ll have to go through this exercise for all routes and (I apologize!) deal with the not so friendly formatted CSV file.  These Rotation CSV files were never meant for stuff like this but it is all we have unfortunately.