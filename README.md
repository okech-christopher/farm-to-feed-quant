---
title: Agri-Demand Optimizer
emoji: 🚜
colorFrom: green
colorTo: yellow
sdk: docker
pinned: false
---

# Agri-Demand Optimizer: Predictive Supply Chain Intelligence

**High-Precision Analytics | 0.916 Private AUC | Agricultural Demand Forecasting**

## Overview: Fresh Produce Supply Chain Optimization
The Agri-Demand Optimizer is a systematic analytics platform designed for **Farm to Feed**, a Kenyan social enterprise focused on reducing post-harvest loss. By providing accurate demand projections for smallholder produce, the system enables the efficient diversion of surplus and underutilized crops to commercial kitchens, stabilizing farmer incomes and strengthening local food systems.

### Core Objectives:
1. **Demand Estimation:** 7-day and 14-day purchase likelihood classification.
2. **Volume Optimization:** High-precision regression of unit requirements per SKU to minimize waste.

## Performance Benchmarks
The system utilizes a High-Precision Ensemble (V11) to ensure stability across varied market regimes:

| Metric | Public Benchmark | Private Benchmark |
| :--- | :--- | :--- |
| **Purchase AUC** | 0.906 | **0.916** |
| **Weighted Accuracy** | ~0.76 | **0.78 (Analytical Grade)** |

## Technical Methodology

### 1. Delta-Modeling Architecture
To mitigate temporal drift and scale-variance, the system employs a Delta-Modeling approach. By predicting the demand variance (Delta) between sequential weeks rather than absolute values, the model achieved a **82% reduction in prediction error** during cross-validation.

### 2. Multi-Threshold Risk Mitigation
The system incorporates a triple-threshold probabilistic mask [0.3, 0.4, 0.5] to protect stakeholders from over-stocking perishables. Quantities are only allocated when the purchase signal demonstrates high statistical confidence, while low-confidence anomalies are automatically suppressed.

### 3. Supply Chain Feature Engineering
- **Velocity Metrics:** `qty_lag_1w` and multi-period rolling frequencies (4w, 8w, 12w).
- **Inventory Anchors:** Category-level baseline statistics and SKU-specific historical volumetrics.

## Project Structure
- `app.py`: Project backend and analytical service.
- `index.html`: Professional analytics dashboard.
- `pipeline/`: End-to-end training and calibration scripts.
- `models_v11_voting/`: Serialized High-Precision Ensemble weights (LFS).

## Deployment
Operational status on Hugging Face Spaces:
- [Analytical Console](https://huggingface.co/spaces/okechobonyo/farm-to-feed-elite)

---
**System Engineering:** Christopher Okech | Nairobi, Kenya
