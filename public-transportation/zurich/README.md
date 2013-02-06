# Public Transportation (Zurich)

The scheduled data set and actual arrival data set are separated into two files. They can be merged by joining them at the following fields:

* serviceDate
* routeId
* runId
* tripStart
* direction
* stopSequenceNr


## passenger-count.csv

Column Name                 | Annotation                                                | Format
------                      | -------------                                             | ---
serviceDate                        | Service Date, can be different from actual date           | YYYYMMDD
routeId                     |                                                           | number
runId                       |                                                           | number
tripStart                   | scheduled trip start (seconds since midnight)             | number
direction                   |                                                           | number [1 or 2]
stopSequenceNr              | stop sequence number, starting with 1                     | number
stopId                      | stop identifier                                           | number 
stopNameShort               |                                                           | string, 4 characters
stopName                    |                                                           | string
vehicleTypeShort            |                                                           | string
vehicleType                 |                                                           | string
vehicleNumber               |                                                           | number
passengersBoardingTrip      | total boarding passenger for the trip                     | number
passengersAlightingTrip     | total alighting passengers for the trip                   | number
passengersDifferenceTrip    | total boarding passenger minus total alighting passengers | number
passengersBoardingStop      | boarding passenger at this stop                           | number
passengersAlightingStop     | alighting passenger at this stop                          | number
passengerLoadStop           | number of passenger at each stop                          | number



## schedule-vs-arrival.csv

Column Name                 | Annotation                                        | Format
------                      | -------------                                     | -----
serviceDate                 | Service Date, can be different from actual date   | YYYY-MM-DD HH24:MI:SS.MMM
date                        | actual date                                       | YYYY-MM-DD HH24:MI:SS.MMM
tripId                      |                                                   | number
tripStart                   | scheduled trip start (seconds since midnight)     | number [seconds]
routeId                     |                                                   | number
routeNumber                 |                                                   | numebr
routeNameShort              |                                                   | string
routeName                   |                                                   | string
runNumber                   |                                                   | number
direction                   |                                                   | number [1 or 2]
stopSequenceNr              |                                                   | number
stopId                      |                                                   | number
stopNumber                  |                                                   | number
stopNameShort               |                                                   | string
stopName                    |                                                   | string
arrivalScheduled            |                                                   | number [seconds]
departureScheduled          |                                                   | number [seconds]
arrivalActual               |                                                   | number [seconds]
departureActual             |                                                   | number [seconds]
mileage                     |                                                   | number
vehicleId                   |                                                   | number
vehicleTechnicalId          |                                                   | number
vehicleNumber               |                                                   | string
vehiclePlate                |                                                   | string
patternId                   |                                                   | number
patternNumber               |                                                   | number
patternName                 |                                                   | string
patternType                 |                                                   | string
blockId                     |                                                   | number
blockNumber                 |                                                   | number
branchId                    |                                                   | number
branchNumber                |                                                   | number
branchName                  |                                                   | string
longitudeScheduled          |                                                   | number [WGS84 in ms]
latitudeScheduled           |                                                   | number [WGS84 in ms]
longitudeActual             |                                                   | number [WGS84 in ms]
latitudeActual              |                                                   | number [WGS84 in ms]
compassDirectionScheduled   |                                                   | number [degree]
compassDirectionActual      |                                                   | number [degree]
