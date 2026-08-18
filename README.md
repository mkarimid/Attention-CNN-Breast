# Attention-CNN-Breast 🏥

**Enhancing Generalization in Breast Cancer Histopathology Classification Through Dual-Attention Learning**

[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)](https://www.tensorflow.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![DOI](https://zenodo.org/badge/DOI/YOUR-DOI-HERE.svg)](https://doi.org/YOUR-DOI-HERE)

> 📖 **Paper**: [Read the full paper](LINK_TO_PAPER)  
> 👤 **Authors**: Farid Karimi et al.

---

## 📌 Overview

This repository contains the official implementation of a **dual-attention CNN** (DANet-based) for breast cancer histopathology classification. The model combines:

- 🔍 **Position Attention Module (PAM)** – captures long-range spatial dependencies
- 🎯 **Channel Attention Module (CAM)** – emphasizes discriminative feature channels
- 📊 **Comprehensive data augmentation** – improves robustness to staining variations

## ✨ Key Results

| Dataset | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|---------|----------|-----------|--------|----------|---------|
| **BreaKHis** (benchmark) | 94.07% | 94.59% | 97.13% | 95.85% | 98.53% |
| **Kashani** (clinical, independent) | **98.70%** | **99.18%** | **99.18%** | **99.18%** | — |

> 🎯 The model achieves **state-of-the-art cross-dataset generalization** without any fine-tuning on the target domain.

## 🏗️ Architecture

<p align="center">
  <img src="figures/architecture.png" alt="Model Architecture" width="700"/>
</p>

The network consists of:
1. Three convolutional blocks (64 → 128 → 256 filters) with BatchNorm + MaxPooling
2. A **DANet block** combining PAM and CAM in parallel
3. Global Average Pooling + two Dense layers (256, 128) with L2 regularization
4. Dropout (0.4) and a sigmoid output for binary classification

## 📦 Installation

```bash
# Clone the repository
git clone https://github.com/YOUR-USERNAME/Attention-CNN-Breast.git
cd Attention-CNN-Breast

# Create a virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
