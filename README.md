# A Hausdorff-Guided Deep Learning Approach for Monitoring the Motion of Rotating Arctic Ice Floes

---

## 📌 Authors
Adan Wu, Tao Che*, Chengzhu Ji, Xiaowen Zhu, Jinlei Chen, Qingchao Xu,  
Qun Gu, Rui Zhang, Kaihui Zhang, Lei Fu, Shengpeng Chen  

**Affiliation:**  
Key Laboratory of Cryospheric Science and Frozen Soil Engineering,  
Heihe Remote Sensing Experimental Research Station,  
Northwest Institute of Eco-Environment and Resources,  
Chinese Academy of Sciences, Lanzhou, China  
---

## 🧭 Framework Overview

![Flow chart](https://github.com/RouteViewLab/A-Hausdorff-Guided-Deep-Learning-Approach-for-Monitoring-the-Motion-of-Rotating-Arctic-Ice-Floes/raw/main/Flow%20chat.png)

---

## 🔬 Research Background & Motivation

In Arctic ice monitoring, **rotation and deformation of ice floes** are critical factors that significantly affect motion estimation.

Our team has identified that:

> **Rotation and deformation are key reasons for the failure of traditional feature matching methods (e.g., SIFT, A-KAZE).**

Traditional approaches assume limited geometric variation. However, in real Arctic scenarios:
- Ice floes often undergo **large-angle rotations**
- Local textures are **degraded or homogeneous**
- Geometric relationships become **highly nonlinear**

To address this issue, we further conducted a **preliminary study based on a deep learning framework** to analyze the impact of rotation on matching performance:

🔗 Project link:  
https://github.com/RouteViewLab/A-Hausdorff-Guided-Deep-Learning-Approach-for-Monitoring-the-Motion-of-Rotating-Arctic-Ice-Floes

---

## 🔬 Preliminary Experiment: Impact of Rotation

### 📈 Quantitative Analysis

![HD vs Rotation Angle](https://raw.githubusercontent.com/LZUFE-Machine-Learning/A-Hausdorff-Guided-Deep-Learning-Approach-for-Monitoring-the-Motion-of-Rotating-Arctic-Ice-Floes/main/Variation%20of%20Hausdorff%20Distance%20with%20Rotation%20Angle.png))

This figure shows the variation of **Hausdorff Distance (HD)** with respect to rotation angle for ice floe **B2**.

- Minimum HD (**3.16**) occurs at approximately **40°**, indicating optimal alignment  
- Maximum HD (**118.07**) reflects severe mismatch  
- Strong nonlinearity indicates high sensitivity to rotation  

👉 **Insight:**  
Rotation drastically alters geometric similarity, making direct matching unreliable.

---

### 🖼️ Qualitative Comparison

![Rotation Comparison](https://raw.githubusercontent.com/LZUFE-Machine-Learning/A-Hausdorff-Guided-Deep-Learning-Approach-for-Monitoring-the-Motion-of-Rotating-Arctic-Ice-Floes/main/Rotation%20Comparison%20Chart.png)

#### 🔹 Before Rotation Alignment
- Feature matches are **disordered and inconsistent**  
- Significant geometric deviation  
- High mismatch rate  

#### 🔹 After Rotation Alignment (~40°)
- Ice floe is **well aligned**  
- Matches become **structured and reliable**  
- Significant improvement in accuracy  

---

## 🚀 Method Overview

This repository implements a **rotation-aware deep learning framework** that integrates:

- **Hausdorff Distance** → rotation estimation  
- **SuperPoint** → feature extraction  
- **SuperGlue** → feature matching  

Key advantages:
- Robust to **large rotation**
- Handles **low-texture regions**
- Improves **matching accuracy and stability**

---

## ⚙️ Requirements

- Python >= 3.11  
- PyTorch >= 1.6  
- NumPy, SciPy, OpenCV  
- Matplotlib  

---


## 🏋️ Training


python train4.py train_base configs/magicpoint_shapes_pair.yaml magicpoint_synth --eval

python train4.py train_joint configs/superpoint_dataset_train_heatmap.yaml superpoint_my_data --eval --debug

python train.py --feature_dim 256 --dataset_offline_rebuild 1 --batch_size 32 --eval


---


## Results

| Method          | Matching Pairs | Matched Accuracy |
|-----------------|----------------|------------------|
| Proposed method | 50             | 100%             |
| SIFT            | 15             | 40%              |
| A-KAZE          | 19             | 68.42%           |

---
##Acknowledgments

This work is built upon:

SuperPoint

SuperGlue

Thanks to the original authors for their contributions.


---


## 📬 Contact

If you have any questions:

📧 wuadan@lzb.ac.cn
