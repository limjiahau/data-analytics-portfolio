Description of all the variables / features: 
id — a unique identifier for each trip

vendor_id — a code indicating the provider associated with the trip record

pickup_datetime — date and time when the meter was engaged

dropoff_datetime — date and time when the meter was disengaged

passenger_count — the number of passengers in the vehicle (driver entered value)

pickup_longitude — the longitude where the meter was engaged

pickup_latitude — the latitude where the meter was engaged

dropoff_longitude — the longitude where the meter was disengaged

dropoff_latitude — the latitude where the meter was disengaged

store_and_fwd_flag — This flag indicates whether the trip record was held in vehicle memory before sending to the vendor because the vehicle did not have a connection to the server (Y=store and forward; N=not a store and forward trip)

trip_duration — (target) duration of the trip in seconds

-------------------------------------------------------

- Plot a map of NYC and overlay a number of pickup coordinates to get a general overview of the locations and distances in questions. 
- For the interactive map, I am using the leaflet package. We can zoom and pan through the pickup locations
- Investigate the variations together with the distributions of "passenger_count" and "vendor_id" by creating a multi-plot panel with different components

Check:
- Number of passengers usually in a taxi
- Vendor wise trips and patterns for different weekdays, hours of the day, months, locations, trip durations
- Relationship between Store and Forward vs "trip_duration

Build new features:
- date, month, wday, and hour from "pickup_datetime"
- calculate direct distance between two pickup points and compare to "trip_durations" from their coordinates (using distCosine function of the geosphere)
- compute average apparently velocity of taxis, average duration per day and hour, and average speed for these time bins

- Create heatmap of speed over the week for hours
- Create a new feature "work", based on busy hours
- Explore trips to airport, long day trips, zero distance trips