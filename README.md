# Medical Image Quality Analysis

Large-scale quality analysis of a 16+ GB medical imaging dataset containing 24,371 NPZ files using Python, NumPy, Pandas, and Matplotlib.

## Dataset Summary

- Total NPZ files: 24,371
- Total archive size: 16+ GB
- Images per file: 24 slices
- Image resolution: 224 × 224
- Data type: uint8
- Successfully processed: 24,371
- Corrupted files detected: 0

## Project Goals

This project performs automated quality inspection of a large medical imaging dataset.

The pipeline:

- validates NPZ files
- checks image dimensions
- checks data types
- calculates pixel statistics
- detects potential intensity outliers
- generates structured CSV reports

## Technologies

- Python
- NumPy
- Pandas
- Matplotlib
- JupyterLab

## Repository Structure

```text
medical-image-quality-analysis/
├── notebooks/
│   └── dataset_analysis.ipynb
├── reports/
│   ├── dataset_report.csv
│   └── possible_outliers.csv
├── images/
├── README.md
└── .gitignore
## Visualizations

### Mean Pixel Intensity Distribution

![Mean Pixel Intensity Distribution](images/intensity_distribution.png)

### File Size Distribution

![File Size Distribution](images/file_size_distribution.png)

### Intensity Outliers

![Mean Pixel Intensity Outliers](images/intensity_boxplot.png)
