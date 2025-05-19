# APLT
Offical implementation of our Towards Micro-Action Recognition with Limited Annotations: An Asynchronous Pseudo Labeling and Training Approach in IJCAI2025.
## 📖 Abstract

Micro-Action Recognition (MAR) aims to classify subtle human actions in videos. However, annotating MAR datasets is particularly challenging due to the subtlety of actions. To this end, we introduce the setting of Semi-Supervised MAR (SSMAR), where only a part of samples are labeled. We first evaluate traditional Semi-Supervised Learning (SSL) methods for SSMAR and find that these methods tend to overfit on inaccurate pseudo-labels, leading to error accumulation and degraded performance. This issue primarily arises from the common practice of directly using classifier predictions as pseudo-labels to train the model.

To solve this issue, we propose a novel framework called **Asynchronous Pseudo Labeling and Training (APLT)**, which explicitly separates the pseudo-labeling process from model training.

Specifically, we introduce a semi-supervised clustering method during the offline pseudo-labeling phase to generate more accurate pseudo-labels. Moreover, a self-adaptive thresholding strategy is proposed to dynamically filter noisy labels of different classes. We then build a memory-based prototype classifier based on the filtered pseudo-labels, which is fixed and used to guide the subsequent model training phase. By alternating the pseudo-labeling and model training phases asynchronously, the model can be learned with more accurate pseudo-labels and avoid the overfitting issue.

Experiments on three MAR datasets show that our APLT significantly outperforms state-of-the-art SSL methods. For instance, APLT improves accuracy by 14.5% over FixMatch on the MA-12 dataset when using only 50% labeled data.

---

## ⚙️ Method Overview

As illustrated in the figure below, we propose an **Asynchronous Pseudo-labeling and Training (APLT)** framework tailored for **Semi-Supervised Micro-Action Recognition (SSMAR)**. The framework consists of two alternating phases:

- **Offline Pseudo-labeling Phase**
- **Online Model Training Phase**
![Framework](your_framework_image_path_here.png)
