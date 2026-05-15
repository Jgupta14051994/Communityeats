# CommuniEats: Product Case Study

**Community-powered last-mile delivery — rethinking who makes the trip.**

Live: [communieats-app.vercel.app](https://communieats-app.vercel.app) · Built with Next.js + TypeScript

---

## The Problem

A $42 meal costs $56 after fees — a 33% markup for a single dedicated courier trip.

The root issue isn't the fee. It's the model: **every order creates its own trip**, even when a neighbor is already headed to that restaurant. Platforms optimize courier routing but ignore the most efficient logistics network that already exists — people's natural travel patterns.

**Prior art:** JoyRun (2017) raised $10M on the same insight, acquired by Walmart in 2020. Still not mainstream. Why? The trust and density problems were never solved.

---

## The Solution: Three-Tier Fulfillment

| Tier | Mechanism | Customer Discount | Core Tradeoff |
|---|---|---|---|
| Traditional Delivery | Dedicated courier | 0% | Convenience over cost |
| Self-Pickup | Customer collects order | 10% | Time for savings |
| Community Pickup | Neighbor picks up en route | 30% | Trust for significant savings |

Community Pickup is the core innovation — and the hardest problem.

---

## Key Product Decisions

### 1. Why 30% for Community Pickup?

**The question:** What discount makes the trust trade-off worth it for customers?

**Options considered:**
- 15%: Too low — not enough to change behavior
- 20%: Marginal — some uptake, weak habit formation
- 30%: Creates genuine "wow" moment on first use, drives word-of-mouth

**Decision:** 30% discount, reviewed after 500 community transactions. Discount level is a lever, not a constant.

**What would prove this wrong:** If >40% of community pickups result in complaints or refund requests, trust cost exceeds discount value.

---

### 2. The Trust Problem

P2P delivery fails when trust fails. Three trust risks identified:

| Risk | Mitigation |
|---|---|
| Order tampering | Sealed, tamper-evident packaging required at restaurant |
| No-show / late delivery | 15-min grace window, then automatic fallback to courier |
| Identity fraud | Verified community member profile (rating + history gated) |

**Design principle:** Remove trust decisions from the user. The system handles fallback — customers should never feel "exposed" if a community pickup fails.

---

### 3. The Density Problem

Community pickup only works when supply (neighbors traveling that route) meets demand (orders going that direction). This is a cold-start problem.

**Approach:** Launch hyper-locally — one zip code at a time. Reach critical density before expanding. Measure: community fulfillment rate per zip code. Target: >25% of eligible orders fulfilled by community within 90 days of launch.

---

## What I'd Do Differently

1. **Build the rating system earlier.** Community picker ratings were deprioritized for launch. They're actually a trust-building flywheel — should have been Day 1.
2. **Instrument fallback events from the start.** Knowing *why* community pickups fall back (late, no-show, opted out) is the most important signal for improving reliability.
3. **Talk to restaurants sooner.** Packaging requirements were designed without restaurant input. Two rounds of revision could have been one.

---

## Frameworks Used

- [RICE Prioritization](../product-management-toolkit) — Feature sequencing
- [Opportunity Scoring](../product-management-toolkit) — Evaluating fulfillment model variants
- [Decision Log Template](../product-management-toolkit) — Documenting all major product choices
- [User Interview Guide](../product-management-toolkit) — Customer discovery (n=14 before spec)

---

## Repo Structure

```
Communityeats/
├── README.md              ← This file (product case study)
└── docs/
    ├── prd.md             ← Full product requirements document
    ├── trust-model.md     ← Trust & safety design decisions
    ├── prioritization.md  ← RICE scoring for all features
    └── decision-log.md    ← Chronological decision history
```

---

*Questions or feedback? Open an issue — I use them to work through product thinking publicly.*