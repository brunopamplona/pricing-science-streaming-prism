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

## files
prism-streaming-analytics/
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   │   ├── subscriptions_historical.csv
│   │   ├── media_spend_by_channel.csv
│   │   └── van_westendorp_survey_raw.csv
│   └── processed/
│       ├── mmm_adstocked_data.csv
│       └── elasticity_panel_data.csv
│
├── models/
│   ├── mmm/
│   │   ├── __init__.py
│   │   ├── adstock.py              # Modelagem de adstock decay (δ = 0.05 a 0.60)
│   │   ├── hill_saturation.py     # Curvas de saturação de Hill
│   │   ├── ols_hac.py              # Regressão OLS com erro padrão robusto (HAC / Newey-West)
│   │   └── evaluate.py             # Validação fora da amostra (R² = 0.9742, MAPE = 1.14%)
│   │
│   └── pricing_v2/
│       ├── __init__.py
│       ├── log_log_elasticity.py   # Regressão log-log de elasticidade-preço por pacote
│       ├── confidence_intervals.py # Propagação de IC 95% (cenários pessimista, central e otimista)
│       ├── cannibalization.py      # Matriz 6x6 de elasticidade cruzada
│       ├── van_westendorp.py       # Análise de WTP (Willingness-to-Pay) por segmento
│       ├── seasonal_optimizer.py   # Otimizador de timing sazonal (ranking de 12 meses)
│       └── bundle_simulator.py     # Simulação de receitas e design de pacotes
│
├── notebooks/
│   ├── 01_mmm_media_channel_decomposition.ipynb
│   ├── 02_prism_v2_price_elasticity_modelling.ipynb
│   ├── 03_van_westendorp_wtp_analysis.ipynb
│   └── 04_seasonal_timing_revenue_simulation.ipynb
│
├── excel/
│   └── PRISM_v2_Pricing_Model_ClaroTVPlus.xlsx  # Motor OLS em Excel com 539 fórmulas vinculadas nas 10 abas
│
├── presentation/
│   └── PRISM_v2_CMO_EN_final.pptx               # Deck executivo com os insights de pricing para o CMO
│
└── utils/
    ├── __init__.py
    ├── metrics.py
    └── visualization.py            # Plotagem de decomposição de canais e curvas WTP

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
