# Medical Image Dataset Quality Analysis

Large-scale quality analysis of a **16+ GB medical imaging dataset** containing **24,371 NPZ files** using Python, NumPy, Pandas, Matplotlib, and JupyterLab.

The purpose of this project is to inspect the structure and quality of a large medical image dataset, detect potential anomalies, generate structured reports, and prepare the dataset for future machine learning or computer vision workflows.

## 📊 Dataset Summary

* **Total NPZ files:** 24,371
* **Total archive size:** 16+ GB
* **Slices per file:** 24
* **Image resolution:** 224 × 224
* **Data type:** uint8
* **Successfully processed:** 24,371
* **Corrupted files detected:** 0

Each NPZ file contains an array named:

```python
data
```

with the shape:

```text
(24, 224, 224)
```

This represents:

```text
24 image slices × 224 height × 224 width
```

## 🎯 Project Goals

The project performs automated quality inspection of the full dataset.

The pipeline:

* validates NPZ files
* checks whether files can be opened successfully
* verifies image dimensions
* verifies array data types
* calculates minimum, maximum, and mean pixel intensity
* measures individual NPZ file sizes
* detects potential intensity outliers
* generates structured CSV reports
* creates visualizations for dataset analysis

## 🔄 Processing Workflow

```text
16+ GB ZIP Archive
        ↓
24,371 NPZ Files
        ↓
Automated File Inspection
        ↓
NPZ Structure Validation
        ↓
Image Shape Validation
        ↓
Pixel Intensity Analysis
        ↓
File Size Analysis
        ↓
Potential Outlier Detection
        ↓
CSV Reports
        ↓
Visualizations
```

## 📁 Project Structure

| Folder / File      | Description                                           |
| ------------------ | ----------------------------------------------------- |
| `images/`          | Generated charts and visualizations                   |
| `notebooks/`       | Jupyter notebook containing the complete analysis     |
| `reports/`         | Dataset quality reports and potential outlier records |
| `README.md`        | Project documentation                                 |
| `requirements.txt` | Required Python packages                              |
| `.gitignore`       | Files excluded from version control                   |

## 📈 Dataset Statistics

The dataset was structurally consistent across all 24,371 files.

| Metric                 |  Result |
| ---------------------- | ------: |
| Number of NPZ files    |  24,371 |
| Successfully processed |  24,371 |
| Corrupted files        |       0 |
| Slices per scan        |      24 |
| Image height           |     224 |
| Image width            |     224 |
| Data type              |   uint8 |
| Average NPZ file size  | 0.68 MB |

### Mean Pixel Intensity

| Statistic          |  Value |
| ------------------ | -----: |
| Mean               |  42.19 |
| Standard deviation |  16.90 |
| Minimum            |   6.90 |
| 25th percentile    |  29.69 |
| Median             |  40.49 |
| 75th percentile    |  53.06 |
| Maximum            | 162.12 |

The wide range of mean pixel intensities suggests that some scans have noticeably different brightness characteristics.

These scans were flagged for further inspection rather than automatically removed.

## 🔎 Outlier Detection

Potential intensity outliers were detected using the Interquartile Range method.

```python
Q1 = df["mean_pixel"].quantile(0.25)
Q3 = df["mean_pixel"].quantile(0.75)

IQR = Q3 - Q1

lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
```

Scans outside these limits were recorded in:

```text
reports/possible_outliers.csv
```

Potential outliers were **not automatically deleted**, because unusual intensity values do not necessarily indicate invalid medical images.

## 📊 Visualizations

### Mean Pixel Intensity Distribution

This chart shows the distribution of average pixel intensity across all **24,371 image volumes**.

![Mean Pixel Intensity Distribution](images/intensity_distribution.png)

### NPZ File Size Distribution

This chart shows how individual NPZ file sizes are distributed across the dataset.

![File Size Distribution](images/file_size_distribution.png)

### Potential Intensity Outliers

A box plot was used to highlight scans with unusually high or low mean pixel intensity.

![Mean Pixel Intensity Outliers](images/intensity_boxplot.png)

## ✅ Key Results

* **24,371 / 24,371 files** successfully processed
* **0 corrupted or unreadable NPZ files** detected
* All image volumes contain exactly **24 slices**
* All image slices have a resolution of **224 × 224**
* All arrays use the **uint8** data type
* Mean pixel intensity across the dataset is approximately **42.19**
* Potential intensity anomalies were identified for further investigation
* A structured dataset quality report was generated automatically

## 📄 Generated Reports

The project produces two main CSV files.

### Dataset Report

```text
reports/dataset_report.csv
```

Contains information such as:

* filename
* number of slices
* image height
* image width
* data type
* minimum pixel intensity
* maximum pixel intensity
* mean pixel intensity
* file size
* processing status

### Potential Outliers

```text
reports/possible_outliers.csv
```

Contains scans identified as possible intensity outliers for additional inspection.

## 🛠️ Technologies Used

`Python` · `NumPy` · `Pandas` · `Matplotlib` · `JupyterLab`

## 🚀 Running the Project

Install the required packages:

```bash
pip install -r requirements.txt
```

Then start JupyterLab:

```bash
jupyter lab
```

Open:

```text
notebooks/dataset_analysis.ipynb
```

## 💾 Dataset Availability

The original **16+ GB dataset is not included in this repository** because of its size and potential redistribution restrictions.

Only the analysis code, generated reports, and visualizations are included.

## 🧠 Skills Demonstrated

This project demonstrates practical experience with:

* large-scale dataset processing
* NumPy arrays
* NPZ file handling
* ZIP archive processing
* automated dataset validation
* data quality analysis
* Pandas
* statistical analysis
* outlier detection
* data visualization
* JupyterLab
* memory-conscious data processing
* preparation of image datasets for machine learning

## 🔮 Future Improvements

Possible future extensions include:

* automatic detection of blank or near-empty slices
* visualization of detected intensity outliers
* pixel intensity normalization
* image preprocessing pipelines
* dataset labeling analysis
* train/validation/test preparation
* machine learning model development
* computer vision experiments

## 👤 Author
Mohamad Mustafa Hindi

Created as a portfolio project demonstrating Python-based large-scale dataset inspection, quality analysis, and preprocessing.
