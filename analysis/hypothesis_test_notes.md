# Hypothesis Test Notes
## New Onboarding Campaign A/B Experiment

---

## Primary Test: 30-Day Paid Conversion Rate

### 1. Null Hypothesis (H₀)
> The 30-day paid conversion rate of the Treatment group is **less than or equal to** that of the Control group.
>
> H₀: p_Treatment ≤ p_Control

### 2. Alternate Hypothesis (H₁)
> The 30-day paid conversion rate of the Treatment group is **greater than** that of the Control group.
>
> H₁: p_Treatment > p_Control

### 3. Test Type
**One-tailed Z-test for two independent proportions**

Rationale: We are testing directional superiority — whether the new onboarding campaign *improves* conversion. A one-tailed test is appropriate because launching the campaign only makes business sense if it performs *better*, not merely *different*, from Control.

### 4. Significance Level
**α = 0.05** (95% confidence threshold; standard for product experiments)

### 5. Inputs

| Parameter | Value |
|---|---|
| Control sample size (n₁) | 693 |
| Treatment sample size (n₂) | 715 |
| Control conversions | 22 |
| Treatment conversions | 50 |
| Control conversion rate (p̂₁) | 3.17% |
| Treatment conversion rate (p̂₂) | 6.99% |
| Pooled proportion (p̂) | 5.11% |

### 6. Test Statistic

**Formula:**
```
Z = (p̂₂ - p̂₁) / sqrt(p̂(1-p̂)(1/n₁ + 1/n₂))
```

**Calculation:**
```
p̂ = (22 + 50) / (693 + 715) = 72/1408 = 0.05114
SE = sqrt(0.05114 × 0.94886 × (1/693 + 1/715)) = 0.01175
Z = (0.0699 - 0.0317) / 0.01175 = 3.252
```

**Z-Statistic = 3.252**

### 7. P-Value
**P-value = 0.000573** (one-tailed)

### 8. Critical Value
At α = 0.05 (one-tailed): **Z_critical = 1.645**

### 9. Decision Rule
- If Z > 1.645 AND p-value < 0.05 → **Reject H₀**
- If Z ≤ 1.645 OR p-value ≥ 0.05 → **Fail to Reject H₀**

**Result: Z = 3.252 > 1.645 and p = 0.000573 < 0.05**
→ **REJECT the null hypothesis**

### 10. Business Interpretation
At a 95% confidence level (actually 99.94% confidence), the evidence strongly supports that the new onboarding campaign produces a statistically significant improvement in 30-day paid conversion rate. The Treatment group converted at **6.99%** versus **3.17%** in Control — an absolute lift of **+3.82 percentage points** and a relative uplift of **+120.5%**.

This result is unlikely to be due to random chance (p = 0.000573).

---

## Secondary Tests

### Test 2: Average Engagement Score (Two-tailed t-test)

| Parameter | Value |
|---|---|
| H₀ | Mean engagement is equal across groups |
| H₁ | Mean engagement differs between groups |
| Test | Independent samples Welch's t-test (two-tailed) |
| Control Mean | 57.03 |
| Treatment Mean | 62.93 |
| t-statistic | 7.944 |
| p-value | < 0.0001 |
| Decision | **Reject H₀** — Treatment significantly more engaged |

### Test 3: Support Ticket Rate (Two-tailed t-test) — GUARDRAIL

| Parameter | Value |
|---|---|
| H₀ | Support ticket rate is equal across groups |
| H₁ | Support ticket rate differs between groups |
| Test | Independent samples Welch's t-test (two-tailed) |
| Control Mean | 0.219 tickets/user |
| Treatment Mean | 0.372 tickets/user |
| t-statistic | 4.214 |
| p-value | < 0.0001 |
| Decision | **Reject H₀** — Treatment has significantly higher support burden |
| Risk Flag | ⚠ GUARDRAIL BREACHED — requires investigation before full launch |

### Test 4: Revenue Per Converted User (Two-tailed t-test)

| Parameter | Value |
|---|---|
| H₀ | Revenue per converter is equal across groups |
| H₁ | Revenue per converter differs |
| Test | Independent samples t-test (two-tailed, small sample caveat) |
| Control Mean | $1,630 |
| Treatment Mean | $770 |
| t-statistic | -1.840 |
| p-value | 0.0791 |
| Decision | **Fail to reject H₀** — Difference not statistically significant at α=0.05 |
| Note | Small sample (n=72 converters) reduces power; monitor in larger rollout |

### Test 5: Days to Convert (One-tailed t-test)

| Parameter | Value |
|---|---|
| H₀ | Days to convert ≥ Control |
| H₁ | Treatment converts faster (fewer days) |
| Test | One-tailed t-test |
| Control Mean | 8.86 days |
| Treatment Mean | 6.40 days |
| t-statistic | -2.814 |
| p-value | 0.0033 |
| Decision | **Reject H₀** — Treatment converts significantly faster |

---

## Summary Table

| Test | Metric | p-value | Decision | Business Status |
|---|---|---|---|---|
| Z-test (proportions) | Paid Conversion Rate | 0.000573 | Reject H₀ | ✅ Significant Win |
| t-test | Engagement Score | <0.0001 | Reject H₀ | ✅ Significant Win |
| t-test | Support Ticket Rate | <0.0001 | Reject H₀ | ⚠ Guardrail Breach |
| t-test | Revenue Per Converter | 0.0791 | Fail to Reject | ℹ Inconclusive |
| t-test | Days to Convert | 0.0033 | Reject H₀ | ✅ Significant Win |

---

## Assumptions & Limitations

1. **Independence**: Users are assumed to be independently assigned. No network effects modelled.
2. **SUTVA**: Stable Unit Treatment Value Assumption — Treatment does not affect Control group behavior.
3. **Sample size**: Converter subgroup (n=72) is small; revenue tests have reduced statistical power.
4. **Experiment duration**: Experiment duration not explicitly provided; results may be subject to novelty effects.
5. **Multiple testing**: Running 5 tests inflates family-wise error rate. Bonferroni correction at α=0.01 would still confirm the primary conversion result (p=0.000573 < 0.01).
