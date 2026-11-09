# Product challenge: Northwind all-hands

Thanks for taking the time. This exercise should take 3 to 4 hours. Please stop at 4. We care about how you think and build, not polish.

## The situation

Northwind Group (12,000 employees, 40 sites) streamed a CEO all-hands last week. The Head of Internal Communications says:

> "I think it went fine, but I have no idea who actually watched, who had a bad experience, or what we should do differently next time. Help me."

Start with `data/event_brief.md`. All data in this repository is synthetic.

## What we ask you to do

1. Decide who your user is and what problem is worth solving. Write it down.
2. Decide what to build and, just as important, what not to build.
3. Build a thin, working slice that uses AI in a way you can defend. A script, a small web app, a notebook or a CLI are all fine. Your stack, your choice.
4. Tell us how you would take this further.

## What to put in your repository

- `PROBLEM.md`: user, problem, evidence from the data, what success looks like (1 page max)
- `SOLUTION.md`: options you considered, what you chose and why, what you cut, risks, next 3 steps (1 page max)
- `AI_LOG.md`: how you used AI. 3 to 5 key moments: what you asked, what it got wrong or missed, what you changed
- Working code with a README so we can run it in under 5 minutes
- Optional: a 3 minute screen recording of the demo

## Ground rules

- Use any AI tools you like. Please keep usage proportionate. You do not need an expensive setup to do well here.
- Do not use data from your current or past employers.
- Tell us how many hours you actually spent.
- Questions are welcome by email. We will share answers with all candidates.
- Share your repository (private is fine, invite the person who sent you this) 24 hours before the review conversation.

## Data

| File | What it is |
| --- | --- |
| `data/event_brief.md` | Context, how delivery works, what stakeholders said |
| `data/event_schedule.md` | Agenda with times (UTC) |
| `data/sessions.csv` | Raw export, one row per viewer session |
| `data/sites.csv` | Office list with network ranges and headcount |
| `data/survey_comments.json` | Free-text feedback from the optional post-event survey |

### sessions.csv fields

The structure follows the platform's viewer export. All times are UTC. The file is a raw export and has not been cleaned.

| Field | Meaning |
| --- | --- |
| `viewerId` | Identifier of the viewer. A viewer who leaves and rejoins can have more than one session |
| `deviceType` | laptop, desktop, mobile, tablet, meeting_room |
| `os`, `app` | Operating system and player/app used |
| `connectionType` | ethernet, wifi, vpn, cellular |
| `publicIp`, `privateIp` | Network addresses seen by the platform. `privateIp` can be matched to the CIDR ranges in sites.csv |
| `siteCode` | Site the platform assigned to the session, matching `Site Code` in sites.csv |
| `reliabilityScore` | 0 to 1 score computed by the platform for the session. Higher is better. The exact formula is not documented |
| `rebufferingEvents` | Number of times playback stalled |
| `rebufferingTime` | Total stalled time, in seconds |
| `viewingTime` | Time spent watching, in seconds |
| `startedAt`, `endedAt` | Session start and end, ISO 8601 |
| `cdnTraffic` | Bytes delivered from outside the corporate network |
| `ecdnTraffic` | Bytes delivered from inside the corporate network |
| `cdnResponses`, `cdnErrors` | Segment requests to the CDN and how many failed |

### sites.csv fields

`CIDR`, `Site Name`, `Site Code`, `ASN`, `Country ISO`, `State ISO`, `City`, `Latitude`, `Longitude`, `VPN` (true for the pseudo-site that covers remote staff on VPN), `Employees` (headcount assigned to the site).

### survey_comments.json fields

`commentId`, `siteCode` (may be empty), `submittedAt`, `rating` (1 to 5), `language` (ISO code), `text`.
