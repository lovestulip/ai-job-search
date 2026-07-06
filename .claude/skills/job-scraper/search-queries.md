# Search Queries for Job Scraper

## Search Sites

Primary (remote-first, US/global):
- **linkedin.com/jobs** - filter to Remote; broadest general coverage
- **hiring.cafe** - remote-focused aggregator pulling from Greenhouse, Lever, Workday, BambooHR, and company career pages. Direct WebFetch on hiring.cafe returns 403 (bot-blocked), including individual `/viewjob/` pages - use `WebSearch site:hiring.cafe` to find postings, then ask the user to paste the job description if a direct fetch is needed for `/apply`.
- **4dayweek.io** - jobs at companies offering a 4-day week, 9-day fortnight, or flexible/reduced hours, fully remote or remote-friendly. Same fetch limitation as hiring.cafe: WebFetch returns 403 on both the site and individual job pages, so rely on `WebSearch site:4dayweek.io` and paste-in job descriptions for `/apply`.

Secondary (company career pages via Google):
- `site:greenhouse.io` / `site:lever.co` / `site:ashbyhq.com` searches combined with role keywords, for direct ATS listings outside the aggregators above
- Direct Google searches with `site:` filters for known target companies

## Query Categories

Queries are grouped by priority. All roles must be fully remote - do not include queries that assume a specific city/commute radius.

### Priority 1: Content Strategist

These match the primary target direction.

```
site:linkedin.com/jobs "Content Strategist" remote
site:hiring.cafe "Content Strategist" remote
site:4dayweek.io "Content Strategist"
"Content Strategist" remote SaaS OR "developer tools"
```

### Priority 2: Content Manager / Marketing Content Manager

More marketing-adjacent framing of the same direction.

```
site:linkedin.com/jobs "Content Manager" remote
site:linkedin.com/jobs "Marketing Content Manager" remote
site:hiring.cafe "Content Manager" remote
"Content Manager" remote startup
```

### Priority 3: Technical Content Strategist / Content Ops

Leans on the technical support and documentation background.

```
site:linkedin.com/jobs "Technical Content" remote
site:linkedin.com/jobs "Content Ops" OR "Documentation Strategist" remote
"Technical Writer" OR "Technical Content Strategist" remote SaaS
site:hiring.cafe "Documentation" content remote
```

### Priority 4: Reduced-hours / 4-day work week (any of the above titles)

```
site:4dayweek.io/remote-jobs content
site:4dayweek.io "Content Strategist" OR "Content Manager"
```

## Location Filter

All roles must be fully remote. Location isn't a commute radius here, it's timezone overlap with Pacific business hours (roughly 9am-5pm PT) and whether the role is genuinely individual-contributor (not people management):

- **Ideal:** Remote, company based anywhere in the Americas (PT, MT, CT, ET) - full or near-full overlap
- **Acceptable:** Remote, company based anywhere in the world, as long as the posting doesn't require core hours entirely outside a reasonable PT overlap window
- **Borderline:** Remote but requires most meetings in European business hours (some PT-morning overlap only) - flag and ask before ruling out
- **Too far / fail:** Requires relocation, requires regular office presence, or the role is people-management rather than individual-contributor

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape 4-day week" -> Priority 4 queries + custom focus-specific queries
- "/scrape technical content" -> Priority 3 queries + custom focus-specific queries
