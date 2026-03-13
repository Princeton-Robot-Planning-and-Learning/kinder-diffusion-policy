# kinder-diffusion-policy

A fork of [diffusion_policy](https://github.com/real-stanford/diffusion_policy) adapted for the [KinDER](https://prpl.group/kinder-site/).

---

## Overview

`kinder-diffusion-policy` extends upstream diffusion_policy with the following capabilities:

### Training
- Support different config files for both 2D and 3D environments in KinDER.
- Support mobile manipulator policy in KinDER

### Inference
- Provide a policy server to evaluate different environments in KinDER

---

## Installation

Clone the repository:

```bash
git clone git@github.com:Princeton-Robot-Planning-and-Learning/kinder-diffusion-policy.git
```

---

## Environment Setup

```console
$ mamba env create -f conda_environment.yaml
```

or
```console
$ conda env create -f conda_environment.yaml
```

---

## Training

### Step 1: Prepare Data

Follow the [README for KinDER](https://github.com/Princeton-Robot-Planning-and-Learning/prpl-mono/blob/main/kinder-imitation-learning/README.md)

---

### Step 2: Launch Training

```bash
cd ~/kinder-diffusion-policy
mamba activate robodiff
python train.py --config-name=train_sweep3d_image
```

---

## Evaluation

### Step 1: Run the evaluation server

```bash
cd ~/kinder-diffusion-policy
mamba activate robodiff
python policy_server.py --ckpt-path $Checkpoint_path 
```

### Step 2: Launch the KinDER environment

Follow the [README for KinDER](https://github.com/Princeton-Robot-Planning-and-Learning/prpl-mono/blob/main/kinder-imitation-learning/README.md)
