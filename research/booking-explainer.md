# Booking Explainer (draft spec)

The first thing to build: you tell Trainy about your booking, and it tells you plainly what your status means and what happens next. No scraping, no live data.

## Why this first

- It's the "make waitlists understandable" idea from the README, and it doesn't need any data source we don't have yet.
- It sidesteps the PNR problem (see [`resource-audit.md`](resource-audit.md)). The user already has their booking details, so we don't need to fetch them.
- It gets something in front of railfans quickly so we can get feedback.

## What the user gives us

The minimum needed to explain a status:

| Field | Example | Needed for |
| --- | --- | --- |
| Booking status | `GNWL 45` | Which waitlist, and where they started |
| Current status | `WL 12` | Where they are now |
| Train number | `12951` | Showing the train, and later history and odds |
| Journey date | `2026-10-04` | Chart timing |
| Class | `3A` | Context. Waitlist caps are per class. |
| Quota | `GN`, `TQ` | Checks the waitlist code. Tatkal matters most here. |
| Boarding and destination stations | `NDLS`, `MMCT` | Context. Explains *why* they got RLWL or PQWL. |

For a first version, only the two statuses really matter. Everything else adds context.

## What Trainy shows back

1. **What the code means,** in one or two plain sentences, using the table in [`terminology.md`](terminology.md).
2. **How far they've moved.** For example, "You started at 45 and you're at 12 now, so 33 places cleared."
3. **A qualitative outlook** for that waitlist type (good / middling / poor), clearly labelled as general guidance. No percentages until we have real historical data to back them up.
4. **What happens at charting.** If it's still waitlisted when the final chart is made, an e-ticket is cancelled and refunded, and they can't board with it.
5. **Roughly when charting happens,** with the caveat that the rules are in flux (see terminology).

## Input methods, simplest first

1. **Manual entry.** Pick a waitlist type from a list and type in the numbers. This is the easiest to build and it never breaks.
2. **Paste the text.** The user pastes their IRCTC confirmation SMS or email and we parse out the statuses. We need real samples first, so we don't guess the format (see open questions).
3. **Forward or share the email or SMS to the app.** Later, and it depends on platform.

## Out of scope for this version

- Fetching PNR status from anywhere
- Live position updates
- Numeric confirmation odds
- Accounts, or storing bookings on a server

## Open questions

- **Stack.** Decided: Flutter. Which platforms to target first is still open.
- **Real samples.** We need a few real IRCTC confirmation emails and SMSes (with personal details stripped) to write a parser against. What does the text actually look like for WL, RAC and CNF?
- **Privacy.** PNRs and passenger details are personal. Could this run entirely on the device with nothing stored?
- **RQWL and RSWL.** Sources are thin on these, so they need confirming with people who know, maybe from the IRFCA forum.
- **Chart timing.** Where do we get a reliable, current rule per train?
