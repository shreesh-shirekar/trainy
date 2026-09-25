# Terminology

Glossary of Indian Railways terms, from loco classes to waitlist codes, written so they're actually understandable.

## Booking status codes

*Checked 2026-09-25. Several of these rules changed in 2025, so re-check before anything ships.*

### How to read a status

An IRCTC booking shows two statuses for each passenger:

- **Booking status:** what you got at the moment you booked. It never changes.
- **Current status:** where you are now. It moves as other people cancel.

So `GNWL 45 / WL 12` means you booked at position 45 on the general waitlist and have since moved up to 12.

### Confirmed and RAC

| Code | Stands for | What it means |
| --- | --- | --- |
| CNF | Confirmed | You have a berth or seat. The coach and berth number may only appear once the chart is prepared. |
| RAC | Reservation Against Cancellation | You can board and travel, but you may have to share a berth (usually the side lower). If confirmed passengers cancel, RAC gets upgraded before anyone on the waitlist does. |

### Waitlist types

Each quota keeps its own waitlist, and a waitlist only moves when a berth in *its* quota frees up. That's why two tickets at "WL 10" on the same train can have very different chances.

| Code | Stands for | Who gets it | Outlook |
| --- | --- | --- | --- |
| GNWL | General Waiting List | Journeys starting at or near the train's origin | Usually the best odds. It draws from the biggest pool of cancellations. |
| RLWL | Remote Location Waiting List | Journeys starting at important intermediate stations that have their own quota | Usually the next best after GNWL, but worse because the quota is smaller. |
| PQWL | Pooled Quota Waiting List | Shorter journeys between intermediate stations, sharing one pooled quota | Slow to move. |
| RSWL | Roadside Station Waiting List | Journeys from the origin to nearby roadside stations | Very low odds. |
| RQWL | Request Waiting List | Journeys between intermediate stations not covered by any of the quotas above | Low odds. Sources are thin on this one, so it needs more digging. |
| TQWL | Tatkal Quota Waiting List | Waitlisted Tatkal bookings | Usually the worst odds. |

These outlooks are what the common guides agree on. Nobody publishes official odds. Real numbers would need historical data on how each train's waitlist actually cleared, which we don't have yet.

### Rules that affect waitlisted tickets

- **Waitlisted e-tickets get cancelled automatically.** If an online ticket is still fully waitlisted when the final chart is prepared, it's cancelled and refunded. You can't board with it.
- **Waitlist cap.** Since 2025, the waitlist is capped at about 25% of the berths available in each class, after reserved quotas are set aside. Fewer waitlist tickets get issued, so a ticket that does get issued has a better chance than it used to.
- **Chart timing is in flux.** In 2025 the first chart moved to about 8 hours before departure. For trains leaving before 2 PM, it's prepared at 9 PM the night before. Some 2026 guides say 10 hours instead, and a 24-hour chart has been piloted in the Bikaner division. The final chart comes shortly before departure. We need a reliable way to know which rule applies to a given train, not a hardcoded number.

### Sources

- [GNWL, RLWL, PQWL, TQWL explained (trainhelp.in)](https://www.trainhelp.in/gnwl-rlwl-pqwl-tqwl-meaning/)
- [What do WL, RSWL, PQWL, GNWL mean (DNA India)](https://www.dnaindia.com/india/report-what-do-wl-rswl-pqwl-gnwl-on-train-tickets-mean-know-all-about-railway-codes-2898270)
- [Reservation against Cancellation (Wikipedia)](https://en.wikipedia.org/wiki/Reservation_against_Cancellation)
- [Railway Board to prepare charts 8 hours prior to departure (News On AIR)](https://www.newsonair.gov.in/railway-board-to-prepare-reservation-charts-8-hours-prior-to-train-departure)
- [Waiting list capped at 25% (Times Bull)](https://www.timesbull.com/business/indian-railways-new-rule-waiting-list-capped-at-25-check-your-real-ticket-confirmation-chance-668664.html)
- [24-hour chart pilot (Tripzilla)](https://www.tripzilla.in/travel/india/indian-railways-to-finalize-reservation-charts-24-hours-before-departure/23480)
- [Chart preparation 10 hours before departure (RailMitra)](https://www.railmitra.com/blog/train-chart-preparation-time-is-now-10-hours-before-departure)
