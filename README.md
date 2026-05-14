# ISU-Undergraduate-Research-F25-S26

## Machine Unlearning and Uncertainty Quantification Experiments

This repository studies how machine unlearning affects model calibration and predictive uncertainty on CIFAR-10. The notebooks compare uncertainty behavior across different unlearning settings and model architectures.

## Experiment Suite Overview

### 1) Removing Different Proportions of Data

These notebooks analyze how uncertainty changes when progressively larger portions of the training set are unlearned (5%, 10%, 15%, and 20%). The evaluation focuses on Expected Calibration Error (ECE) and Brier Score (BS), using MC Dropout uncertainty estimation on the CIFAR-10 test set.

- **`Experiments/removing_different_proportions.ipynb`**: Proportion-based unlearning with a CNN.
- **`Experiments/removing_different_proportions_resnet18.ipynb`**: Proportion-based unlearning with ResNet-18.

**Key observation:** as more data is unlearned, both ECE and Brier Score increase, indicating greater predictive uncertainty.

### 2) Unlearning Different Data Modalities

These notebooks keep the unlearning ratio fixed at 5% and vary what kind of samples are removed:

- Random instances from the training set
- Gaussian-noise-corrupted instances
- Modified-label instances (randomly flipped labels)

Uncertainty is evaluated with ECE and Brier Score after temperature scaling on CIFAR-10 test data.

- **`Experiments/unlearning_different_data_modalities.ipynb`**: Data-modality unlearning with a CNN.
- **`Experiments/unlearning_different_data_modalities_resnet18.ipynb`**: Data-modality unlearning with ResNet-18.

**Key observation:** unlearning modified-label samples has the strongest negative impact on calibration and uncertainty metrics.

## Supporting Notebooks

- **`Experiments/train_uncertainty_demo.ipynb`**: Training-focused uncertainty demonstration.
- **`Experiments/train_unlearn_demo.ipynb`**: Training and unlearning workflow demonstration.
- **`Experiments/uncertainty_demo.ipynb`**: Standalone uncertainty estimation demonstration.
