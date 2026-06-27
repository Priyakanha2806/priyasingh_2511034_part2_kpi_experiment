# Recommendation Memo
## New Onboarding Campaign — Launch Decision

**To:** Product Leadership & Growth Team  
**From:** Senior Business Analyst  
**Date:** June 2026  
**Classification:** Internal — Decision Memo  
**Experiment ID:** OB-CAMP-2026-01

---

## Executive Summary

A controlled A/B experiment (n=1,408 users) was conducted to evaluate whether deploying a new onboarding campaign to all users would improve 30-day paid conversion rates. The Treatment group achieved a **6.99% paid conversion rate** compared to **3.17%** in Control — a statistically significant absolute lift of **+3.82 percentage points** (Z=3.25, p=0.0006, 99.94% confidence).

**Recommendation: Conditional Launch — proceed with full rollout, with mandatory guardrail monitoring and a rapid-response plan for elevated support tickets.**

---

## 1. Business Problem

The company operates a subscription-based digital product and seeks to determine whether a newly designed onboarding campaign should be deployed to all users. The experiment tests whether the campaign can meaningfully accelerate the user journey from signup to paid subscription.

**Key decision:** Should the new onboarding campaign replace the current onboarding experience for all new users?

**Stakeholders impacted:**
- Product & Growth teams (campaign design and iteration)
- Customer Success (support ticket volume implications)
- Finance (revenue and refund rate projections)
- Marketing (channel mix and traffic acquisition)

**Business objective:** Increase 30-day paid conversion rate, driving sustainable subscription revenue growth.

**Success criteria:** Statistically significant improvement in paid conversion rate at α=0.05, with no material deterioration in guardrail metrics (refund rate, support tickets, engagement score).

---

## 2. North Star Metric

**North Star Metric: 30-Day Paid Conversion Rate**

This metric was chosen because it:
- Directly measures the campaign's ability to drive revenue
- Captures the cumulative effect of every improvement in the user funnel (landing visit → trial → onboarding → payment)
- Aligns product, marketing, and customer success around a single shared goal
- Is a leading indicator of long-term subscription revenue and LTV

**Supporting KPIs:** Landing Page Visit Rate, Trial Start Rate, Onboarding Completion Rate, Engagement Score, Days to Convert

**Guardrail metrics:** Refund Rate, Support Ticket Rate, Segment-level conversion parity

---

## 3. KPI Tree Summary

```
North Star: 30-Day Paid Conversion Rate
│
├── USER ACQUISITION & ACTIVATION
│   ├── Landing Page Visit Rate (+9.0pp ✅)
│   ├── Trial Start Rate (+4.0pp ✅)
│   └── Campaign CTR, Channel Mix
│
├── ENGAGEMENT & ONBOARDING
│   ├── Onboarding Completion Rate (+5.7pp ✅)
│   ├── Avg Engagement Score (+5.9 pts ✅)
│   └── Feature Adoption Depth, Session Frequency
│
└── MONETISATION & RETENTION
    ├── Avg Revenue Per Converted User (-$860 ⚠)
    ├── Days to Convert (-2.5 days ✅)
    └── Plan Upgrade Rate, Revenue Quality

GUARDRAILS:
  ├── Refund Rate: 0.42% vs 0.00% (Monitor ⚠)
  ├── Support Ticket Rate: +0.15/user (⚠ Breach)
  ├── Engagement Score: 62.9 vs 57.0 (Pass ✅)
  └── Segment Parity: All regions positive (Pass ✅)
```

---

## 4. Experiment Summary

| Metric | Control (n=693) | Treatment (n=715) | Lift | Significant? |
|---|---|---|---|---|
| Landing Page Visit Rate | 63.6% | 72.6% | +9.0pp | Yes |
| Trial Start Rate | 25.1% | 29.1% | +4.0pp | Yes |
| Onboarding Completion Rate | 15.6% | 21.3% | +5.7pp | Yes |
| **Paid Conversion Rate ★** | **3.17%** | **6.99%** | **+3.82pp** | **Yes ✓** |
| Avg Revenue Per User | $51.75 | $53.88 | +$2.13 | No |
| Avg Revenue Per Converted User | $1,630 | $770 | -$860 | No (low n) |
| Refund Rate | 0.00% | 0.42% | +0.42pp | Monitor |
| Support Ticket Rate | 0.219 | 0.372 | +0.153 | Yes ⚠ |
| Avg Engagement Score | 57.03 | 62.93 | +5.90 | Yes ✓ |
| Avg Days to Convert | 8.86 | 6.40 | -2.46 | Yes ✓ |

---

## 5. Hypothesis Test Result

**Test:** One-tailed Z-test for two independent proportions  
**H₀:** p_Treatment ≤ p_Control  
**H₁:** p_Treatment > p_Control  
**α = 0.05**

| Result | Value |
|---|---|
| Z-Statistic | 3.252 |
| P-Value | 0.000573 |
| Critical Value (Z₀.₀₅) | 1.645 |
| Decision | **REJECT H₀** |
| Confidence Level | 99.94% |

