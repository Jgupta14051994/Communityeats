# CommuniEats — Decision Log

Chronological record of major product decisions. Each entry includes the decision, alternatives considered, rationale, and the signal that would reverse the decision.

---

## Decision #1 — Set community pickup discount at 30%

**Date:** March 2026  
**Decision:** 30% discount for community pickup tier  
**Status:** Active

**Alternatives considered:**
- 15% — Insufficient behavioral change; comparable to credit card cashback users already ignore
- 20% — Borderline; some uptake modeled but weak habit formation
- 30% — Creates genuine "moment of wow" on first use; drives word-of-mouth
- 40% — Economically unsustainable at early volume without picker supply

**Rationale:** Behavior change requires a threshold, not a gradient. 30% is above the "I'll plan for this" threshold for our target persona (Maya). It's also a number people share ("I got 30% off my lunch").

**Reversible if:** Community tier adoption >60% in first 30 days (discount may be unnecessarily high) OR complaint rate >10% (trust cost exceeds discount value).

---

## Decision #2 — 15-minute community pickup claim window

**Date:** March 2026  
**Decision:** 15-minute window for picker to claim an order before auto-fallback  
**Status:** Under review

**Alternatives considered:**
- 5 min — Too tight; pickers may be mid-errand when notification arrives
- 10 min — Possible; adds risk of order going cold at restaurant
- 15 min — Balances picker availability with food quality window
- 30 min — Too long; customers frustrated by uncertainty

**Rationale:** Restaurant prep time averages 8–12 min. A 15-min claim window means orders typically go out fresh even on fallback. Picker latency data from comparable platforms (DoorDash Drive) suggests 15 min captures ~70% of willing nearby pickers.

**Reversible if:** Fallback rate >30% of community orders (window is too short) OR avg food quality rating for community tier drops below courier tier (food going cold).

---

## Decision #3 — Single zip code launch (not city-wide)

**Date:** February 2026  
**Decision:** Launch in one pilot zip code only  
**Status:** Active

**Alternatives considered:**
- City-wide launch — More data faster, but community density too low to prove model
- 3–5 zip codes — Spreads resources, hard to optimize simultaneously
- 1 zip code — Allows density to build, learn fast, replicate

**Rationale:** Community pickup only works above a density threshold. A city-wide launch at low density would prove the model doesn't work — when the real question is whether we can reach critical density. One zip code, done right, is the correct test.

**Reversible if:** Pilot zip reaches 25% community fulfillment rate and picker supply is stable — then expand to adjacent zips.

---

## Decision #4 — Tamper-evident packaging as restaurant requirement

**Date:** February 2026  
**Decision:** Tamper-evident packaging mandatory for all community pickup orders  
**Status:** Active

**Alternatives considered:**
- Optional packaging (restaurant choice) — Too risky; one incident poisons trust
- Platform-supplied packaging only — Logistically complex; supply chain dependency
- Seal sticker provided by CommuniEats + restaurant confirms in-app — Current approach

**Rationale:** A single tampered-food incident is a platform-ending story. The cost of a tamper-evident sticker is ~$0.02. This is the highest-ROI trust investment available.

**Note:** Should have involved restaurant partners earlier in packaging design. Two revision cycles required after initial restaurants flagged workflow friction.

---

## Decision #5 — Picker rating minimum 4.2/5.0 for eligibility

**Date:** April 2026  
**Decision:** Pickers below 4.2 average rating are ineligible for new orders  
**Status:** Active

**Alternatives considered:**
- No minimum — Race to bottom on service quality
- 4.0 minimum — Too permissive; 4.0 on our binary-ish system signals real issues
- 4.5 minimum — Too restrictive early on; reduces supply before trust data exists
- 4.2 minimum — Allows new pickers to build history, removes consistent low performers

**Rationale:** Supply is the scarce resource at launch. A 4.5 minimum would eliminate too many borderline pickers who might improve. 4.2 gives 3–4 bad trips before removal, which feels fair to pickers and still protects customers.

**Reversible if:** 30+ picker reviews available (sufficient data to tighten) OR community complaint rate rises above 5%.