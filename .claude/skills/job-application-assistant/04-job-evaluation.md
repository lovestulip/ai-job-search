# Job Evaluation Framework

<!-- SETUP: Skill match areas and career goals are personalized by running /setup -->

## Scoring Dimensions

Evaluate each job posting against these five dimensions:

### 1. Technical Skills Match (0-100)
How well do the required/preferred skills align with the candidate's capabilities?

| Score | Meaning |
|-------|---------|
| 80-100 | Core requirements are primary skills |
| 60-79 | Most requirements match, 1-2 gaps that are learnable |
| 40-59 | Partial match, significant upskilling needed |
| 0-39 | Fundamental mismatch |

**Strong match areas:** Content strategy and writing (blog, help center, docs, announcements), technical documentation, editing/QA of AI-generated content, cross-functional collaboration with engineers, Jira/GitHub workflows
**Moderate match areas:** SQL, reading TypeScript/TSX codebases, REST APIs/caching concepts, SaaS onboarding and account-health thinking
**Weak match areas:** Formal marketing positioning/demand-gen frameworks (actively learning, not yet expert), SEO, paid growth/performance marketing, people management

### 2. Experience Match (0-100)
Does work history align with what they're looking for?

| Score | Meaning |
|-------|---------|
| 80-100 | Direct experience in the same domain and role type |
| 60-79 | Related experience, transferable skills clear |
| 40-59 | Adjacent experience, would need to make the case |
| 0-39 | Unrelated experience |

**Strong:** Technical writing/documentation, help center content, incident/status communication, editing AI-generated content, developer-tool and open-source-adjacent products
**Moderate:** Blog/newsletter content, product marketing announcements, brand voice/positioning work (Lightfall is the first real rep, not 8 years of it)
**Entry-level:** Formal content marketing/demand-gen roles, SEO-driven content roles, paid-channel content

### 3. Behavioral/Culture Fit (0-100)
Does the role and company culture match the behavioral profile?

| Score | Meaning |
|-------|---------|
| 80-100 | Culture strongly matches behavioral preferences |
| 60-79 | Mixed signals but mostly compatible |
| 40-59 | Some friction areas |
| 0-39 | Significant culture mismatch |

**Red flags to research:** Department disorganization, work dominated by maintenance over development, poor chemistry with leadership, culture mismatches. Check reviews, media coverage, LinkedIn connections, and network contacts for insider perspective.

### 4. Location & Logistics (Pass/Fail + Notes)
- Fully remote, any timezone that overlaps Pacific business hours: PASS
- Fully remote but requires heavy overlap with a non-compatible timezone (e.g. all-hours-CET with no PT overlap): FLAG (discuss with user)
- Remote with occasional/required office presence: FAIL (deal-breaker - fully remote is required)
- Requires relocation: FAIL (deal-breaker)
- Role is people-management (manages reports) rather than individual contributor: FAIL (deal-breaker)
- Role is centered on high live-call volume (e.g. a phone-heavy support or sales queue) rather than written/async work: FLAG (discuss with user - not an automatic fail, but a friction point to weigh against the rest of the role)

### 5. Career Alignment & Motivation (0-100)
Does this role advance career goals and contain tasks that energize?

| Score | Meaning |
|-------|---------|
| 80-100 | Strongly aligned with career direction, clear growth path |
| 60-79 | Good role but only partially aligned with long-term goals |
| 40-59 | Decent job but doesn't build toward career goals |
| 0-39 | Dead end or backwards step |

**Career goals:**
- Pivot from technical support/account management into a Content Strategist role that uses both the writing craft and the technical fluency built over 8 years
- Own a product's content system end-to-end (docs, help center, blog, announcements), not just execute a content calendar written by someone else
- Build a track record as a paid Content Strategist that stands independently of the unpaid Lightfall work

