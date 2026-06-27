# priyasingh_2511034_part2_kpi_experiment

# MBA Business Analytics Assignment – Part 2
## KPI Framework, Business Experiment Analysis & Decision Recommendation

---

# Project Overview

This repository presents a complete business analytics solution for evaluating a new onboarding campaign conducted as an A/B experiment for a subscription-based digital product company.

The objective is to determine whether the new onboarding experience should be launched to all users based on business KPIs, statistical evidence, guardrail metrics, and segment-level analysis.

---

# Business Problem Statement

A subscription-based digital product company introduced a new onboarding experience to improve user activation and paid conversion.

Users were randomly divided into:

- Control Group – Existing onboarding experience
- Treatment Group – New onboarding campaign

The key business decision is whether the treatment should replace the existing onboarding experience for all users.

The decision impacts product, marketing, customer success, and business leadership.

The experiment aims to improve the primary business success metric while ensuring customer experience is not negatively affected.

Evidence required before launch includes:

- Statistical improvement in paid conversion
- Positive movement across the conversion funnel
- No major deterioration in guardrail metrics
- Consistent performance across customer segments

---

# Dataset Description

Dataset File:

`data/campaign_experiment_data.xlsx`

Dataset contains:

- 1,408 users
- 16 business variables

Main fields include:

- User ID
- Signup Date
- Experiment Group
- Region
- Device Type
- Traffic Source
- Plan Type
- Landing Page Visit
- Trial Start
- Onboarding Completion
- Paid Conversion
- Revenue (30 Days)
- Refund Request
- Support Tickets
- Days to Convert
- Engagement Score

---

# Repository Structure

```
priyasingh_2511034_part2_kpi_experiment/

├── data/
│   └── campaign_experiment_data.xlsx

├── analysis/
│   ├── experiment_analysis.xlsx
│   └── hypothesis_test_notes.md

├── outputs/
│   ├── experiment_summary.xlsx
│   ├── kpi_tree.png
│   └── recommendation_memo.md

├── screenshots/
│   ├── summary_metrics.png
│   ├── hypothesis_test_output.png
│   └── kpi_tree_preview.png

└── README.md
```

---

# North Star Metric

**30-Day Paid Conversion Rate**

This metric was selected because it:

- Directly measures business growth
- Represents successful customer activation
- Reflects onboarding effectiveness
- Drives subscription revenue
- Aligns marketing, product, and leadership objectives

Supporting metrics include:

- Landing Page Visit Rate
- Trial Start Rate
- Onboarding Completion Rate
- Engagement Score
- Revenue per User
- Days to Convert

Optimizing only conversion without monitoring customer quality may increase refunds or support requests, therefore guardrail metrics are also monitored.

---

# KPI Tree Summary

North Star Metric:

**30-Day Paid Conversion Rate**

Primary KPI Drivers:

### 1. User Acquisition & Activation

- Landing Page Visit Rate
- Trial Start Rate

Sub-drivers

- Campaign CTR
- Acquisition Cost
- Trial Activation Time

---

### 2. Engagement & Onboarding

- Onboarding Completion Rate
- Average Engagement Score

Sub-drivers

- Feature Adoption
- Session Frequency
- Step Completion Rate

---

### 3. Monetisation & Retention

- Average Revenue per Converted User
- Days to Convert

Sub-drivers

- Plan Upgrade Rate
- Revenue Quality
- Price Sensitivity

---

Guardrail Metrics

- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Segment-Level Conversion Parity

---

# Data Cleaning & Preparation

The experiment dataset was validated before analysis.

Checks performed:

- Missing values
- Duplicate User IDs
- Binary field validation
- Revenue outlier detection
- Segment distribution
- Date validation
- Group count validation

Handling:

- Missing categorical values replaced with "Unknown"
- Missing engagement scores filled using group median
- Missing conversion days retained where users never converted
- Revenue outliers flagged but retained
- Duplicate IDs reviewed
- Binary variables validated successfully

No major data quality issues affected the analysis.

---

# Experiment Analysis Approach

The experiment compared Control and Treatment groups using:

- Conversion Funnel Metrics
- Revenue Metrics
- Customer Experience Metrics
- Guardrail Metrics
- Segment Analysis

Summary metrics included:

- User Count
- Landing Page Visit Rate
- Trial Start Rate
- Onboarding Completion Rate
- Paid Conversion Rate
- Average Revenue Per User
- Average Revenue Per Converted User
- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Average Days to Convert

Additional analysis was performed across:

- Region
- Device Type
- Plan Type

---

# Hypothesis Test Summary

Primary Metric Tested

30-Day Paid Conversion Rate

Null Hypothesis

Treatment conversion rate is less than or equal to Control conversion rate.

Alternative Hypothesis

Treatment conversion rate is greater than Control conversion rate.

Test Used

One-tailed Z-Test for Two Proportions

Significance Level

α = 0.05

Results

- Z Statistic = 3.252
- P Value = 0.000573
- Confidence Level = 99.94%

Decision

Reject the Null Hypothesis.

The Treatment onboarding campaign significantly improves paid conversion.

---

# Segment-Level Insights

The experiment was also evaluated across key customer segments.

Key findings include:

- Mobile users showed stronger conversion improvement than desktop users.
- Free plan users experienced the largest uplift after the new onboarding flow.
- All geographic regions recorded positive conversion improvement.
- No major segment experienced a decline in performance.

These findings suggest the treatment performs consistently across different user groups while maintaining positive business impact.

---

# Guardrail Metrics Considered

The recommendation was not based only on conversion improvement.

Guardrails evaluated included:

- Refund Rate
- Support Ticket Rate
- Average Engagement Score
- Revenue Quality
- Days to Convert
- Segment Performance

Results

- Refund Rate remained below acceptable threshold.
- Support Tickets increased and should continue to be monitored.
- Engagement improved significantly.
- Conversion became faster.
- Revenue remained stable.

---

# Final Recommendation

**Recommendation: LAUNCH**

The Treatment campaign demonstrated a statistically significant improvement in the North Star Metric.

Key findings:

- Higher Paid Conversion Rate
- Higher Engagement
- Faster Conversion
- Better Funnel Performance
- Positive Segment Performance

Launch Conditions

- Monitor support ticket volume
- Continue tracking refund rate
- Review 90-day customer retention
- Monitor long-term customer lifetime value

---

# Assumptions

- Random assignment between Control and Treatment
- Independent user behaviour
- 30-day revenue adequately represents short-term business value
- Median imputation does not materially change experiment conclusions

---

# Limitations

- Limited long-term retention information
- Small number of converted users for revenue analysis
- No 90-day LTV available
- Experiment duration not provided

---

# Screenshots Included

- summary_metrics.png
- hypothesis_test_output.png
- kpi_tree_preview.png

---

# Deliverables

Analysis

- experiment_analysis.xlsx
- hypothesis_test_notes.md

Outputs

- experiment_summary.xlsx
- recommendation_memo.md
- kpi_tree.png

Screenshots

- summary_metrics.png
- hypothesis_test_output.png
- kpi_tree_preview.png

Dataset

- campaign_experiment_data.xlsx

---

# Final Conclusion

The new onboarding campaign achieved a statistically significant improvement in paid conversion while improving user engagement and reducing conversion time.

Although support ticket rates increased slightly, refund rates remained within acceptable limits and all customer segments showed positive performance.

Based on the overall business evidence, statistical testing, and guardrail evaluation, the recommendation is to launch the new onboarding experience while continuing to monitor customer support and long-term customer behaviour.

---

**Submitted By**

**Priya Singh**

**Student ID:** 2511034

MBA Business Analytics Assignment – Part 2
