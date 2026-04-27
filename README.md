# CNN Training Strategy Comparison

A comparative deep learning project that studies how the order and pacing of data exposure during training affects model performance, efficiency, and learning dynamics.

This project evaluates multiple CNN architectures under different training strategies on CIFAR-10 and CIFAR-100.

## Objective

Standard training uses the full dataset from the beginning. This project explores whether alternative training schedules can improve learning.

We compare:

- Full Dataset Training
- Progressive Revelation
- Curriculum Learning
- Hybrid Strategy (Progressive + Curriculum)

Across three architectures:

- VGG-style CNN
- ResNet-18
- EfficientNet-B0

## Datasets

### CIFAR-10
- 10 classes
- 50,000 training images
- 10,000 test images
- 32×32 RGB images

### CIFAR-100
- 100 classes
- Same image size
- More challenging due to higher class count

## Models Used

### VGG-style CNN
Custom CNN inspired by VGG using stacked convolution layers and max pooling.

### ResNet-18
Residual CNN with skip connections for stable deep learning.

### EfficientNet-B0
Parameter-efficient CNN with modern scaling and optimized convolution blocks.

## Training Strategies

### Strategy 1: Full Dataset
Train using all data from the start.

### Strategy 2: Progressive Revelation
Gradually increase available training data:

10% → 25% → 50% → 75% → 100%

### Strategy 3: Curriculum Learning
Train from easier samples to harder samples using entropy-based difficulty scoring.

### Strategy 4: Hybrid
Combines:
- Progressive data growth
- Easy-to-hard curriculum ordering

## Preprocessing

Training augmentations:
- Random Crop
- Random Horizontal Flip

Normalization applied separately for CIFAR-10 and CIFAR-100.

## Training Setup

- Loss Function: Cross-Entropy Loss
- Optimizer: SGD with Momentum
- Scheduler: Cosine Annealing Learning Rate

## Evaluation Metrics

- Final Validation Accuracy
- Best Validation Accuracy
- GPU Hours
- Accuracy per GPU-Hour
- Forgetting Analysis

## Key Findings

- ResNet-18 was generally the strongest and most stable model.
- CIFAR-10 achieved higher accuracy than CIFAR-100.
- Progressive strategy performed strongly on CIFAR-10.
- Hybrid strategy performed best on CIFAR-100.
- Training strategy affects accuracy, convergence speed, and efficiency.

## How to Run

Install dependencies:

pip install torch torchvision numpy matplotlib

Run the notebook cells sequentially.
