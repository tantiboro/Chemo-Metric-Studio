# ⚡ Electro-Insight: Automated Electrochemical R&D Pipeline

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://electro-insight-msd.streamlit.app)
![Python](https://img.shields.io/badge/Python-3.10-blue)
![Build Status](https://img.shields.io/badge/Build-Passing-brightgreen)
![Domain](https://img.shields.io/badge/Domain-Electrochemistry-purple)

**Electro-Insight** is an automated data analysis platform designed to bridge the gap between "Wet Lab" experimentation and modern Data Science. It streamlines the analysis of Cyclic Voltammetry (CV) data, utilizing signal processing and machine learning to detect quality issues in conductive polymer batches.

> **Why this project?** This application demonstrates the ability to translate complex physicochemical concepts (redox peaks, diffusion) into scalable, automated Python code—a key requirement for modern high-throughput R&D workflows.

## 🚀 Live Demo
**[Click here to launch the Dashboard](https://electro-insight-msd.streamlit.app)**
*(Note: If the app is sleeping, please allow 30 seconds for the cloud container to wake up.)*

---

## 🧪 Key Features

### 1. Automated Signal Processing (The "Analyst")
* **Noise Reduction:** Implements Savitzky-Golay filtering to smooth raw sensor data without distorting peak heights.
* **Peak Detection:** Automatically identifies Anodic Peak Potential ($E_{pa}$) and Current ($I_{pa}$) using `scipy.signal`.
* **QC Logic:** Instantly flags batches as **PASS/FAIL** based on defined conductivity thresholds.

### 2. Chemometrics & Anomaly Detection (The "Data Scientist")

* **Batch Clustering:** Uses **Principal Component Analysis (PCA)** to visualize trends across hundreds of experimental runs.
* **SNV Normalization:** Includes a toggle for **Standard Normal Variate (SNV)** preprocessing. This decouples signal *intensity* (concentration/area) from signal *shape* (chemical identity), allowing for robust detection of contamination or degradation.

### 3. Structure-Property Simulation (The "Chemist")
* **Molecular Visualization:** Integrates **RDKit** to render chemical structures (e.g., Polythiophene, Ruthenium(bpy)₃) directly in the browser using disconnected-ion notation for complexes.
* **Predictive Modeling:** Simulates how chemical modifications (e.g., changing a monomer from Pyrrole to Thiophene) theoretically impact the electrochemical response.

---

## 🛠️ Tech Stack

* **Frontend:** [Streamlit](https://streamlit.io/) (Rapid dashboarding)
* **Data Processing:** `Pandas`, `NumPy`
* **Signal Processing:** `SciPy` (Peak finding, Smoothing)
* **Machine Learning:** `Scikit-Learn` (PCA, Preprocessing)
* **Chemoinformatics:** `RDKit` (SMILES rendering, Molecular Weight calc)
* **Visualization:** `Plotly` (Interactive scientific charts)
* **CI/CD:** GitHub Actions (Automated testing on push)

---

## 📂 Project Structure

```text
Electro-Insight/
├── app.py              # Main dashboard application
├── analyzer.py         # Physics engine: smoothing & peak picking logic
├── chemometrics.py     # ML engine: PCA & SNV algorithms
├── generator.py        # Simulator: Creates synthetic CV data
├── structure_viz.py    # RDKit wrapper for molecular rendering
├── requirements.txt    # Python dependencies
├── packages.txt        # System-level dependencies (Linux graphics libs)
└── tests/              # Automated unit tests

## 💻 How to Run Locally

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/YOUR_USERNAME/Electro-Insight.git](https://github.com/YOUR_USERNAME/Electro-Insight.git)
    cd Electro-Insight
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the App:**
    ```bash
    streamlit run app.py


4.  **Set up Virtual Environment (Recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use: venv\Scripts\activate
    pip install -r requirements.txt
    ```
    ```
