# Trainy

Flighty for trains: nerd-level detail on Indian Railways, for people who actually care which loco is up front.

## What Trainy is

Trainy is a train app for Indian Railways enthusiasts. The idea is simple: the way Flighty surfaces aircraft type and flight history for aviation people, Trainy surfaces locomotive type, rake composition, punctuality history and other details that railfans care about.

Indian Railways is a fantastic system to follow and a confusing one to travel on. Booking is uncertain, waitlists are opaque, and the information that exists is scattered across forums, unofficial APIs and tribal knowledge. The goal of Trainy is certainty and clarity: tell you what is actually going on, with the level of detail a train nerd wants.

## Who it's for

For railfans. People who know what a WAP-7 is, who notice when a rake gets swapped, who have opinions about which side of the train to sit on, and who want the data behind the journey and not just the ticket.

## Who it isn't for

Not for daily commuters. Local and suburban commuter features (Mumbai suburban indicators and similar) are explicitly out of scope. There are apps that do that well already, and trying to serve both audiences would water down the thing that makes this interesting.

## Current status

Research phase. There is no app code yet and no tech stack picked.

Right now the work is figuring out what data exists, what is reliable, and what is actually legal and practical to use. The `research/` folder is where those notes will live.

## Ideas we're exploring

Nothing here is a commitment. These are the directions that seem worth investigating:

- **Loco and rake details per train.** Which locomotive class is hauling it, how the rake is put together.
- **Punctuality history.** Not just "is it late today" but how this train behaves over time.
- **Making waitlists understandable.** RLWL, GNWL, Tatkal and the rest are genuinely confusing. Explaining what the type means, and giving an honest sense of the odds, feels like real value.
- **Window view prediction.** Combining sun position with seat and coach data to guess which side gets the view, and which side gets the glare.
- **Delay probability by station.** Using historical running data to show how likely a train is to be late at each stop, the way Flighty does for flights.
- **Loco and consist origin tracking.** Where did today's loco and rake come from? The train equivalent of tracking a plane's tail number to see its previous flight.
- **Stop durations on long routes.** How long the train actually halts at each station, so you know whether there's time to step out.
- **Onward connection times.** How much time you have between arriving and your next ground transport leg.
- **Live signal state per track section.** A long shot. This data is probably not public, likely for safety reasons, but it came up and it's worth noting.

## Data sources under investigation

None of these are confirmed. Terms of use are still being checked, and that will shape what is possible.

- **IndiaRailInfo.** Broad coverage of trains, schedules and running data.
- **IRFCA LocoDB and forum.** The deepest source of locomotive knowledge, plus decades of community discussion.
- **Unofficial Indian Railways APIs.** Various ones exist. Reliability and terms vary a lot.
- **Real Time Trains (UK).** Not a data source for India, but a strong reference for how to present this kind of information well.

### Known gaps

- **Loco assignment.** Nothing out there reliably maps which locomotive is assigned to which train. That is one of the most interesting things a railfan would want, and right now there is no dependable source for it. Solving or working around this is an open question.
- **PNR status.** There is no public official API for PNR status. The official routes are either captcha-gated or limited to large booking agents, and the big travel apps don't allow scraping in their terms. Details are in [`research/resource-audit.md`](research/resource-audit.md).

## Building in public

This is a passion project and it's being built in the open, starting from the research notes rather than from a finished app.

If you're a railfan, especially if you know these data sources well or have thoughts on the loco assignment problem, feedback is very welcome. Open an issue, or just tell me where I'm wrong. Early input shapes this more than late input.
