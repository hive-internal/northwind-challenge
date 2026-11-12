# Product challenge: Northwind all-hands

Thanks for taking the time. This exercise should take 3 to 4 hours. Please stop at 4. We care about how you think and build, not polish.

## The situation

You are a product manager. Your product helps companies see how employees experience their live events, and act on it. Northwind Group (12,000 employees, 40 sites) streamed a CEO all-hands last week. Their Head of Internal Communications says:

> "I think it went fine, but I have no idea who actually watched, who had a bad experience, or what we should do differently next time."

Start with `data/event_brief.md`. Evaluate the context, make assumptions and state them clearly.

## What we ask you to do

1. **Define the problem.** Who is your user, and what problem are you solving for them? Put it in `PROBLEM.md` (1 page max).
2. **Design the solution.** How would you approach solving that problem? Cover the options you considered, what you chose and why, and the risks. Put it in `SOLUTION.md` (1 page max).
3. **Build a small slice with AI.** Deliver a small, working slice of your solution, using AI. It could be a script, a prototype of a small web app or a notebook. Use the stack and tools you prefer. Describe exactly how you used AI in `AI_LOG.md`: key moments, what you asked, what it got wrong, what you changed. Include a README.
4. **Measure.** How would you know the solution works? Add this to `SOLUTION.md`.
5. **Take it further.** What would you do next? Add this to `SOLUTION.md`.

Share your repository (private is fine, invite the person who sent you this) 24 hours before the review conversation. Be ready to present and demo it locally in the interview.

## Ground rules

- Use any AI tools you like. Keep usage proportionate. You do not need an expensive setup to do well here.
- Do not use data from your current or past employers.
- All data here is synthetic. It only suggests the kinds of challenges enterprise video users experience and is not real.

## Data

| File | What it is |
| --- | --- |
| `data/event_brief.md` | Context, how delivery works, what stakeholders said |
| `data/event_schedule.md` | Agenda with times (UTC) |
| `data/sessions.csv` | Raw export, one row per viewer session |
| `data/sites.csv` | Office list with network ranges and headcount |
| `data/survey_comments.json` | Free-text feedback from the optional post-event survey |

### sessions.csv fields

All times are UTC. The file is a raw export and has not been cleaned.

| Field | Meaning |
| --- | --- |
| `viewerId` | Identifier of the viewer. A viewer who leaves and rejoins can have more than one session |
| `deviceType` | laptop, desktop, mobile, tablet, meeting_room |
| `os`, `app` | Operating system and player/app used |
| `connectionType` | ethernet, wifi, vpn, cellular |
| `publicIp`, `privateIp` | Network addresses seen by the platform. `privateIp` can be matched to the CIDR ranges in sites.csv |
| `siteCode` | Site assigned to the session, matching `Site Code` in sites.csv |
| `reliabilityScore` | 0 to 1 score computed by the platform for the session. Higher is better. The formula is not documented |
| `viewingTime` | Time spent watching, in seconds |
| `startedAt`, `endedAt` | Session start and end, ISO 8601 |

### sites.csv fields

`CIDR`, `Site Name`, `Site Code`, `ASN`, `Country ISO`, `State ISO`, `City`, `Latitude`, `Longitude`, `VPN` (true for the pseudo-site that covers remote staff on VPN), `Employees` (headcount assigned to the site).

### survey_comments.json fields

`commentId`, `siteCode` (may be empty), `submittedAt`, `rating` (1 to 5), `language` (ISO code), `text`.