**Motivation filter:** Evaluate not just whether you *can* do the tasks, but whether the tasks will *energize* you. Consider:
- Tasks that energize: writing and editing (docs, blog, help center, announcements), digging into a technical system to explain it accurately, catching and fixing errors (in content or in a product), working directly with engineers/founders
- Tasks that drain: high-volume live call queues, people management, roles where content is purely templated/formulaic with no ownership over voice or strategy
- Non-task factors: async-first culture, trust-based/light-touch management, small or founder-led teams

**Life situation alignment:** Consider personal constraints:
- **Security**: Actively job searching; Lightfall is unpaid, so a paid role is a near-term priority, not optional
- **Flexibility**: Fully remote required; needs working hours that overlap Pacific business hours, but is open to companies based anywhere in the world on that basis
- **Professional development**: Wants to build formal content strategy/positioning experience and credentials to back up the pivot from technical support/CS into content

### 6. Salary Benchmark (Optional)

If the salary lookup tool is configured (`salary_data.json` exists), look up the company:
```
python salary_lookup.py "<Company Name>" --json
```

If a city is known from the posting, add `--city "<City>"` to narrow results.

Present findings as:
```
### Salary Benchmark
| Metric | Value |
|--------|-------|
| [Category] index | XX.X (+/-X.X% vs baseline) |
| Overall index | XX.X (+/-X.X% vs baseline) |
```

Interpret results relative to the baseline defined in the data file's metadata. For index-based data, higher typically means above-market compensation.

If the salary tool is not configured, skip this section.

## Output Format

Present the evaluation as:

```
## Job Fit Evaluation: [Role] at [Company]

| Dimension | Score | Notes |
|-----------|-------|-------|
| Technical Skills | XX/100 | [brief note] |
| Experience Match | XX/100 | [brief note] |
| Behavioral Fit | XX/100 | [brief note] |
| Location | PASS/FAIL | [brief note] |
| Career Alignment | XX/100 | [brief note] |

**Overall Score: XX/100** (weighted average of scored dimensions)

### Verdict: [Strong Fit / Good Fit / Moderate Fit / Weak Fit / Poor Fit]

### Key Strengths for This Role
- [bullet points]

### Gaps to Address
- [bullet points]

### Recommendation
[1-2 sentences: apply/skip/apply with caveats]

### Company Research Checklist
- [ ] Checked company website (mission, values, recent news)
- [ ] Checked review sites (Glassdoor, Jobindex, etc.)
- [ ] Checked LinkedIn for team size, recent hires, connections
- [ ] Checked media for restructuring, growth, or workplace issues
- [ ] Identified network contacts who may know the team/manager
```

## Weighting
- Technical Skills: 30%
- Experience Match: 25%
- Behavioral Fit: 15%
- Career Alignment: 30%

(Location is pass/fail, not weighted)

## Thresholds
- **Strong Fit** (75+): Definitely apply, tailor everything
- **Good Fit** (60-74): Apply, address gaps in cover letter
- **Moderate Fit** (45-59): Consider carefully, discuss with user
- **Weak Fit** (30-44): Probably skip unless strategic reasons
- **Poor Fit** (<30): Skip

## Pre-Application: Call the Employer (Best Practice)

Before writing the application, consider whether the candidate should call the contact person listed in the posting. **Only call if there are substantive questions** - never call just to "be remembered."

### When to Suggest Calling
- The posting has unclear or ambiguous requirements
- It's unclear which competencies are essential vs. nice-to-have
- The role description is vague about day-to-day tasks
- There's a named contact person who invites questions

### Good Questions to Ask
- "What are the primary challenges in this role?"
- "How is time typically divided across the listed responsibilities?"
- "Which competencies are most critical for success in this position?"
- "What does success look like in the first 6-12 months?"

### Rules for the Call
- Prepare a 30-second "elevator pitch" about your background in case they ask
- The call's purpose is **gathering information**, not delivering a pitch
- Take notes - use what you learn to tailor the application
- Reference the conversation naturally in the cover letter ("After speaking with [name], I was especially drawn to...")
