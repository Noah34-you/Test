# #2 — PO / Order-Entry Automation for Distributors (DISCOVERY ONLY)

**One-sentence pitch:** *"Emailed POs become entered orders in minutes, with zero manual keying and
zero entry errors."*

**Status: interviews only. No selling, no building, until Play #1 is generating cash.**

## Problem

- **Who:** Inside-sales / customer-service teams at wholesale distributors and suppliers
  (electrical, plumbing, building materials, industrial). Customers email PDF POs; staff re-key
  them into the ERP (Epicor, P21, Eclipse, SAP B1, NetSuite, even QuickBooks).
- **How often:** All day, every day. A mid-size distributor keys hundreds of POs/week.
- **Current workaround:** Humans re-typing. Sometimes offshore data entry. EDI exists but only the
  biggest trading partners use it; the long tail is email + PDF forever.
- **How painful:** 5–15 min per order × volume = multiple FTEs. Keying errors cause wrong
  shipments, returns, credit memos — errors cost far more than the labor.
- **Who pays / cost today:** Ops/branch manager or VP of ops. 2 order-entry FTEs ≈ $120k+/yr loaded.
  Existing vendors (Conexiom, Esker) charge tens of thousands/yr and have long implementations —
  which is our opening at the mid-market.

## Why us

- **Mom's network and fluency** — she knows purchasing workflows, the titles who own this pain, and
  how these companies buy. That's the hard part; the OCR/LLM extraction is the easy part for us.
- Genuine data moat over time: customer-specific PO layouts, SKU/UoM cross-reference mappings,
  vendor catalogs. Each client makes the system smarter and stickier.
- High-9 SaaS ceiling: this is a real software category (Conexiom validated it) with mid-market
  whitespace.

## Honest risks

1. **Sales cycle.** Mid-market ops buyers take 1–3 months and want references. Wrong first play
   with zero capital — right second play funded by #1.
2. **Accuracy bar is brutal.** 98% isn't good enough when a mis-keyed SKU ships a pallet of the
   wrong pipe. Human-in-the-loop review is mandatory for a long time — which conveniently *is* the
   service phase.
3. **ERP integration is the real product.** Extraction is commodity; writing clean orders into P21
   or Epicor is the moat and the implementation cost.

## Staging (drafted now, executed later)

- **MVP:** Client forwards PO emails to an inbox we run. We (humans + LLM/OCR assist) return a
  validated, ERP-ready order file (or key it directly in their ERP via remote session) within 30
  minutes, error-checked against their catalog. Charge per-order or monthly.
- **Service:** Human validation of every order; exception handling (missing SKUs, price mismatches)
  by phone/email like a real CSR would.
- **Automation:** LLM extraction + SKU mapping + validation rules; humans only touch exceptions.
- **SaaS:** Self-serve inbox → ERP pipeline with a review UI; per-order or tiered monthly pricing.

## Discovery plan (the only work allowed on this play right now)

Goal: 8–10 interviews by end of August via Mom's introductions. Questions:

1. How many orders arrive by email/PDF per week? Who keys them?
2. What does an order-entry mistake cost you? Last bad one?
3. Have you looked at Conexiom/Esker/EDI? Why didn't it happen (or why did it)?
4. If emailed orders just appeared in [ERP] correctly, what would that be worth per month?
5. Who besides you would need to approve buying a fix?

**Success signal to activate this play:** 3+ interviewees independently describe the pain as an FTE
cost or error cost ≥ $3k/mo AND at least one says "call me when it works."
