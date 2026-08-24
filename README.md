# PRISM — Pricing & Revenue Intelligence for Streaming Markets

> Marketing Mix Model + Pricing Science framework
> applied to a video streaming subscription platform.

## What this repository contains

**MMM (Marketing Mix Model)**
- Hill Saturation OLS regression with HAC/Newey-West SE
- 7 media channels decomposed: Affiliate, Meta, Google,
  YouTube, Email, Call Center, E-commerce
- Out-of-sample validation: R² = 0.9742, MAPE = 1.14%
- Seasonality isolation (Brazilian Championship peak: +42%)
- Adstock decay by channel (δ = 0.05 to 0.60)

**PRISM v2 (Pricing Science)**
- OLS log-log price elasticity estimated per package
- 95% CI propagated end-to-end (pessimistic/central/optimistic)
- 6×6 cross-elasticity cannibalization matrix
- Van Westendorp WTP analysis by segment
- Seasonal timing optimizer (12-month ranking)
- Bundle design & revenue simulation

## Business context
Video streaming subscription platform with 6 content packages
(Football, MMA, Family, Series/Films, Kids, Bundle).

## Technical stack
Python (numpy, scipy, pandas) · Excel (OLS engine +
539 linked formulas across 10 sheets) · Statistical methods:
OLS, HAC SE, Hill Saturation, Van Westendorp

## Key results
| Metric | Value |
|---|---|
| MMM R² holdout | 0.9742 |
| MMM MAPE | 1.14% |
| Elasticity range | −0.36 (Football) to −1.35 (Series) |
| Pricing uplift potential | +12–18% revenue |
| Optimal reajuste timing | November (seasonality index 1.35) |

## Author
Bruno Pamplona Corte-Real
Lead Business Insights & Analytics
linkedin.com/in/bruno-pamplona
