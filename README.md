# ISU-Undergraduate-Research-F25-S26

Machine Unlearning and Uncertainty Quantification Experiments

This repository contains a series of experiments exploring the relationship between machine unlearning and predictive uncertainty.

## Experiment 2: Removing Different Proportions of Data

This experiment investigates how removing an increasing proportion of training data affects the model's uncertainty. We unlearn 5%, 10%, 15%, and 20% of the CIFAR-10 training set and measure the change in Expected Calibration Error (ECE) and Brier Score (BS) using MC Dropout for uncertainty estimation.

The experiment is conducted with two different model architectures:

*   **`Experiments/removing_different_proportions.ipynb`**: A simple Convolutional Neural Network (CNN).
*   **`Experiments/removing_different_proportions_resnet18.ipynb`**: A ResNet-18 architecture.

### Findings
In both CNN and ResNet-18 models, we observe that as the proportion of unlearned data increases, both ECE and Brier Score consistently rise. This suggests that removing more data through unlearning leads to higher predictive uncertainty, as the model becomes less confident in its predictions.

## Experiment 4: Unlearning Different Data Modalities

This experiment explores how unlearning different *types* of data impacts predictive uncertainty. We unlearn a fixed 5% of the CIFAR-10 training data, but vary the modality of the data being removed:

*   **Random Instances**: A random 5% of the training data.
*   **Gaussian-Noise Instances**: 5% of training samples corrupted with Gaussian noise.
*   **Modified-Label Instances**: 5% of training samples with their labels randomly flipped.

Uncertainty is measured using ECE and Brier Score after applying temperature scaling.

The experiment is conducted with two different model architectures:

*   **`Experiments/unlearning_different_data_modalities.ipynb`**: A simple Convolutional Neural Network (CNN).
*   **`Experiments/unlearning_different_data_modalities_resnet18.ipynb`**: A ResNet-18 architecture.

### Findings
Across both model architectures, unlearning modified-label instances results in the most significant increase in both ECE and Brier Score. This indicates that removing "hard" or mislabeled examples has a more pronounced effect on model uncertainty compared to removing random or noisy data.
