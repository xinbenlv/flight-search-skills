# flight-search-skills

An agent skill for finding flights that a single search engine won't show you.

Point an AI agent at Google Flights and it will confidently tell you the cheapest way
from A to B. Often it's right. But global aggregators have real coverage holes — a
destination's home carrier that never made it into the feed, a local booking platform
that's the only place a fare shows up, an airline like Southwest that sits outside most
aggregators entirely, or a connection that only appears if you build it as two separate
searches by hand. An agent that checks one source and stops will miss all of it, and will
sound just as sure either way.

This skill makes the agent search in layers and then prove its coverage.

## What it does

1. **Pins the request down** — dates in local time, cabin, bags, passport and transit
   constraints, and what you're actually optimizing for. Lowest price and shortest trip
   are different requests.
2. **Searches in layers** — schedule and fare baselines (Google Flights, ITA Matrix),
   metasearch and odd combinations (Kiwi, Skiplagged, Kayak, Momondo, Skyscanner), OTAs,
   and award engines (Point.me, PointsYeah, Roame). Then the part most agents skip: the
   origin's hub carriers, the destination country's own airlines and local search
   platforms, plausible gateway markets nearby, and airlines with known distribution gaps.
3. **Normalizes every candidate** — all-in price, not headline fare. Bags, seat fees,
   airport changes, hotel nights, and positioning flights included.
4. **Does the layover math** — how many usable daytime hours a stopover really gives you
   after immigration, transit, and check-in eat into it. A twelve-hour layover that lands
   at 1am isn't a day in the city.
5. **Flags operational risk** — separate tickets versus one protected ticket, whether bags
   must be recollected, whether the onward airline owes you anything after a delay, and
   airspace or routing exposure when that matters to you.
6. **Ends with a coverage audit** — every carrier and platform on the map is marked
   searched, unavailable, or ruled out with a reason. The agent isn't allowed to call a
   search exhaustive while entries sit unchecked.

## Install

Clone into wherever your agent reads skills from. For Claude Code:

```bash
git clone https://github.com/xinbenlv/flight-search-skills.git ~/.claude/skills/flight-search-skills
```

Any agent that loads a `SKILL.md` from a directory works the same way — the whole skill is
one file with no dependencies, so you can also just paste it in.

## Use

Ask for a flight and mention what you care about:

> Find me SFO to Astana in mid-September. Avoid conflict airspace, and I'd like a real
> daytime stop in Seoul rather than an overnight connection.

The skill was written during exactly that search. The itinerary it surfaced routed through
Seoul with a full day on the ground, and the useful legs only turned up after checking
carriers and platforms that the first-page aggregator results never mentioned.

## Contributing

The coverage checklist is the part of this skill that gets better with other people in it.
It currently names carriers and local platforms for the US, Central Asia, Japan, China,
and South Korea — which reflects where I've been searching, not where the gaps are.

If you know your market, a PR adding its principal airlines and the search platform people
there actually use is worth more than any amount of editing to the prose. Same for
distribution gaps: airlines whose fares or schedules show up late, partially, or not at all
on the big aggregators.

Two things to keep in mind when adding a platform: note any residency, payment-card, phone
number, or language requirement that would stop a traveler from actually booking, and keep
the list a discovery checklist rather than a fixed roster. The skill tells the agent to
adapt it to the real route, not to read it as gospel.

## A note on hidden-city itineraries

The skill includes Skiplagged, and it is explicit that hidden-city ticketing carries
baggage, cancellation, loyalty-account, and contract-of-carriage risk. The agent is
instructed never to recommend or book one unless you've said you accept that. If you'd
rather it not surface them at all, say so in your request.

## License

MIT. See [LICENSE](LICENSE).
