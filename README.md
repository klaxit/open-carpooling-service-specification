# Drafts for the carpool API spec

This repository include drafts for building an open carpool specification.

## 1 - Information

This repo provides specifications draft for a new carpooling API standard.

### `carpool-api-en.yml`
A perfect copy of the (Vianavigo Carpool API specification)[https://doc.vianavigo.com/api-carpool/] translated in English.

Except some minor modifications on HTTP statuses.
### `carpool-api-refined-en.yml`

A perfect copy of the (Vianavigo Carpool API specification)[https://doc.vianavigo.com/api-carpool/] translated in English.

With these changes that must be discussed :
- add a mandatory `passengerPickupDate` as it's the one date the requesting passenger cares about.
- make `passengerPickupLat`, `passengerPickupLng`, `passengerDropLat`, `passengerDropLat` mandatory as it's the coordinates the requesting passenger cares about.
- make `driverDepartureDate`, `driverDepartureLat`, `driverDepartureLng`, `driverArrivalLat`, `driverArrivalLng` optionals. They are not necessary to present a consistent journey to a passenger.
- add optional `passengerPickupAddress` and `passengerDropAddress`, as it's the ones passenger may care about.
- remove `pickupTime`, as it can be calculated far more reliably by the consuming platform (difference between current time dans `passengerPickupDate`).

Additional change that should be discussed (may be less consensual / breaking change) :
- make `driver` mandatory and remove `nbJourneys`. Are response with multiple journeys and no specification of the driver really used ?


### `carpool-api-both-drivers-passengers.yml`
Starting from (Vianavigo Carpool API specification)[https://doc.vianavigo.com/api-carpool/], it tries to support passengers' journeys.

**It includes too many breaking changes**.

## 2 - Connect

TODO
