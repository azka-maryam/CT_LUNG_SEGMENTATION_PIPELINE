# 🫁 CT LUNG SEGMENTATION PIPELINE

This project demonstrates a **CT chest imaging workflow** that combines **AI-assisted preprocessing in Python** and **manual lung segmentation using 3D Slicer**.  
It includes preprocessing of multiple CT scans, comparison of image statistics, and manual refinement of segmentation masks.

---

## 🧠 Overview

The workflow preprocesses chest CT scans in batch, analyzes image statistics before and after processing, and performs manual lung segmentation refinement using 3D Slicer tools.  
The project illustrates the reproducible workflow of a real-world medical imaging pipeline.

---

## 🧰 Tools & Software Used

| Category | Tools |
|-----------|-------|
| **Preprocessing (AI-assisted)** | Python, SimpleITK, NumPy, pandas |
| **Visualization & Segmentation** | 3D Slicer (Threshold, Erase, Level Tracing, Smoothing) |
| **File Formats** | `.nii.gz`, `.nrrd`, `.seg.nrrd`, `.csv` |

---

## 📁 Folder Structure

> *(Medical data is not included in the repository for privacy and size reasons.)*

CT_LUNG_SEGMENTATION_PIPELINE/
│
├── 01_Notebooks/
│ ├── 01_Batch_Preprocessing.ipynb
│ ├── 02_Compare_Statistics.ipynb
│ └── 03_Segmentation_Notes.ipynb
│
├── 02_CSV_results/
│ ├── raw_data_stats.csv
│ └── preprocessed_data_stats.csv
│
├── 03_Images/
│ ├── lung_threshold_segmentation.png
│ ├── manual_refinement.png
│ └── final_segmentation.png
│
├── 04_Flowchart.png
│
└── README.md

yaml
Copy code

---

## ⚙️ Workflow Summary

### 1️⃣ AI-Assisted Batch Preprocessing
- Used **AI-generated Python script** to automate batch preprocessing of 5 CT chest scans.  
- Preprocessing steps included:
  - **Resampling** to 1 mm³ voxel spacing  
  - **Intensity normalization** to range 0–1  
  - Saving processed files automatically  
- **NumPy** and **pandas** used to compute and compare image statistics (size, spacing, and intensity values).  
- Output CSV summaries were generated for raw and preprocessed datasets.

---

### 2️⃣ Manual Lung Segmentation in 3D Slicer
- Opened preprocessed scans in **CT Lung window** for better contrast.
- Used the **Threshold tool** to segment lung air regions.
- **Erase tool** removed unwanted outer air and tracheal regions.
- **Level Tracing tool** filled missed lung areas that threshold didn’t capture.
- Applied **Smoothing (Median/Gaussian)** to refine lung borders.
- Exported final segmentation as `.nrrd`.

---

### 3️⃣ Comparison & Outputs
- Compared **raw vs. preprocessed statistics** using NumPy arrays.
- All results saved in `/02_CSV_results/`.
- Manual segmentation saved in `/03_Images/` as visual results.

---

## 🧪 Results Overview

| File | Description |
|------|--------------|
| `raw_data_stats.csv` | Original CT image statistics |
| `preprocessed_data_stats.csv` | Processed image statistics |
| `lung_segmentation.png` | Manual lung mask visual output |

---

## 🔁 Workflow Reproducibility

This project highlights **reproducible medical imaging steps**, meaning all preprocessing, inspection, and segmentation operations are **clearly documented** and can be replicated by others using their own data.

---

📊 Key Notes
Lungs (left and right together) were segmented as a single region.

Air in trachea and outside body was manually erased.

Missed regions inside lungs were corrected using Level Tracing.

Some lung holes remained to preserve inner structures.

No quantitative volume or density measurements were performed.

This workflow emphasizes clarity, reproducibility, and realism in handling chest CT segmentation.

🧾 Summary
Step	Description
Preprocessing	AI-assisted Python pipeline for normalization & resampling
Segmentation	Manual refinement using 3D Slicer
Comparison	NumPy-based statistical validation
Visualization	Screenshots saved in /03_Images/
Flowchart	Included as /04_Flowchart.png and Mermaid code

👩‍💻 Author
Azka Maryam
LinkedIn [www.linkedin.com/in/azka-maryam-55582b26a]
Part of Medical Imaging & AI Workflow Portfolio Projects

