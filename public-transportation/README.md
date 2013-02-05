Public transportation data for the three cities contain information about
* scheduled arrivals of vehicles
* real time arrivals of vehicles
* passenger counts at each stop

Each city has a folder containing the data that was provided by its transit authority. The data structure and the extent of the data collected is different for 
each of the three cities, but you'll be able to find common data field in each city's collection:

## Common Data Fields

### Schedule
| field                 | San Francisco                                             | Zurich                                        | Geneva                                           |
| -------------         | -------------                                             | ------                                        | ------                                           |
| Date                  | derived from realtime-arrivals.csv/NEXTBUS_ARRIVAL_TIME   | schedule-vs-arrival.csv/serviceDate           | schedule-real-time.csv/date |
| Route Identifier      | scheduled-arrivals.csv/PUBLIC_ROUTE_NAME                  | schedule-vs-arrival.csv/routeId               | schedule-real-time.csv/routeCode |
| Trip Identifier       | scheduled-arrivals.csv/TRIP_ID                            | schedule-vs-arrival.csv/tripId                | schedule-real-time.csv/tripId |
| Vehicle Identifier    | realtime-arrivals.csv/NEXTBUS_VEHICLE_ASSIGNMENT          | schedule-vs-arrival.csv/vehicleId             | schedule-real-time.csv/vehicleId |
| Stop Identifier       | realtime-arrivals.csv/STOP_ID                             | schedule-vs-arrival.csv/stopId                | schedule-real-time.csv/stopCode |
| Scheduled Arrival     | scheduled-arrivals.csv/SCHEDULED_ARRIVAL_TIME             | schedule-vs-arrival.csv/departureScheduled    | schedule-real-time.csv/stopTimeSchedule |
| Actual Arrival        | realtime-arrivals.csv/NEXTBUS_ARRIVAL_TIME                | schedule-vs-arrival.csv/departureActual       | schedule-real-time.csv/stopTimeReal |
| Latitude              | realtime-arrivals.csv/LONGITUDE                           | schedule-vs-arrival.csv/longitudeActual       | derived from entry in tpg_Map/Stops.kml          |
| Longitude             | realtime-arrivals.csv/LATITUDE                            | schedule-vs-arrival.csv/latitudeActual        | derived from entry in tpg_Map/Stops.kml          |
                                                                                    
### Passenger numbers
| field                           | San Francisco            | Zurich                                        | Geneva                  |
| ----------------------          | ------                   | ------                                        | ------                  |
| Nr Passengers boarding per trip | N/A                      | passenger-counts.csv/passengersBoardingTrip   | passengerCountTripUp    |
| Nr Passengers exiting per trip  | N/A                      | passenger-counts.csv/passengersAlightingTrip  | passengerCountTripDown  |
| Nr Passengers boarding per stop | passenger-count.csv/ON   | passenger-counts.csv/passengersBoardingStop   | passengerCountStopUp    |
| Nr Passengers exiting per stop  | passenger-count.csv/OFF  | passenger-counts.csv/passengersAlightingStop  | passengerCountStopDown  |
