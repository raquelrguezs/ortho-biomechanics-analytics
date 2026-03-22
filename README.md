# OrthoBiomechanics Analytics: Exploratory Study on Orthotic Impact & Gait Kinematics

## Executive Summary
This project explores the application of machine learning to characterize and contrast the kinematic impact of orthopedic bracing (knee and ankle) on gait. Using data from a controlled experiment, we analyze joint Range of Motion (ROM) and movement symmetry to investigate compensatory patterns and the feasibility of automated detection of orthotic usage patterns. While initial models achieved high classification accuracy, this project serves as a critical methodological review of subject-specific gait signatures and the high risk of subject leakage in small-scale biomechanical datasets.

## Problem Statement
In clinical rehabilitation, assessing longitudinal compliance with prescribed orthotics (braces) remains challenging in clinical practice. Automated quantification of bracing effects through kinematic data could potentially enable:
- **Preliminary Compliance Monitoring**: Observing deviations from expected movement patterns.
- **Biomechanical Impact Assessment**: Quantifying how joint restriction propagates through the lower-limb kinetic chain.
- **Hypothesis Generation**: Identifying compensatory movements associated with specific device configurations.

## Objective
To implement a data-driven framework for:
1. Quantifying localized and global kinematic changes (hip, knee, ankle) during experimental bracing.
2. Evaluating classification performance for brace-type detection (none, knee, or ankle) within a controlled environment.
3. Documenting the impact of **subject leakage** on model performance and clinical generalizability.

## Dataset Information (Context & Limitations)
- **Source**: UCI Machine Learning Repository - Biomechanical Gait Dataset.
- **Participants**: 10 healthy individuals (exploratory cohort).
- **Clinical Context**: All participants are asymptomatic; **no musculoskeletal pathologies are present**. The data represents "induced" gait modifications in healthy subjects.
- **Experimental Conditions**: Unbraced (Baseline), Right Knee Brace, Right Ankle Brace.

## Methodology

### Preprocessing & Feature Extraction
- **Temporal Alignment**: Gait cycles time-normalized to a 100% stride basis for intra-subject comparison.
- **Feature Engineering**: Extraction of clinical metrics per gait cycle (ROM, mean/SD joint angles, peak timing) to capture subject-specific gait patterns.

### Modeling & Evaluation Strategy
Initial validation was performed using a standard **stratified split at the gait cycle level** (70/30). 
- **Validation Metric**: Performance was assessed using Accuracy and F1-Score.
- **Model Critique**: The near-perfect accuracy (Acc 100%) observed **within this specific dataset** is treated as a methodological artifact of **Subject Leakage**. 

### Subject Leakage and Validation Constraints
Since the split occurred at the gait cycle level rather than the subject level, samples from the same individual are present in both subsets. This demonstrates that the model is likely optimizing for subject-specific kinematic signatures rather than generalizable orthotic effects. For clinical validity, a **Leave-One-Subject-Out (LOSO)** validation would be required.

## Key Findings (Within this Cohort)
- **Knee Bracing (Experimental)**: Associated with a **~31.4% reduction in knee ROM** and an associated **~13.6% secondary reduction** at the ankle joint.
- **Kinematic chain coupling**: Bracing effects are not isolated to the target joint; they propagate through the limb, potentially altering stride dynamics.
- **Generalization Warning**: These findings describe the behavior of **this specific healthy cohort** and are not directly transferable to clinical populations without further cross-validation.

## Clinical Interpretation (Conditional Framework)
This framework **could potentially** serve as a proof-of-concept for automated monitoring tools. If deployed in a remote setting, such models might help identify kinematic deviations that suggest a patient is either non-compliant or experiencing suboptimal biomechanical alignment from the device.

## Methodological Limitations (Critical Review)
1. **Limited Subject Diversity (N=10)**: High probability of the model over-fitting to the gait quirks of the participants.
2. **Cycle-level Split**: Direct subject leakage prevents claims of predictive power on unseen users.
3. **Controlled Conditions**: Data originates from laboratory walking; real-world terrain and activities are likely to significantly degrade model performance.
4. **Asymptomatic Population**: The absence of pathology limits the findings to "healthy compensation" patterns.

## Reproducibility
1. `pip install -r requirements.txt`
2. Run notebooks in `/notebooks` to observe the EDA and the classification analysis.
Expected outputs include feature extraction summaries and classification performance results.
