# CommuniEats — Feature Prioritization (RICE Scoring)

**Framework:** RICE = (Reach × Impact × Confidence) / Effort  
**Scoring period:** Q2 2026 · **Owner:** Jyoti Gupta

---

## Scoring Key

| Dimension | Scale |
|---|---|
| **Reach** | Estimated users affected per quarter |
| **Impact** | 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal |
| **Confidence** | % confidence in reach/impact estimates |
| **Effort** | Person-weeks to design, build, and ship |

---

## Feature Scores

| Feature | Reach | Impact | Confidence | Effort | RICE Score | Priority |
|---|---|---|---|---|---|---|
| Three-tier order selection | 500 | 3 | 90% | 3 | **450** | P0 |
| Community picker matching | 500 | 3 | 80% | 5 | **240** | P0 |
| Automatic courier fallback | 500 | 3 | 85% | 3 | **425** | P0 |
| Tamper-evident packaging flow | 500 | 3 | 95% | 1 | **1,425** | P0 |
| Basic picker rating | 400 | 2 | 80% | 2 | **320** | P0 |
| Push notifications (order status) | 450 | 2 | 75% | 2 | **338** | P1 |
| Picker earnings dashboard | 200 | 2 | 70% | 3 | **93** | P1 |
| Order history & preferences | 300 | 1 | 80% | 2 | **120** | P1 |
| Restaurant self-serve onboarding | 50 | 3 | 60% | 4 | **23** | P1 |
| Dynamic discount (supply-based) | 500 | 2 | 50% | 6 | **83** | P2 |
| Multi-stop route optimization | 100 | 2 | 40% | 8 | **10** | P2 |
| CO₂ impact dashboard | 300 | 0.5 | 70% | 2 | **53** | P2 |
| In-app picker/customer chat | 200 | 1 | 60% | 4 | **30** | P2 |

---

## Key Prioritization Decisions

### Why tamper-evident packaging scores highest

RICE is a useful first filter, but the model doesn't capture catastrophic risk. Packaging has a high RICE score AND is an asymmetric bet: failure cost is existential (one food safety incident), success cost is $0.02/order. It's P0 regardless of the score.

### Why restaurant self-serve onboarding is deprioritized despite high impact

Impact is high *if* we have many restaurants. At pilot scale (one zip code), we have 5–10 partner restaurants we can onboard manually. Building self-serve now is premature optimization. Revisit at 50+ restaurants.

### Why dynamic discounts are P2

We don't have supply data yet. Dynamic pricing requires a model trained on picker availability patterns. Building the model before having the data is the wrong order of operations.

---

## What RICE Doesn't Capture

- **Existential risks** — handled above with packaging
- **Dependencies** — picker matching depends on picker profiles existing
- **Sequencing constraints** — trust features must ship before growth features
- **Learning value** — some low-RICE features teach us things no metric captures

Final priority call always involves judgment. RICE is an input, not an answer.