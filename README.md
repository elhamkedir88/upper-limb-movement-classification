# Interpretable Joint Movement Classification via Combinatorial DTW Medoid Distances

> **Conference:** IISCC 2026  
> **Domain:** Biomedical Signal Processing, Wearable IMU Sensing, Applied Machine Learning  
> **Key Result:** Achieved **91.88% overall classification accuracy** using a 75-feature Cubic SVM.

###  Quick Links
* 📄 **[Download Full Research Paper (PDF)](IISCC2026_paper.pdf)**
* 📊 **[Download IISCC 2026 Slide Deck (PDF)](IISCC2026_presentation.pdf)**
---

##  Project Overview
Rehabilitation tracking requires accurate, interpretable classification of multi-joint physical exercises. This research presents an end-to-end Machine Learning framework using **19-channel wearable IMU sensor data** to classify upper-limb movements while accounting for joint coupling effects.

---

##  Methodology & Technical Architecture

1. **Kinematic Data Extraction:** Processed multi-channel IMU data across accelerometer, gyroscope, user acceleration, gravity, quaternion, and Euler angle metrics (19 sub-channels).
2. **Combinatorial Feature Engineering:** Generated cycle-level Dynamic Time Warping (DTW) medoid distance metrics across individual, paired, and triplet channel combinations (3,477 total initial features).
3. **Feature Selection:** Applied **RUSBoost ensemble feature selection** to rank predictor importance and remove redundancy.
4. **Classification Engine:** Evaluated performance using a **Cubic Polynomial Support Vector Machine (SVM)**.


```mermaid
graph TD
    A[19-Channel IMU Sensor Data <br> Accel, Gyro, Quat, Euler] --> B[Kinematic Data Extraction & Cycle Segmentation]
    B --> C[Combinatorial Sub-channel Grouping <br> Individual, Pairs, Triplets]
    C --> D[DTW Medoid Distance Calculation <br> 3,477 Initial Features]
    D --> E[RUSBoost Ensemble Feature Selection <br> Rank Importance & Prune Redundancy]
    E --> F[75 Optimized Features]
    F --> G[Cubic Polynomial SVM Classifier]
    G --> H[Joint Movement Classification <br> 91.88% Overall Accuracy]
    
    style A fill:#f9f2f4,stroke:#333,stroke-width:2px
    style E fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style G fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    style H fill:#fff3e0,stroke:#f57c00,stroke-width:2px
```
---

##  Key Results & Performance Metrics

| Model Configuration | Feature Count ($N$) | Overall Accuracy | Key Finding / Trait |
| :--- | :--- | :--- | :--- |
| **Unpruned Baseline** | 3,477 | 87.60% | High dimensionality, redundant sub-channels |
| **Euclidean 1-NN** | — | 82.32% | Sensitive to speed variability across subjects |
| **Optimized Cubic SVM** | **75** | **91.88%** | **Optimal balance of accuracy & computational efficiency** |

* **High-Accuracy Joints:** Isolated wrist movements achieved peak accuracy (**96.04%**).
* **Kinematic Coupling Discovery:** Shoulder and elbow interactions exhibited bidirectional kinematic coupling, resulting in an elbow Average Precision (AP) of **0.624**.

---

## 📬 Contact & Citation
* **Author:** Elham
* **GitHub:** [elhamkedir88](https://github.com/elhamkedir88)
