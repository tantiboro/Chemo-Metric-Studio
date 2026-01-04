# 🧪 Chemo-Metric-Studio: Automated Electrochemical R&D Pipeline

**Chemo-Metric-Studio** (formerly Electro-Insight Legacy) is an automated data analysis platform designed to bridge the gap between "Wet Lab" experimentation and modern Data Science. It focuses on **Cyclic Voltammetry (CV)** analysis, utilizing signal processing and machine learning to detect quality issues in conductive polymer batches and analyze molecular properties.

> **Note:** This project focuses on *Chemical Analysis (CV, PCA, Molecular Viz)*. For the Battery Life Prediction project, please see [Electro-Insight](https://github.com/tantiboro/Electro-Insight).

## 🚀 Live Demo
[Click here to launch the Dashboard](https://share.streamlit.io/tantiboro/chemo-metric-studio/main/app.py)
*(Note: If the app is sleeping, please allow 30 seconds for the cloud container to wake up.)*

## 🧪 Key Features

### 1. Automated Signal Processing (The "Analyst")
* **Noise Reduction:** Implements Savitzky-Golay filtering to smooth raw sensor data without distorting peak heights.
* **Peak Detection:** Automatically identifies Anodic Peak Potential ($E_{pa}$) and Current ($I_{pa}$) using `scipy.signal`.
* **QC Logic:** Instantly flags batches as **PASS/FAIL** based on defined conductivity thresholds.

### 2. Chemometrics & Anomaly Detection (The "Data Scientist")
* **Batch Clustering:** Uses **Principal Component Analysis (PCA)** to visualize trends across hundreds of experimental runs.
* **SNV Normalization:** Includes a toggle for **Standard Normal Variate (SNV)** preprocessing. This decouples signal *intensity* (concentration/area) from signal *shape* (chemical identity), allowing for robust detection of contamination.

### 3. Structure-Property Simulation (The "Chemist")
* **Molecular Visualization:** Integrates **RDKit** to render chemical structures (e.g., Polythiophene, Ruthenium(bpy)₃) directly in the browser.
* **Predictive Modeling:** Simulates how chemical modifications (e.g., changing a monomer from Pyrrole to Thiophene) theoretically impact the electrochemical response.

## 🛠️ Tech Stack
* **Frontend:** Streamlit (Rapid dashboarding)
* **Data Processing:** Pandas, NumPy
* **Signal Processing:** SciPy (Peak finding, Smoothing)
* **Machine Learning:** Scikit-Learn (PCA, Preprocessing)
* **Chemoinformatics:** RDKit (SMILES rendering, Molecular Weight calc)
* **Visualization:** Plotly (Interactive scientific charts)

## 📂 Project Structure

```text
Chemo-Metric-Studio/
├── app.py              # Main dashboard application
├── analyzer.py         # Physics engine: smoothing & peak picking logic
├── chemometrics.py     # ML engine: PCA & SNV algorithms
├── generator.py        # Simulator: Creates synthetic CV data (Current vs Voltage)
├── structure_viz.py    # RDKit wrapper for molecular rendering
├── requirements.txt    # Python dependencies
├── packages.txt        # System-level dependencies (Linux graphics libs)
└── tests/              # Automated unit tests
