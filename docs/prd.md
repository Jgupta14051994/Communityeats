# CommuniEats — Product Requirements Document

**Version:** 1.2 · **Status:** In Development · **Owner:** Jyoti Gupta

---

## Problem Statement

Last-mile delivery costs are structurally high because every order generates a dedicated trip. Customers pay 25–35% in fees; platforms subsidize couriers to maintain supply. Neither side wins long-term.

**Opportunity:** Neighbors already make trips to restaurants. The logistics network exists — it's just uncoordinated.

---

## Goals

| Goal | Metric | Target |
|---|---|---|
| Reduce delivery cost for customers | Avg fee per order | <$3 for community tier |
| Achieve community fulfillment at scale | % orders via community pickup | >25% within 90 days per zip |
| Build trust in P2P delivery | Community pickup complaint rate | <5% |
| Grow community picker supply | Active pickers per zip | >50 within 60 days |

---

## User Personas

### Persona 1: Budget-Conscious Foodie ("Maya")
- Orders 3–4x/month, fee-sensitive
- Will plan ahead to save money
- **Jobs-to-be-done:** Get food I want without paying courier markup
- **Key friction:** Uncertainty about reliability of community pickup

### Persona 2: Community Picker ("Alex")
- Already goes to restaurants regularly
- Motivated by small income supplement + "helping neighbors" narrative
- **Jobs-to-be-done:** Make my existing trip pay for itself
- **Key friction:** Doesn't want to commit if it adds significant time

### Persona 3: Restaurant Owner ("Carlos")
- Wants more orders, lower commission dependency
- **Jobs-to-be-done:** Grow revenue without paying 30% to aggregators
- **Key friction:** Operational complexity of managing multiple pickup types

---

## Features

### P0 — Launch Blockers

| Feature | Description | Rationale |
|---|---|---|
| Three-tier order selection | Customer chooses delivery type at checkout | Core product mechanic |
| Community picker matching | Match open community orders to nearby pickers | Primary value delivery |
| Fallback to courier | Auto-fallback if community pickup not claimed in 15 min | Trust & reliability |
| Tamper-evident packaging flow | Restaurant confirms sealed packaging before release | Trust foundation |
| Basic picker profile + rating | Rating visible to customers before accepting community order | Trust signal |

### P1 — Post-Launch (Next 60 days)

| Feature | Description |
|---|---|
| Picker earnings dashboard | Show cumulative earnings, trips, community impact |
| Order history & preferences | Remember preferred tier per restaurant |
| Push notifications | Real-time status for community pickup progress |
| Restaurant onboarding flow | Self-serve packaging setup + order type configuration |

### P2 — Future

- Dynamic discount based on real-time community availability
- Route optimization for pickers with multiple stops
- Community impact dashboard (CO₂ saved, trips reduced)

---

## Out of Scope (v1)

- Multi-city launch (single zip code only)
- Corporate/catering orders
- Subscription model
- In-app chat between picker and customer

---

## Success Criteria (90-day post-launch)

1. Community fulfillment rate >25% of eligible orders in pilot zip code
2. Community pickup complaint/issue rate <5%
3. 50+ active pickers with >2 completed trips
4. Customer repeat order rate (community tier) >40%

---

## Open Questions

- [ ] What's the right SLA for community pickup claim window? (Currently 15 min — may need testing)
- [ ] Should restaurant rating factor into community picker eligibility?
- [ ] How do we handle tip for community pickers vs. couriers?