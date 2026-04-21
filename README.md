# Sequential Optimization for Deep Learning Training (AdaGrad → Lion)

## Overview
This project explores optimization strategies for training a fixed autoencoder under strict constraints (AdaGrad and Lion only).

The main idea is that different optimizers perform better at different training stages.

## Key Idea
- AdaGrad is effective in early training ("basin finding")
- Lion is effective in late training ("refinement")

We combine them using a sequential strategy:
**AdaGrad → Lion**

## Method
- 20% of training with AdaGrad
- 80% with Lion
- Learning rate schedule: warmup + cosine annealing
- Batch size: 350

## Results
- Final loss: **0.008573**
- ~85% improvement over initial loss
- Ranked **1st place** in course competition (30+ participants)

## Insights
- AdaGrad suffers from late-stage stagnation due to shrinking effective learning rate
- Lion is sensitive to learning rate and gradient noise
- Warmup is critical when switching optimizers
- Larger batch sizes stabilize Lion updates

## Files
- `Final.ipynb` – full implementation
- `Presentation.pdf` – detailed explanation and results
