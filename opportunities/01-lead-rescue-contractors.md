# #1 — Lead Rescue for Trade Contractors (ACTIVE)

**One-sentence pitch:** *"Every call answered, every lead followed up within 60 seconds, every open
quote chased until it closes — you only swing hammers."*

## Problem

- **Who:** Trade contractors (HVAC, plumbing, electrical, roofing, remodel) doing ~$1M–$10M/yr.
  Owner or office manager is the de facto receptionist.
- **How often:** Daily. Industry surveys consistently put missed-call rates for home services at
  25–40%. Speed-to-lead research (Harvard/InsideSales) shows contacting a lead within 5 minutes vs
  30 minutes raises qualification odds ~21x. Most contractors respond in hours or never.
- **Current workaround:** Voicemail nobody checks, spouse answering phones, generic answering
  services ($1–2/min, take a message, no follow-up), or nothing.
- **How painful:** An HVAC replacement is a $8k–$15k ticket. Missing 2 calls a week that would have
  closed at even 20% ≈ $10k+/mo in lost revenue. They *feel* this — it's not a latent pain.
- **Who pays / cost today:** The owner. Cost is invisible (lost revenue) plus whatever they spend on
  lead gen they then waste — many pay $50–200/lead on Angi/Google LSA and let leads rot.

## Why us

- Dad's network = warm intros to exactly this buyer. Trust is the whole game with contractors.
- Manual delivery is genuinely feasible for 3–5 clients (call forwarding + a phone + scripts).
- Every piece automates cleanly later: voice AI answering, instant SMS-back, LLM-drafted follow-ups,
  quote-chasing sequences.

## Honest risks (co-founder pushback)

1. **Crowded space.** "AI receptionist for home services" has many funded players (answering
   services, Goodcall-style bots, CSR platforms). Our edge is not tech — it's **distribution (warm
   intros) + doing follow-up and quote-chasing, not just answering.** Most competitors stop at
   answering the phone. Revenue recovery, not reception, is the positioning.
2. **Small contractors are hard customers.** Cheap, churny, phone-averse. Mitigation: qualify hard —
   must have real lead flow (ads, LSA, Angi) or $1M+ revenue. A guy with a truck and 3 calls a week
   is not a customer.
3. **Dad's intros ≠ demand.** Intros get meetings. The missed-call audit (below) converts meetings
   into urgency with *their own numbers*.
4. **Weak moat / SaaS ceiling.** Fine. This play's job is cash flow, market learning, and a
   contractor customer base we can upsell (#4, #5) — while #2/#3 mature.

## The wedge: the Missed-Call Audit (free, 20 minutes of our time)

Call their business line 5 times over a week (after hours, lunch, mid-morning). Log what happens.
Pull their Google LSA/Angi spend if they share it. Present one page: *"You missed 3 of 5 calls.
At your average ticket, that's ~$X/month walking to your competitors."* Then pitch the pilot.
Nobody argues with their own missed calls.

## Staging

### MVP (< 2 weeks, ~$50 of tooling)
- Twilio number per client; conditional call-forwarding when unanswered/after-hours.
- Missed call → instant SMS to caller ("Sorry we missed you — this is X Plumbing, are you calling
  about a repair or a quote? We'll call you right back") + alert to us.
- **We** (humans) call the lead back within 60 seconds during business hours, qualify with a
  5-question script, book into their calendar (Google Calendar/Jobber/Housecall Pro — whatever they use).
- Weekly one-page report: calls rescued, jobs booked, estimated revenue recovered.

### Service (what humans keep doing)
- Live callback + qualification, appointment booking, quote follow-up calls, weekly report,
  escalation of emergencies to the owner's cell.

### Automation (after 5 clients)
- Voice AI answers overflow/after-hours directly; LLM qualifies and books.
- Automated SMS/email follow-up sequences on open quotes (day 2, 5, 10) with human-in-loop approval.
- Auto-generated weekly reports from call/booking data.
- Humans move to QA + exceptions only → margin goes from ~50% to ~90%.

### SaaS (self-serve, later)
- Dashboard: connect your number + calendar + quote list; the system answers, follows up, chases,
  reports. $199–399/mo. Data moat: trade-specific call/qualification corpus and close-rate benchmarks.

## Pricing

- **Founding 3 clients:** $0 setup, $500/mo, 30-day guarantee: *"If we don't book you at least
  [3] jobs from calls you'd have missed, you don't pay."*
- **Standard:** $750 setup + $750–1,500/mo depending on call volume.
- Anchor to outcome: one rescued HVAC job > a year of fees.

## Kill criteria (written now, before we're invested)

- 10 discovery calls without a single paid pilot → reposition or kill.
- Pilots run 60 days without provable recovered revenue → the pain isn't monetizable; kill.
- Churn > 30% in first 90 days across first 5 clients → wrong segment; requalify or kill.

## Path to $100M (so it's not a lifestyle business)

Lifestyle version: 30 retainer clients, $30k/mo, done. Venture version: own the **revenue-recovery
layer for the trades** — answering → follow-up → booking → payments/financing referral, priced per
recovered job (take-rate, not seat-fee), expanded nationally through trade distributors and
franchise networks. The wedge is the service; the company is the transaction layer it earns.

## Sales assets

See [`sales/lead-rescue-assets.md`](../sales/lead-rescue-assets.md).
