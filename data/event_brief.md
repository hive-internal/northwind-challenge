# Event brief: Northwind Q3 all-hands

## Company
Northwind Group is a fictional software and services company with 12,000 employees. About 8,700 work in 39 offices across Europe, North America, Asia Pacific, Latin America and Africa. About 3,300 work remotely and connect to the corporate network through VPN. Everything in this exercise is invented.

## The event
On Wednesday 4 November 2026 the CEO held the quarterly all-hands, live streamed to everyone. It was the first all-hands that also announced an organisation change, so Internal Communications cared more than usual that people actually saw it. The agenda is in event_schedule.md. A replay was available for 7 days.

## How the stream is delivered
Northwind uses an enterprise video platform. Each viewer's player gets video segments from one of two sources:

- **CDN traffic:** segments downloaded from outside the corporate network (the internet CDN).
- **eCDN traffic:** segments served from inside the corporate network, for example from other viewers' players in the same office, which saves office internet bandwidth.

The platform records one row per viewer session in sessions.csv. See the README for field definitions.

## What we have
- **sessions.csv:** raw export of viewer sessions from the video platform.
- **sites.csv:** the office list maintained by IT, mapping network ranges to sites, with headcount.
- **survey_comments.json:** free-text feedback from the post-event survey (the survey was optional, so it is not a random sample).
- **event_schedule.md:** the agenda.

We do not have: reliable attendance records, any marketing or invitation data, or any data about how the audio was set up in meeting rooms.

## What stakeholders told us

**Maja Lindqvist, Head of Internal Communications**
"I think it went fine, but I have no idea who actually watched, who had a bad experience, or what we should do differently next time. I got a handful of angry emails and some lovely ones, and I cannot tell which of them is typical. The next one is in February and the CEO wants everyone to be able to join."

**Daniel Okafor, Head of IT Network**
"Our monitoring showed no incidents on the corporate network that day. I would not expect the stream to be the problem. To be fair, we do not monitor what happens on people's home connections or on VPN."

## Constraints
- No budget for new hardware this quarter.
- Three more all-hands events next year, plus smaller team events.
- Internal Communications has no analyst, so whatever you propose has to be usable by non-technical people.
