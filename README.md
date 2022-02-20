# Drafts for OCSS (Open Carpooling Service Specification)

This repository include drafts for building an open carpooling specification.

## 1 - Driver journeys

This repo provides 2 proposal of specifications for a standardized carpooling
API adressing driver journeys search.

### `carpool-api-en.yml`
A perfect copy of the (Vianavigo Carpool API specification)[https://doc.vianavigo.com/api-carpool/] translated in English.

### `carpool-api-refined-en.yml`

A new proposition compatible with (Vianavigo Carpool API specification)[https://doc.vianavigo.com/api-carpool/], but modified according to 5 years feedbacks in production, with up to 2M driver journeys search queries a day (for Klaxit alone).

With these changes that must be discussed :
- add a mandatory `passengerPickupDate` as it's the one date the requesting passenger cares about.
- make `passengerPickupLat`, `passengerPickupLng`, `passengerDropLat`, `passengerDropLat` mandatory as it's the coordinates the requesting passenger cares about.
- make `driverDepartureDate`, `driverDepartureLat`, `driverDepartureLng`, `driverArrivalLat`, `driverArrivalLng` optionals. They are not necessary to present a consistent journey to a passenger.
- add optional `passengerPickupAddress` and `passengerDropAddress`, as it's the ones passenger may care about.
- remove `pickupTime`, as it can be calculated far more reliably by the consuming platform (difference between current time dans `passengerPickupDate`).
- add an optional `currency` field to make the standard i18n-ready.

Additional change that should be discussed (may be less consensual / breaking change) :
- make `driver` mandatory and remove `nbJourneys`. Are response with multiple journeys and no specification of the driver really used ?

## 2 - Connect

Klaxit has been supporting a "Connect" feature, allowing its visitors to use
their MaaS account to connect to Klaxit, for 3+ years. To date, more than
100K users are using this technology to connect to Klaxit.

Klaxit has historically built a founding article about the [best pratices to implement an OIDC flow on mobile](https://medium.com/klaxit-techblog/openid-connect-for-mobile-apps-fcce3ec3472).

And presents here a [draft specification](connect-specification.md) to standardize
these best practises. It covers additionnal aspects as the GDPR compliance of the flows.

