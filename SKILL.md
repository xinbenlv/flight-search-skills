---
name: "flight-search-skills"
description: "Research, compare, and verify cash or award flights across multiple flight search engines and booking sites, including complex, multi-city, long-layover, self-transfer, points, and conflict-airspace-sensitive itineraries."
---

# Flight Search Workflow

## 1. Establish the request

Before searching, identify:

- Origin and destination airports or cities
- Departure and arrival date constraints in local time
- One-way, round-trip, open-jaw, or multi-city
- Passenger count, cabin, baggage, and accessibility needs
- Cash, points, or both
- Date and airport flexibility
- Maximum stops, acceptable self-transfers, and desired stopovers
- Passport, transit, visa, and airspace-safety constraints when relevant
- Whether the user prefers the lowest price, shortest trip, protected ticket, direct-airline booking, or a long daytime layover

Ask only for information that cannot be obtained from existing context or a reasonable flexible search.

## 2. Search in layers

Use the engines below according to their strengths. For a normal cash search, check Google Flights plus at least two independent metasearch or OTA sources. Use more sources when the itinerary is expensive, complex, unusually constrained, or incomplete.

### Discover hub, local-market, and non-aggregated inventory

Do not assume a global aggregator has complete airline coverage. Build a route-market coverage map before concluding that no good itinerary exists. Include four layers:

- Origin: the airport's dominant or hub airlines and the origin country's major independent carriers.
- Destination: the destination airport's home carriers, the destination country's flag or network airlines, and leading local flight-search platforms.
- Route-adjacent markets: airlines and local search platforms in plausible gateway economies near the route, especially large aviation markets such as Japan, South Korea, China, Taiwan, or comparable regional hubs.
- Distribution gaps: airlines whose schedules or fares may be absent, delayed, or incomplete on aggregators, such as Southwest for relevant US segments.

For each layer:

1. Use official airport airline or route directories to identify carriers rather than relying only on memory or an aggregator.
2. Search relevant airlines directly, including low-cost subsidiaries, and manually construct separate-segment or multi-city searches when the through-search omits a connection.
3. Search the destination market's leading local engines and the leading engines of plausible gateway markets, using airport codes and local-language names when helpful.
4. Compare aggregator, local-platform, and direct-airline inventory. Record flights, fare families, baggage options, or schedules that appear in only one channel.
5. Mark every coverage-map entry as searched, unavailable for the dates, or ruled out with a reason. Do not describe coverage as exhaustive while material entries remain unchecked.

Examples of regional coverage to consider when geographically relevant:

- United States: the origin airport's hub carrier, Alaska, Southwest, JetBlue, and other large or locally strong carriers.
- Kazakhstan and Central Asia: Air Astana, FlyArystan, destination-airport carriers, and reputable local platforms such as Aviata or Chocotravel.
- Japan: JAL, ANA, ZIPAIR, other relevant Japanese carriers, and Japanese-market search or booking platforms such as Travelko or Skyticket.
- China: Air China, China Eastern, China Southern, Hainan, XiamenAir, and local platforms including Qunar, Fliggy, and Ctrip/Trip.com.
- South Korea: Korean Air, Asiana, Air Premia, Jeju Air, T'way, Jin Air, Eastar Jet, and Korean-market search platforms such as Naver Flights or Interpark Tour.

Use this as a discovery checklist, not a fixed airline list. Adapt it to the actual airports, route geography, and date. Verify every local-platform fare on the operating airline's own schedule when possible, and note language, residency, identity, payment-card, phone-number, or currency restrictions.

### Schedule, routing, and fare baselines

