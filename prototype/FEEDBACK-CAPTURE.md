# Feedback Capture Sheet — V0 Review Sessions

Keep this open while someone reviews the prototype. Fill it in *during* the session,
in their words, not after from memory. One sheet per reviewer. The goal is to turn
"what did they think" into decisions we can act on.

Reviewer: ____________________   Role/lens: ____________________   Date: __________
Are they a real target user, or a proxy? ____________________

---

## 5 rules for running the session

1. **Don't sell. Don't explain.** Hand them the screen and shut up. The moment you
   narrate, you've contaminated the data. Silence is the instrument.
2. **Watch where their eyes go and where they hesitate.** Confusion is the signal —
   log the exact spot they paused or frowned.
3. **Capture verbatim.** Exact words > your summary. "I'd never let it say a price"
   is data; "she had concerns about pricing" is mush.
4. **Time the first action.** Put the dashboard up, say nothing, and note: how many
   seconds until they correctly point at Dana's unconfirmed appointment? (UX goal:
   under 10.) If they point somewhere else, that's a finding.
5. **End every screen with: "What's missing that would make this useless without it?"**

---

## Per-screen capture grid

For each screen, note what they *did* (eyes, clicks, hesitation) and *said* (verbatim).

| Screen | Watch for | Did / hesitated | Said (verbatim) |
|---|---|---|---|
| **Dashboard** | Seconds to first correct action. Do they trust the numbers? | | |
| **Flow 1** (after-hours call) | The exact step where they stop trusting the automation | | |
| **Flow 2** (web form 60s) | Reaction to the $285 price the system states on its own | | |
| **Lead detail** | Do they read the thread top-down? Is the summary believable? | | |
| **Follow-up Engine** | "Would you let these go out as-is, or approve each one?" | | |
| **Quote Recovery** | Do they believe the close-probability %? | | |
| **Reporting** | Do they believe the $18,450 recovered? What would make them? | | |
| **Settings → templates** | Ask them to rewrite the missed-call text in their own words | | |

---

## Verbatim quote log (the most valuable section)

Write down anything they say word-for-word, especially objections and "I wish it…"

- "
- "
- "
- "

---

## Decision triggers — if they say X, we do Y

These are the reactions that change what we build. Tick any that fire.

- [ ] "I'd never let software quote a price" → **quote/price approval must be human, always.**
- [ ] "This is just more work for me" (office mgr) → **reposition as fewer interruptions, not another inbox.**
- [ ] "Where's my calendar / this won't match my real schedule" → **calendar truth is the #1 build gap.**
- [ ] "It needs to be in [Housecall Pro / ServiceTitan / Jobber]" → **segment to no-FSM shops, or integrate.**
- [ ] "Those jobs would've come anyway" → **attribution rule must be agreed at onboarding.**
- [ ] "Confirm & dispatch — dispatch who?" → **booking-without-assignment may be incomplete.**
- [ ] They rewrote the SMS template unprompted → **strong buying signal; they're imagining owning it.**
- [ ] "What happens when it says the wrong thing?" → **lead with the human-in-the-loop / constrained-script story.**

---

## Red-flag reactions (stop and rethink, don't paper over)

- Shrug / "yeah, seems fine" with no engagement → they don't feel the pain. Wrong person or wrong problem.
- They can't find the one thing that needs attention → the dashboard's core promise failed.
- They'd want to turn off the automation entirely → we're solving a problem they'd rather own.

---

## If the reviewer is Mom (procurement / enterprise-buying lens)

Her instincts are on the *buy side* — use them where they're sharp, and discount them where they're not.

**Where her feedback is gold (trust it):**
- Approval chains — who signs off before money moves. Watch her reaction to anything the
  system does *without* a human approving. She's spent decades on exactly this.
- Vendor/quote follow-up cadence — she's chased suppliers for years; ask if our 5-step
  sequence feels right, too aggressive, or too soft.
- What an office/operations person needs to *trust* a number before acting on it.

**Where to discount it (she's a proxy, not the customer):**
- Whether a $2M plumbing owner will tolerate any given thing — that's Dad's read, not hers.
- Trade-specific urgency (gas smell, burst pipe) — outside her domain.

**Better use of her time — the distributor play she's actually built for:**
If she's engaged, walk her through the PO/order-entry concept (`opportunities/02`) and run
these live. This is feedback no one else can give us:
1. How many orders arrive by email/PDF per week at a shop her size? Who keys them?
2. What does an order-entry mistake cost — last bad one?
3. Did anyone ever pitch her Conexiom / Esker / EDI? Why did it or didn't it happen?
4. If emailed orders just appeared in the ERP correctly, what's that worth per month?
5. Who else has to approve buying a fix like that?
6. **The real ask: who are 3 people she'd introduce us to?**
