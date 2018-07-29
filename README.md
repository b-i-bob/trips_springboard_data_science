# trips_springboard_data_science
Repo for building predictive models about trips. For Springboard Data Science course.

## About this data set

The dataset is from a transportation service provider who wishes to remain anonymous.

The data has about 200K rows and 74 columns/attributes/features. Each row is a trip booked with this service during 2017.

## Notes on Data Semantics

- Trips are one way. A trip is one vehicle. A round trip is scheduled as 2 separate trips.
- Trips are scheduled from one or more origin locations to one or more destinations.
- Trips have a finished state of either `complete` or `canceled`. `Complete` trips delivered 1 or more passengers from one or more origin locations to one or more destinations. `Canceled` trips are where no pickups happened. Trips can be canceled by the trip organizer or by the system if needed. There may be a fee for trips cancelled too close to the scheduled start.
- The data set contains test trips which appear mostly normal but did not actually happen and are not explicitly marked. Best to filter those out.
- The trip lifecycle has booking, claiming, driving phases.
  - Trips are booked by an organizer for 1 or more passengers at least 8 hours before the scheduled start. Regularly recurring trips can be booked all at once. These are called repeating. A shuddle trip is a kind of repeating trip.
  - Trips in the marketplace can be claimed by a driver. Trips enter the marketplace at noon 7 days prior to the scheduled start date, or immediately upon booking if the scheduled start is within the next 7 days. Drivers only have visibility to some trips in the marketplace (within their communting limit, not conflicting with prior claimed trips, etc.). Several mechanisms match trips to drivers. Trips remain in the marketplace until claimed by a driver or cancelled. 
  - Some trips are unclaimed and possibly reclaimed by another driver if the original driver is unavailable or late. Unclaimed trips are canceled by the system 30 minutes before scheduled start for lack of a driver. Organizers can cancel a trip at anytime.
  - On the day of the trip... A driver checks in before the trip to confirm their availability to drive. The driver drives to the first pickup, arrives, and may wait. Passengers are picked-up. The vehicle departs the pickup location. This is repeated at each origin. At each destination passengers disembark. The trip is complete after the last passenger is delivered.

## Possible Predictions

1. Will the trip be claimed by a driver? 
2. How long will it take to claim the trip? 
3. Will the trip be unclaimed after it is claimed? 
4. What will driver’s commute distance be? 
5. Will the trip be canceled by the organizer? 
6. Will the trip be bonused (driver incentive in order to get the trip claimed)? 
7. Will be driver be late to the first pick-up? 
8. How will the organizer rate the trip (unhappy, happy, super-happy)? 
9. Will the organizer book another trip after this one?
10. Will the driver claim another trip after this one?


