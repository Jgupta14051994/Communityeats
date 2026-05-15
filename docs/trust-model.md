# CommuniEats — Trust & Safety Design

**The core challenge:** P2P delivery requires customers to trust a stranger with their food. Trust must be designed, not assumed.

---

## Trust Risk Matrix

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Order tampering | Low | Critical | Tamper-evident packaging, restaurant verification step |
| Community picker no-show | Medium | High | 15-min claim window, automatic courier fallback |
| Late delivery | Medium | Medium | Picker ETA shown in real-time, fallback at 15 min past estimate |
| Identity fraud (fake picker) | Low | Critical | Verified profile required (phone + ID check) before first pickup |
| Picker eats/damages food | Very Low | Critical | Rating system, community ban on first verified incident |

---

## Trust Signals (Customer-Facing)

Before a customer accepts a community pickup, they see:
1. **Picker rating** (min 4.2/5.0 to be eligible)
2. **Completed trips** (shown as "47 community pickups")
3. **Estimated arrival time** (updated every 2 min via location)
4. **Fallback guarantee** — "If your picker doesn't arrive, we switch to a courier automatically. No action needed."

Design principle: **Eliminate the moment of doubt.** The fallback guarantee means customers never have to decide "should I wait or re-order."

---

## Trust Signals (Picker-Facing)

Pickers need to trust the system is fair:
1. Clear earnings displayed before accepting
2. Transparent rating criteria (what loses you points)
3. Appeal process for disputed ratings
4. "Trip shield" — no penalty if restaurant order wasn't ready

---

## Packaging Requirements

**Requirement for restaurant partners:**
- All community pickup orders must use sealed packaging (bag + tamper sticker)
- Restaurant must confirm seal in app before releasing to picker
- CommuniEats provides starter pack of tamper-evident stickers at onboarding

**Why this matters:** A tampered order is a platform-ending incident. The cost of the sticker is trivial. The cost of a trust breach is not.

---

## Rating System Design

### Customer rates picker:
- Was food intact? (Yes / No — binary, not scale)
- Was delivery on time? (Yes / Somewhat / No)
- Would you accept a pickup from this person again? (Yes / No)

### When ratings affect eligibility:
- Below 4.0 after 10+ trips: suspended pending review
- Three "food not intact" reports: immediate suspension
- Verified tampering incident: permanent ban

### Why simple ratings:
Uber's 5-star system creates grade inflation — 4.5 feels like failure. Binary + specific questions give more actionable signal.

---

## Fallback Logic

```
Order placed (Community Pickup selected)
  └─ Broadcast to eligible nearby pickers
       ├─ Claimed within 15 min → proceed normally
       └─ Not claimed in 15 min
            ├─ Notify customer ("Switching to courier delivery")
            └─ Auto-assign nearest available courier
                 └─ Customer charged community pickup price (not courier price)
                      ← Platform absorbs price difference
```

**Decision:** Customer always pays community pickup price even on fallback. Rationale: We promised the discount. Reliability is more valuable than the margin recapture.

---

## Open Trust Questions

- [ ] Should we show picker's first name + photo, or keep them anonymous until order claimed?
- [ ] At what complaint rate do we trigger a manual review vs. automated suspension?
- [ ] How do we handle the "picker knows customer" edge case in small communities?