- [Google Flights](https://flights.google.com): Start here for dates, schedules, filters, price trends, flight numbers, duration, and booking options.
- [ITA Matrix](https://itasoftware.com): Use for advanced fare construction, routing codes, fare classes, and validating complex itineraries. It does not normally sell tickets.
- [BookWithMatrix](https://bookwithmatrix.com): Use to reproduce or find a booking path for an ITA Matrix itinerary. Recheck live availability before relying on it.

### Metasearch, deal discovery, and alternate combinations

- [Skiplagged](https://skiplagged.com): Use for alternate combinations. Treat hidden-city itineraries as high-risk and never recommend or book one without explicit user acceptance of the baggage, cancellation, loyalty-account, and contract-of-carriage risks.
- [Kiwi](https://kiwi.com): Useful for virtual interlining and unusual combinations. Clearly label self-transfers and identify which connections are not protected by the airlines.
- [Hopper](https://hopper.com): Use for price forecasts and mobile-oriented deal discovery; verify the final itinerary elsewhere.
- [Going](https://going.com): Use for deal alerts and destination/date inspiration, not as the sole source for a specific live fare.
- [Skyscanner](https://skyscanner.com): Compare airlines and regional OTAs; verify seller reputation and final all-in price.
- [Kayak](https://kayak.com): Compare schedules, flexible dates, and booking sources.
- [Momondo](https://momondo.com): Check alternate OTAs and fare combinations, especially when mainstream results are narrow.

### Online travel agencies

- [Priceline](https://priceline.com)
- [Booking.com](https://booking.com)
- [Agoda](https://agoda.com)
- [Orbitz](https://orbitz.com)
- [Travelocity](https://travelocity.com)
- [Trip.com](https://trip.com)
- [Qunar](https://qunar.com)
- [Fliggy](https://fliggy.com)

Use OTAs to compare live prices and availability. Record the exact seller, currency, refund/change rules, baggage display, and whether the itinerary is issued as one ticket or separate tickets. Qunar and Fliggy may have language, payment, identity, phone-number, or regional-account requirements; verify that the user can actually book the displayed fare.

### Award-flight search

- [Point.me](https://point.me)
- [PointsYeah](https://pointsyeah.com)
- [Roame](https://roame.travel)

For award results, record:

- Loyalty program and operating airline
- Miles or points required per passenger
- Taxes, fees, and surcharges
- Transfer partners and expected transfer time
- Cabin and segment-by-segment availability
- Whether the award is bookable now on the loyalty program's own site

Never treat an aggregator's award result as confirmed until the operating or ticketing program shows matching availability.

## 3. Normalize every candidate

For each viable itinerary, capture:

- Local departure and arrival dates and times
- Airports, terminals when shown, airlines, and flight numbers
- Aircraft when useful
- Stops, layover airports, and layover durations
- Total elapsed time
- One protected ticket, separate tickets, or self-transfer
- Cash price or award cost for the full party
- Booking source and direct-airline price when available
- Carry-on and checked-bag allowances or fees
- Fare family, change/refund restrictions, and seat-selection limits

Compare all-in prices, not headline fares. Include required bags, seat fees when relevant, airport changes, ground transfers, hotel nights, and separately ticketed positioning flights.

## 4. Evaluate long layovers and stopovers

When the user wants time in a connecting city:

1. Compute the layover from local arrival to local departure.
2. State how many usable daytime hours and hotel nights it provides.
3. Allow realistic time for immigration, baggage collection, airport-to-city transport, return travel, security, and check-in.
4. Confirm whether the traveler must enter the country and whether passport, visa, or transit rules apply.
5. Prefer a full calendar daytime over a nominally long layover that occurs mostly overnight.

## 5. Evaluate operational and safety risk

When airspace or geopolitical avoidance matters:

- Exclude prohibited layover airports and countries first.
- Check current official aviation advisories and recent route-track evidence when available.
- Distinguish verified historical tracks from geographic inference.
- Do not claim that a future route is guaranteed; dispatch routes can change because of weather, politics, or airspace restrictions.
- Recheck operational routing close to departure.

For separate tickets and virtual interlining, explain:

- Whether bags must be collected and rechecked
- Whether immigration is required
- Minimum practical buffer, including terminal or airport changes
- That the onward airline may not protect the traveler after a delay
- Whether an overnight buffer materially reduces the risk

## 6. Rank and present

De-duplicate identical flights sold by different sites. Present a short ranked list, normally:

1. Best overall
2. Lowest practical price
3. Best protected or direct-airline option
4. Best schedule, stopover, or award option when relevant

For each recommendation, show the decisive trade-off. Explicitly mark unattractive or excluded options and why they were rejected.

Before finalizing, perform a coverage audit: confirm that the origin's main hub airline, the destination country's principal airlines, relevant route-adjacent regional carriers, and plausible non-aggregated airlines were either searched or explicitly ruled out.

Prefer booking directly with the airline when the price difference is modest, especially for international, separate-ticket, or disruption-sensitive travel. Do not purchase until the user confirms the exact itinerary and current fare.