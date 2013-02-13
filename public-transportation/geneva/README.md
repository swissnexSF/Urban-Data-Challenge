Transports publics genevois (tpg, or Geneva Public Transport) is public transport authority for the larger Geneva region. It helps manage mobility throughout the France-Vaud-Geneva metropolitan area, offering a range of top-quality services with due regard for sustainable development principles. All tpg activities aim at excellence in the service of the community, on the basis of a contract for the supply of services renegotiated every four years with the State of Geneva.

The network's routes and stops are available as

* KML (best viewed in Google Maps)
* ESRI Shapefile
* GeoJSON
* [TopoJSON](https://github.com/mbostock/topojson/)

The daily schedule, real time arrival, and passenger counts for Oct 1 to 7 are provided in one big comma separated file.

# Data description

## Routes.kml
This file describes every routes of the TPG network in a kml file.

| Field            | Description                    |
| ---------------- | ------------------------------ |
| networkCode      | Identifies the Network         |
| routeCode        | Code of the route              |
| routeDirection   | Direction of the route         |
| routeDestination | Final Destination of the route |

## Stops.kml
This file describes every stops of the TPG in a kml file.

| Field            | Description                              |
| ---------------- | ---------------------------------------- |
| networkCode      | Identifies the Network                   |
| stopCode         | Code of the stop                         |
| stopName         | Name of the stop (as seen by the client) |
| routeCode        | Code of the route                        |
| routeDirection   | Direction of the route                   |
| routeDestination | Final Destination of the route           |

## schedule-real-time.csv

This data set contains specific data about vehicles (tram/bus/trolley bus) and juxtaposes the scheduled time with the real arrival time. In addition, it contains data about passengers boarding and leaving the vehicle at each stop.
Each line in the file relates to a *stop*, a particular vehicle stopping at a particular stop at a particular time.

| Field                     | Description                              |
| ----------------          | ---------------------------------------- |
| date                      | Day of the trip |
| routeCode                 | Code of the route of the trip |
| serviceVehicle            | Service of the trip. All the trips of a service are assigned to a same vehicle. |
| tripId                    | Id of the trip. A trip is a set of stops along a route and a pattern ordered by departure time (from a departure terminal to an arrival terminal) |
| vehicleId                 | Id of the vehicle |
| patternId                 | Id of the pattern. A pattern is a subset of a route |
| tripDirection             | Direction (A=inbound or S=outbound) of a trip |
| tripLength                | Length of the whole trip (in meter). |
| stopSequenceNr            | Sequence number of each stop, starting with 1 at the departure terminal |
| stopCode                  | Short stop identifier code |
| stopLength                | Distance from the departure terminal to the stop (in meter) |
| stopTimeSchedule          | Schedule time for the time stop |
| stopTimeReal              | Real time for the time stop |
| passengerCountTripUp      | Total number of passengers entering the vehicle for the trip (at all stops and all doors) |
| passengerCountTripDown    | Total number of passengers exiting the vehicle for the trip (at all stops and all doors) |
| passengerCountStopUp      | Total of the number of passengers entering the vehicle for the timestop (at all stops and all doors) |
| passengerCountStopDown    | Total of the number of passengers leaving the vehicle for the timestop (at all stops and all doors) |
| passengerLoadStop         | Number of passengers on board (when the vehicle is leaving the stop) |
| passengerCountDoor1Up     | Number of passengers entering the vehicle by door 1 |
| passengerCountDoor1Down   | Number of passengers leaving the vehicle by door 1 |
| passengerCountDoor2Up     | Number of passengers entering the vehicle by door 2 |
| passengerCountDoor2Down   | Number of passengers leaving the vehicle by door 2 |
| passengerCountDoor3Up     | Number of passengers entering the vehicle by door 3 |
| passengerCountDoor3Down   | Number of passengers leaving the vehicle by door 3 |
| passengerCountDoor4Up     | Number of passengers entering the vehicle by door 4 |
| passengerCountDoor4Down   | Number of passengers leaving the vehicle by door 4 |
| passengerCountDoor5Up     | Number of passengers entering the vehicle by door 5 |
| passengerCountDoor5Down   | Number of passengers leaving the vehicle by door 5 |
| passengerCountDoor6Up     | Number of passengers entering the vehicle by door 6 |
| passengerCountDoor6Down   | Number of passengers leaving the vehicle by door 6 |
| isRedirection             | The vehicle is redirected at this stop |
| isDelocalisation          | If *isRelocalisation* is false, the vehicle can't be reliably located at this stop. This is a technical problem on the AVLS (Automatic vehicle Localization System) or the vehicle did not respect the scheduled stops. The data may not be very accurate for this stop. |
| isRelocalisation          | The vehicle is re-located after it couldn't have been located previously.
￼
