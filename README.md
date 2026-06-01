# Evaluating Aerial Visual Intelligence

**data avaliable upon request**


## Sim-to-real transfer learning for fine-grained aerial tank classification

This repository contains the code accompanying the master's thesis 

<div align="center">

> "**Evaluating Aerial Visual Intelligence:** <br>
*A Sim-to-Real Study Using Synthetic, and Generative Diffusion-Augmented Deep Learning Methods*" <br>
by N. L. Sørensen & S. V. J. Olesen, <br>
University of Southern Denmark, <br>
2026.<br>

</div>
The thesis investigates whether physically generated synthetic replica imagery can substitute for or complement authentic imagery for fine-grained tank classification under authentic-data scarcity. The study trains a classifier on three tank classes (T-72, T-80, T-90) under four experimental regimes — synthetic alone, synthetic combined with diffusion-augmented imagery, authentic alone, and a hybrid of all three — and compares them on classification accuracy and robustness to common visual degradations.

### Data

The image data is not included in this repository because of size. Any and all data is available upon request. Contact nisoe24@student.sdu.dk or siole24@student.sdu.dk

### Reproducing the results

The training scripts are designed to run in Google Colab with the data and intermediate artifacts stored in Google Drive. The data-splitting scripts run locally on Windows.

### Running the pipeline

The full pipeline runs as follows:

1. **Splits.** Run the data-splitting scripts to produce the per-condition train/val/test partitions (see "Splits" folder).
2. **Diffusion.** Run the pre diffusion, then the diffusion script (see "Diffusion" folder).    
3. **Synthetic regimes.** Train the synthetic-only and synthetic-plus-diffusion models (the zero-shot evaluation scripts are included, as "...TestOnAuthentic").
5. **Authentic-only regime.** Run exploratory training, then the grid search, the aggregation script, the analysis script, the final evaluation, and the results script — in that order.
6. **Hybrid regime.** Run exploratory training, then the final evaluation and the results script.
7. **Robustness.** Run the robustness analysis script.

Each training script saves checkpoints and a JSON results log after every fold and epoch, so runs can be resumed across Colab sessions.
