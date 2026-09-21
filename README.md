# IGNIS Fire-Footprint Forecaster — segmentation-based next-day fire-complex footprint

> Part of the **IGNIS** platform — NASA Space Apps Challenge 2026, challenge #9
> *Harmonization of MODIS and VIIRS Hot Spots*. **Private during judging.**

Cell-wise (0.05 deg) segmentation model predicting tomorrow's fire-complex footprint from prior-days detection-density features (multi-bandwidth Gaussian KDE, FRP-weighted density). Strict forward holdout (train targets 09-17..19, test target 2026-09-20): Amazon IoU 0.657, Congo 0.549, Borneo 0.500 vs persistence baseline 0.355/0.388/0.378 — 1.3-1.9x skill.

## Contents
- `train_footprint_forecaster.py` — full reproducible training pipeline (real NASA FIRMS data)
- model artifacts (scikit-learn joblib bundles) + `metrics.json`
- `LICENSE` — MIT

## Hugging Face
The same model, with the full model card, lives at
**https://huggingface.co/Nabidnur/ignis-fire-footprint-forecaster** (private; request access or see the main repo).

## Main project
https://github.com/Hisernberg/ignis-spaceapps2026 — live app:
https://ignis-spaceapps2026.vercel.app

## Provenance
All training data derives from NASA FIRMS active-fire detections (public domain),
harmonized across MODIS (Terra/Aqua) and VIIRS (S-NPP/NOAA-20/NOAA-21) by the IGNIS
pipeline. No synthetic data is used for supervised labels.
