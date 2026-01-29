# Noise-Free Label Differential Privacy for Long-Tailed Classification

[cite_start]This repository contains the official implementation of the paper: **"Noise-Free Label Differential Privacy for Long-Tailed Classification with Latent Based Diffusion Augmentation"**. [cite: 1]

## 1. Overview

[cite_start]Existing label differential privacy (Label DP) methods often rely on randomized response (RR) and related label perturbation[cite: 6]. [cite_start]While these provide formal protection, they do so by corrupting labels and thereby introduce systematic bias, which is especially damaging in the **long-tailed classification** regime where minority classes are already data-starved[cite: 7, 15].

[cite_start]We propose a **noise-free alternative** that makes sampling-based label DP practical for long-tailed data[cite: 8]. Our pipeline performs **public padding in the latent space**:
* [cite_start]**Latent Augmentation**: Using an encoder and a class-conditional latent diffusion generator trained only on a disjoint public dataset, we synthesize per-class pseudo-features[cite: 9, 78].
* [cite_start]**Eliminating Bottlenecks**: This process eliminates rare labels and satisfies the frequency precondition required by sampling-based privacy theory[cite: 9, 61].
* [cite_start]**Poisson Subsampling**: We then apply value-independent Poisson subsampling and train a classifier via standard Empirical Risk Minimization (ERM), releasing only the trained model[cite: 10].

[cite_start]Our method achieves substantially higher utility under stricter privacy guarantees without injecting additive noise into gradients, parameters, or labels[cite: 13, 75].
