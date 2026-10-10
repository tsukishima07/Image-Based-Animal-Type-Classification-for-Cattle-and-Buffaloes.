# ATC Dataset Structure

Place your images here following this layout:

```
dataset/
├── train/
│   ├── cow/        ← training cow images (*.jpg, *.png)
│   └── buffalo/    ← training buffalo images
├── val/
│   ├── cow/        ← validation cow images
│   └── buffalo/    ← validation buffalo images
└── test/           ← test images (unlabelled)
```

## Quick Start

### Option A: Use your own images
```bash
cd ml/scripts
python prepare_dataset.py --src /path/to/raw_images --dst ../dataset --val_split 0.2
```
Raw images should be in: `/path/to/raw_images/cow/` and `/path/to/raw_images/buffalo/`

### Option B: Generate synthetic dummy images (for testing)
```bash
cd ml/scripts
python prepare_dataset.py --generate_dummy --dst ../dataset --count 100
```

### Validate dataset
```bash
python prepare_dataset.py --validate --dst ../dataset
```

## Recommended Dataset Sources
- ICAR bovine image databases
- NDDB/NABARD livestock image archives
- OpenImages (filtered for cattle)
- Custom field photos (side-profile, good lighting)

## Image Guidelines for Best Results
- **Angle**: Pure side-profile (90° lateral view)
- **Distance**: Full body visible with ~10% margin
- **Background**: Plain or contrasting
- **Resolution**: ≥ 640×480 px
- **Format**: JPG or PNG
