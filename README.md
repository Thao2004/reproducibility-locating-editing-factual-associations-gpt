# Reproducibility: Locating and Editing Factual Associations in GPT

## Paper

Locating and Editing Factual Associations in GPT  
Meng et al., NeurIPS 2022  
https://rome.baulab.info

## Overview

This repository contains our reproducibility study and three extensions of the ROME paper.

## Requirements

- Google Colab Pro  
- A100 GPU (High-RAM runtime required for GPT-J experiments)
- No local installation required (all dependencies installed in notebooks)

## Quick Start

1. Open a notebook in Google Colab  
2. Enable GPU runtime  
3. Run all cells from top to bottom  

All dependencies and the original ROME repository are automatically installed.

## How to Run

### Main reproduction

Reproduces ROME results on GPT-2 XL using a subset of the zsRE dataset  
Open [notebooks/rome_reproducibility_gpt_xl.ipynb](notebooks/rome_reproducibility_gpt_xl.ipynb)

### Extension 1: ROME on GPT-J

Evaluates whether ROME generalizes to a larger model (GPT-J 6B) on the zsRE dataset
Open [notebooks/extension_1_gpt_j.ipynb](notebooks/extension_1_gpt_j.ipynb) (Requires A100 GPU with High-RAM runtime)

### Extension 2: Sequential edit degradation

Tests the robustness of ROME under multiple sequential edits and measures interference effects  
Open [notebooks/extension_2_sequential_edits.ipynb](notebooks/extension_2_sequential_edits.ipynb)

### Extension 3: Extreme paraphrase generalization

Tests whether ROME edits remain reliable when the same factual association is expressed through more difficult prompt transformations. In addition to the original prompt and standard paraphrases, this extension evaluates passive, question, negation, and indirect prompt forms.

Open [notebooks/extension_3_extremeParaphrase.ipynb](notebooks/extension_3_extreme_Paraphrase.ipynb)
  
## Results

All experiment outputs are stored in the `results/` folder:

- `gpt2-xl/`: Reproducibility results (zsRE dataset)
- `extension_1/`: GPT-J experiments
- `extension_2/`: Sequential editing experiments
- `extension_3/`: Extreme paraphrase generalization experiments

Each folder contains:

- `raw/`: Per-sample outputs  
- `summary/`: Aggregated metrics  

## Original Codebase

All notebooks clone the original ROME repository at runtime:  
https://github.com/kmeng01/rome

## Notes

- Some experiments may require restarting the runtime due to GPU memory limits  
- GPT-J experiments require the A100 High-RAM option due to model size and memory usage 
- Intermediate results are saved to avoid data loss  
