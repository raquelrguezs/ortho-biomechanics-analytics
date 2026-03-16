# OrthoAnalytics: Clinical Gait & Orthotic Impact Study

## Project Overview
This project performs an in-depth clinical analysis of human gait patterns to evaluate the effectiveness of orthopedic braces. Using real biomechanical data from the UCI Machine Learning Repository, we analyze how different orthopedic interventions (knee vs. ankle braces) affect joint kinematics, symmetry, and movement efficiency.

## Repository Structure
- `data/`: 
    - `raw/`: Original biomechanical sensor data (`gait.csv`).
    - `processed/`: Time-normalized and cleaned gait cycles.
- `notebooks/`: 
    - `01_data_exploration.ipynb`: Initial EDA and ROM analysis.
    - `02_asymmetry_analysis.ipynb`: Bilateral comparison and Symmetry Index.
    - `03_brace_detection_ml.ipynb`: Machine Learning model (100% Accuracy).
- `reports/`: 
    - `clinical_impact_summary.md`: Detailed clinical findings.
    - `executive_dashboard.png`: Visual summary of all project phases.
- `scripts/`: Data processing utilities.

## Dataset Information
- **Source**: UCI Machine Learning Repository - Enhanced Gait Biomechanics Dataset.
- **Participants**: 10 healthy subjects.
- **Interventions**: Unbraced (Baseline), Knee-Braced (Right), Ankle-Braced (Right).
- **Sensors**: Joint angles, velocity, and acceleration for Ankle, Knee, and Hip.
- **Format**: Time-normalized to 101 points per gait cycle (0-100% stride).

## Clinical Goals
1. **Kinematic Comparison**: Quantify the change in joint range of motion (ROM) induced by different braces.
2. **Symmetry Analysis**: Detect compensatory movements in the contralateral (unbraced) limb.
3. **Compliance & Detection**: Build models to automatically identify brace usage from walking patterns.

## How to Run
1. Create a virtual environment: `python3 -m venv .venv`
2. Activate it: `source .venv/bin/activate`
3. Install dependencies: `pip install pandas matplotlib seaborn scikit-learn jupyter`
4. Run the notebooks in order.

## Author
**Raquel Rodríguez** - Clinical Data Analyst & AI Enthusiast