The result is statistically significant and robust. Even under Bonferroni correction for multiple tests (α = 0.01), the conversion result remains significant.

---

## 6. Guardrail Analysis

### Refund Rate
- Control: 0.00% | Treatment: 0.42% (3 refunds out of 715 users)
- Low absolute count but represents a new signal; **monitoring required**
- Action: Track refund rate weekly for 30 days post-launch; escalate if >1%

### Support Ticket Rate
- Control: 0.219/user | Treatment: 0.372/user (+70% increase)
- **Statistically significant (p<0.0001)** — this is a guardrail breach
- Root cause analysis required: likely reflects onboarding confusion, unclear upgrade prompts, or payment friction
- Action: Audit top 3 support ticket categories in Treatment cohort before full launch

### Engagement Score
- Control: 57.03 | Treatment: 62.93 (+10.3% improvement, p<0.0001)
- **Guardrail PASSED** — Treatment users are meaningfully more engaged
- Higher engagement is a strong predictor of long-term retention and renewal

### Revenue Per Converted User
- Control: $1,630 | Treatment: $770 (decline, not statistically significant at p=0.079)
- The campaign may be converting a broader but lower-value user base
- Action: Track 90-day LTV to assess whether this represents a mix shift or genuine value concern

---

## 7. Segment Insights

### By Region
All four regions show positive conversion lift in Treatment:
- **North: +5.4pp** (strongest absolute lift; 8.9% vs 3.4%)
- South: +4.3pp | East: +3.9pp | West: +1.7pp (weakest; monitor)

### By Device
The campaign performs particularly well on mobile:
- **Mobile: +4.8pp** (7.3% vs 2.6%) — campaign reverses the mobile underperformance seen in Control
- Desktop: +2.0pp | Tablet: +5.4pp (small sample caution)

### By Plan Type
Free plan users show the largest conversion uplift:
- **Free plan: +6.2pp** (9.2% vs 3.0%) — highest opportunity segment
- Premium: +3.5pp | Basic: +0.2pp (limited campaign impact on Basic plan users)

### By Traffic Source
Analysis of traffic source segments shows consistent positive trends across channels, with Organic and Referral users showing particularly strong responses.

---

## 8. Business Risks

| Risk | Likelihood | Impact | Mitigation |
|---|---|---|---|
| Support ticket volume overwhelms CS team | Medium | High | Pre-brief CS, set up campaign-specific ticket triage |
| Revenue per converter LTV risk | Medium | Medium | Monitor 90-day LTV; segment by plan type |
| Novelty effect (inflated initial conversion) | Low-Medium | Medium | Re-run experiment at 60-day mark post-launch |
| Mobile edge cases not caught in test | Low | Low | A/B test mobile experience separately |
| Refund rate escalation | Low | Medium | Automated alert if refunds exceed 1% |

---

## 9. Limitations

1. **Small converter sample (n=72):** Revenue tests are underpowered. Revenue conclusions should be treated as directional, not confirmatory.
2. **Experiment duration unknown:** If the experiment ran <4 weeks, novelty effects may inflate early conversion rates.
3. **No long-term LTV data:** Days-to-convert and 30-day revenue are leading indicators only; 90-day retention data is needed to confirm campaign quality.
4. **Missing data:** 18 device_type and 24 traffic_source records were imputed as 'Unknown', which may slightly affect segment-level conclusions.
5. **Group size imbalance:** Treatment (715) slightly exceeds Control (693) — 3.2% imbalance. This is within acceptable range but noted.

---

## 10. Final Recommendation

### Decision: **LAUNCH — with Guardrail Conditions**

The new onboarding campaign has demonstrated a **statistically and practically significant improvement** in the primary business metric (30-day paid conversion rate: +120.5% relative lift, p=0.0006). Every funnel stage improved. Users are more engaged and convert faster.

**However, the elevated support ticket rate is a guardrail breach that must be addressed before or immediately after launch.**

### Recommended Launch Conditions:

1. **Immediate:** Conduct root-cause analysis on support ticket spike (top 3 category audit)
2. **Week 1 post-launch:** Monitor daily refund rate and support ticket rate vs. thresholds
3. **Week 4:** Re-evaluate revenue per converter; if LTV gap persists, investigate plan mix
4. **Month 2:** Run follow-up experiment targeting Basic plan users separately (lowest lift segment)
5. **Month 3:** Full 90-day LTV cohort analysis to confirm long-term campaign viability

### Priority Segments for Accelerated Rollout:
- **Free plan users** (highest lift: +6.2pp)
- **Mobile users** (campaign reverses prior mobile underperformance)
- **North region** (highest absolute conversion rate at 8.9%)

---

*This memo was prepared as part of the MBA Business Analytics Assignment — Part 2.*  
*All values are derived from the campaign_experiment_data.xlsx dataset.*
