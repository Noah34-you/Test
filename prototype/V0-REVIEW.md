# V0 Review — What This Prototype Assumes, Hides, and Gets Wrong

Written before showing it to a single contractor, so we know what we're testing.
The prototype's job is to provoke corrections. Every item below is a question to put
in front of real users, not a defect to quietly fix first.

---

## 1. Persona critiques

### Contractor Owner (Miguel, 52, runs a 6-person shop from his truck)

- **"I'm not going to look at a dashboard."** He lives in his truck and his texts. The
  dashboard is really for the office. For the owner, the product might be *three texts a
  week and a Friday one-pager*. If demo feedback confirms this, the owner-facing product
  is SMS + a weekly PDF, and the dashboard is an office tool. V0 wrongly assumes the
  owner logs in.
- **"Who's talking to my customers?"** The text-back bubbles say "Reyes (auto)". He will
  ask: what happens when it says something wrong, quotes a price I didn't approve, or
  promises a slot I can't staff? The $285 leak-detection price in Flow 2 is exactly the
  kind of thing an owner never lets software say unsupervised. V0's "human confirms
  every booking" rule needs to extend to "human approves every price."
- **"Recovered revenue" will be challenged.** $18,450 recovered — says who? He'll argue
  Dana would have called back in the morning anyway. Attribution is the #1 number the
  entire business rests on, and V0 asserts it instead of defending it. We need an
  attribution rule he agrees with *at onboarding* (e.g., "only jobs from calls you missed
  outside hours + quotes silent 5+ days"), or the Friday report reads as marketing.
- **Trade benchmark "~22% conversion" is invented.** Cut it or source it before demos.
- He will like: response-time before/after, the unconfirmed-appointment alarm, quote
  chasing (nobody in his shop does it and he knows it).

### Office Manager (Carla — actually runs everything)

- **This tool creates work for her before it saves any.** Every "Needs attention" item is
  her queue. If the AI qualifies 10 leads a day, she now has 10 confirmations to do on
  top of her old job. The pitch to her must be "the phone interrupts you less," not
  "here's another inbox." Watch whether she sees it that way in demos.
- **Where's the calendar?** She books against a real schedule with two techs, drive
  times, and jobs that run long. V0 hand-waves "slots come from real calendar
  availability." She will immediately ask what happens when the 8–10 slot the AI offered
  at 9:48 PM is gone by 7 AM. (Answer we're testing: AI holds nothing, offers only
  windows she pre-marked as offerable. Is that acceptable to her?)
- **Duplicate hell.** Dana calls the office line at 8:01 AM before Carla confirms — does
  the system know it's the same person mid-flow, or does it text her again? V0 has no
  answer. Real CSRs merge people in their heads all day.
- **She already has software.** If the shop runs Housecall Pro / ServiceTitan / Jobber,
  a lead living in *our* dashboard and not in *her* system is a bug, not a feature. V0's
  "we book into Google Calendar" is only plausible for shops with no FSM software —
  which may actually be the right first segment. Validate that segment choice.
- She will like: the thread view (she reconstructs these from voicemail + sticky notes
  today), templates in her own words, the review-request automation.

### Dispatcher (J. Silva — assigns techs, fights the schedule)

- **V0 barely exists for him.** He appears in Settings and gets "booked-job details."
  There is no schedule board, no assignment step ("Confirm & dispatch" — dispatch *who*?),
  no notion of parts on the van, drive time, or emergency insertion. Honest position for
  demos: dispatch is out of scope in V0; we hand a confirmed, qualified appointment to
  whatever process exists today. If demo feedback says booking without assignment is
  useless, that's a major scope finding.
- **Urgency 9/10 at 9:42 PM raises the on-call question.** Who decides a true emergency
  (burst pipe flooding) warrants waking someone? V0 pages the on-call phone at
  urgency ≥ 8 — the *thresholds and liability* of that rule need a contractor's opinion.
  A flooded house that got a polite text until morning is a lawsuit-shaped story.

---

## 2. Assumptions (each is a test, not a fact)

**Behavioral**
1. Customers who ring out will engage with a text within minutes — including 55+
   homeowners at 9:42 PM.
2. Customers will answer 4–6 qualification questions by SMS without dropping off.
3. Two offered time slots beat "when works for you?" (we believe it; unproven here).
4. The office will act on "Needs attention" within hours (the whole loop dies if not).
5. Owners will let an automated system state prices (detection fees, quote figures).
6. Contractors will let quote reminders go out in their name without pre-approval each
   time — or is one-click approval the actual requirement?

**Technical / operational**
7. Conditional call-forwarding is available and configurable on their phone setup
   (landline PBX, Google Voice, personal cell — wildly variable in reality).
8. Caller ID gives us a usable callback number (blocked/spoofed/office trunk lines
   don't).
9. Voicemail transcription is accurate enough to seed the lead ("kitchen sink leak").
10. A2P 10DLC registration, opt-out handling, and quiet-hours compliance are solved
    (TCPA — texting a 9:42 PM caller back at 9:42 PM is fine; re-texting at 8 AM after
    silence is where consent questions start. Legal review before pilot #1.)
11. Close probability on quotes can be estimated at all in V1 (it's a placeholder
    heuristic; the *column* is what we're validating, not the math).
12. "Estimated ticket value" per lead is guessable from job type without offending the
    contractor's sense of their own pricing.

**Business**
13. The shop has enough missed-call volume for weekly proof (below ~15 missed calls/mo
    the Friday report is embarrassingly empty).
14. Attribution methodology will be accepted (see owner critique).
15. One default follow-up sequence fits all trades; V0 has no per-trade branching.

---

## 3. Edge cases the prototype ignores

**Inbound chaos**
- Same customer, multiple channels: calls, then fills the form, then calls again → three
  leads or one?
- Existing customer calls (should skip qualification: "Hi Dana, calling about the water
  heater we installed?") — V0 treats everyone as new.
- Spanish-language callers — huge in Bay Area trades; V0 is English-only.
- Landline callers who cannot receive SMS (a large share of 65+ homeowners). Text-back
  silently fails; V0 shows no fallback (should trigger: voicemail-transcript lead +
  "call back" task instead).
- Robocalls, solicitors, wrong numbers, supplier calls on the same line — the sequence
  would cheerfully nurture a telemarketer for 7 days.
- Photos via MMS ("here's the leak") — contractors *want* these; V0 threads are
  text-only.

**Conversation failures**
- Customer replies with a phone call instead of a text mid-sequence.
- Customer replies "STOP" then calls again next week — suppression vs. genuine new lead.
- AI misreads urgency in both directions: gas-smell described casually (under-triage =
  dangerous) or "no hot water" from a tenant of a landlord customer (over-triage =
  wrong payer entirely).
- Tenant vs. owner vs. property manager: who approves work, who pays, who gets texts —
  V0 has a single "customer."
- Customer negotiates in-thread ("can you do $2,400?") — AI must hand off, never haggle.

**Scheduling reality**
- Offered slot taken before office confirms (the Dana race condition — V0's answer is
  "human confirms," but the *customer* thinks she has an appointment).
- Job before Dana's runs 3 hours long; nothing reschedules or notifies.
- After-hours emergency that needs a truck *tonight*, not tomorrow 8 AM.
- Two leads pick the same slot 5 minutes apart overnight.

**Data & trust**
- Recovered-revenue double count: Priya's $450 counts as "recovered," but she'd already
  hired them once — repeat customer vs. rescued lead.
- Quote marked "won" offline (customer called the owner's cell) — stale reminders then
  fire at a customer who already said yes. Mortifying; needs a dead-simple "mark won/lost"
  everywhere.
- Owner's spouse answers the missed call from their personal cell — system never learns
  the lead was handled.

---

## 4. What breaks in the real world (ranked by damage)

1. **A wrong automated message to a real customer.** One hallucinated price, one tone-deaf
   reply to an angry customer, one text to a grieving household — and trust is gone
   shop-wide. Mitigation for pilots: constrained scripts, not open generation; human
   approval on anything with a number in it. (This is also why the *service phase* —
   us, manually — precedes automation.)
2. **TCPA / A2P compliance.** Unregistered traffic gets carrier-filtered (product
   silently stops working) or worse, fined. Must be solved before pilot #1, not after.
3. **The confirmation queue rots.** If Carla ignores the dashboard for a day, customers
   who "picked a slot" hear nothing. The system must escalate (SMS → call the office →
   call the owner), or unconfirmed promises are worse than voicemail.
4. **Forwarding misconfiguration.** One wrong star-code and either every call forwards
   (office bypassed, owner furious) or none do (we're billing for nothing). Needs the
   "Run test call" ritual weekly, not just at setup.
5. **Attribution dispute at renewal.** Month 3, owner says "those jobs would've come
   anyway," cancels. The agreed-upfront attribution rule is churn insurance, not
   reporting polish.
6. **FSM-software overlap.** Shops on ServiceTitan already have some of this; our lead
   record becomes the second source of truth nobody updates. Segment or integrate.
7. **Volume too low to feel.** A shop missing 4 calls a month sees an empty dashboard
   and cancels — qualification criteria (lead flow) protect us more than features do.

---

## 5. What to actually test in demos (the script)

Put the prototype in front of each person and watch for these specific reactions:

1. Dashboard, 10 seconds, then ask: **"What would you do first?"** (Pass: they point at
   Dana's unconfirmed appointment.)
2. Flow 1, stepping through: **"Where would you stop trusting it?"** Note the exact step.
3. Quote Recovery: **"Would you let this text go out as-is, or do you want to approve
   each one?"** (Determines whether the engine is auto-send or one-click-approve.)
4. Reporting: **"Do you believe the $18,450? What would make you believe it?"**
5. Settings → templates: **"Rewrite the missed-call text in your words."** (If they
   engage, they're imagining owning it. Strongest buying signal in the room.)
6. End: **"What's missing that would make this useless without it?"** — expect calendar
   truth, FSM sync, or dispatch. Whichever they name first is the next build priority.
