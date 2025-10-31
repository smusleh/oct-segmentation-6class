# OCT Segmentation (6-Class) — Segmentation Only

This repository is a **clean, GitHub-ready** package for **retinal OCT 6-class segmentation**.  
It includes a ready folder structure, environment requirements, and your uploaded segmentation notebook.

## Repository Structure

```
oct-segmentation-6class/
├── notebooks/
│   └── OCT_Segmentation_6Class_Pipeline.ipynb    # your segmentation pipeline
├── src/                                          # reusable modules (optional)
├── configs/
│   └── config.yaml                               # class IDs & paths (no thickness entries)
├── data/
│   ├── images/                                   # place OCT images here
│   └── masks_6class/                             # place 6-class masks here (match filenames)
├── outputs/
│   └── visualizations/                           # segmentation overlays / figures
├── .github/workflows/
│   └── lint.yml                                  # optional CI
├── .gitignore
├── LICENSE
├── requirements.txt
└── README.md
```

### Mask Class IDs
- `0`: background
- `1`: ILM
- `2`: OPL
- `3`: IS-OS
- `4`: IBRPE
- `5`: OBRPE

> **Note**: This package is **segmentation-only**. There are **no thickness measurements** or references to thickness in code or configs.

## Quick Start

1. Clone and enter:
```bash
git clone <your-repo-url>.git
cd oct-segmentation-6class
```

2. Create a venv and install:
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

3. Add your data:
```
data/
├── images/
│   ├── sample_001.png
│   └── ...
└── masks_6class/
    ├── sample_001.png
    └── ...
```

4. Run the notebook:
```bash
jupyter notebook notebooks/OCT_Segmentation_6Class_Pipeline.ipynb
```

## Tips
- Keep image and mask filenames identical; ensure same spatial size.
- Masks should be **single-channel** integer labels `[0..5]`.
- Adjust class IDs or paths in `configs/config.yaml` if your dataset differs.
