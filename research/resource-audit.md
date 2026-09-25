# Resource Audit

Running notes on each data source we're looking at: what it covers, how reliable it is, and what its terms allow.

## PNR status and the IRCTC API question

*Checked 2026-09-25.*

**Short version:** there is no public official API for PNR status. The interim plan from our meeting was to scrape a partner platform like Ixigo. Their terms explicitly ban that, so it needs a rethink before any code gets written.

### Official routes

- **indianrail.gov.in PNR enquiry.** This is the official PNR lookup and it has no API. The page is gated by a captcha. Getting around that captcha automatically is exactly what it's meant to block, so this isn't a route we can take.
- **NTES (enquiry.indianrail.gov.in).** CRIS's official system for running status and train enquiries. It doesn't cover PNR, and it has no public API either.
- **IRCTC authorised partners (B2B / Principal Service Provider).** This is how apps like RailYatri and Trainman get official access. The bar is built for large booking agencies: the B2B norms ask for at least 500 agents and Rs. 5 crore in annual turnover, and the fee tiers run into lakhs. It's not realistic for a passion project.

### Resellers

- **API resellers (AOPAY, Roundpay, Travelopro, ZuelPay and others).** They say they're IRCTC-authorised and advertise PNR status alongside booking APIs. They're aimed at travel agents and OTAs and are paid. We'd need to check pricing, whether they'll sell PNR lookup on its own, and whether we'd be allowed to show the data publicly.
- **RapidAPI "PNR status" APIs.** These are unofficial and it's unclear where the data comes from. They're probably scraping something underneath, which means relying on them just hands the terms problem to someone else.

### Partner platforms (the scraper idea)

- **Ixigo.** The terms of use explicitly prohibit scrapers, bots, spiders and data mining. They also ban compiling their data into a database without written permission and using it commercially without authorisation. robots.txt disallows `/api/`, `/trains/v1/search/` and `/track/`. Disputes go to Delhi courts under Indian law. Trainy is public and built in the open, so a scraper here would be visible to anyone, Ixigo included.
- **ConfirmTkt.** Ixigo acquired it, so the same position probably applies. Its terms page didn't load when I checked.
- **Trainman, RailYatri.** Both are authorised partners. I haven't checked their terms yet because the terms page URLs returned 404s.

### Options that don't need scraping

These are ideas to discuss. None of them have been decided.

1. **Ask Ixigo for permission.** Their terms prohibit this "without written permission", so permission is a real path. Their robots.txt even invites bots and geeks to email them. A small railfan project built in public might get a hearing.
2. **Price a reseller API.** It's possibly the fastest legitimate route if one will sell PNR lookup on its own at hobby scale.
3. **Start with booking details the user provides.** Users could enter or forward their own IRCTC booking confirmation, and Trainy would explain the waitlist type and odds from that. It won't give live updates, but it covers the "make waitlists understandable" idea with no scraping at all.

### Static data that is fine to use

- **data.gov.in, Indian Railways Train Time Table.** Official open government data with train routes, distances, and arrival and departure times.
- **datameet/railways on GitHub.** Station and train data released under CC0. The last update was in 2016, so it's stale, but it's clean for station coordinates and for bootstrapping.

### Sources

- [ixigo Terms of Use](https://www.ixigo.com/about/terms-of-use/)
- [ixigo robots.txt](https://www.ixigo.com/robots.txt)
- [Indian Railways PNR Enquiry](https://www.indianrail.gov.in/enquiry/PNR/PnrEnquiry.html?locale=en)
- [NTES](https://enquiry.indianrail.gov.in/ntes/)
- [IRCTC Norms for Web Services B2B Scheme](https://contents.irctc.co.in/en/NormsforB2B.pdf)
- [IRCTC Authorised Principal Service Providers](https://contents.irctc.co.in/en/IRCTC%20Authorised%20Principal%20Service%20Providers.pdf)
- [AOPAY Train API](https://aopay.in/train-api)
- [RapidAPI: PNR Status Indian Railways](https://rapidapi.com/pnr_status/api/pnr-status-indian-railways)
- [data.gov.in: Indian Railways Train Time Table](https://www.data.gov.in/catalog/indian-railways-train-time-table)
- [datameet/railways](https://github.com/datameet/railways)
