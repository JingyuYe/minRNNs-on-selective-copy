# Scaled Replication of “Were RNNs All We Needed?” on Selective Copy

Replication study of **minGRU** and **minLSTM** from *Were RNNs All We Needed?*, compared against standard **GRU** and **LSTM** on the **Selective Copy** synthetic sequence modeling task.

This project focuses on a **scaled replication** rather than an exact reproduction of the original paper. Due to hardware and runtime constraints, experiments were run under reduced settings while preserving the core structure of the task and the central comparison between minimal recurrent models and their standard counterparts.

---

## Overview

Recent work in sequence modeling has revisited recurrent neural networks by showing that simplified gated architectures can be trained in parallel and still perform competitively on long-range tasks. In *Were RNNs All We Needed?*, the authors propose **minGRU** and **minLSTM**, minimal variants of GRU and LSTM obtained by removing hidden-state dependence from gate computation. This makes the recurrence parallelizable during training while significantly reducing parameter count.

This repository implements a **single-notebook replication** of that idea on the **Selective Copy** task. The goal is to evaluate whether these minimal recurrent architectures retain strong performance under a controlled, hardware-constrained setting, and whether their relative behavior compared to standard GRU/LSTM is consistent with the original study.

Our experiments compare:

- **GRU**
- **LSTM**
- **minGRU**
- **minLSTM**

using a shared training setup on synthetic long-range memory tasks. We report:

- training and validation curves
- final test accuracy and loss
- parameter counts
- training time
- generalization to longer sequence lengths
- qualitative comparison with the findings of the original paper

---
## Repository Structure

```text
.
├── cs679proj_RNN_256sequencelength.ipynb  # fast development run
├── cs679proj_RNN_512sequencelength.ipynb  # 512sequencelength experiments
├── cs679proj_RNN_1024sequencelength.ipynb # Longer-sequence experiments
├── 1024sequence_output.txt                # Saved training logs for plotting
├── README.md
