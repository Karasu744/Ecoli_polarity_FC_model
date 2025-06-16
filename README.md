# *E.coli* Polarity Recognition using Fully Connected Model

This repository contains the code and notebooks used for training and testing a fully connected (FC) neural network model to recognize polarity in *E.coli* cells. The analysis supports the findings reported in the scientific manuscript:

**"Construction and Phenotypic Classification of Synthetic Dual-Pole *Escherichia coli* Cells"**, submitted to *Communications Biology*.

## Repository Contents

- `train_fc_model.ipynb` — Jupyter Notebook for training the FC model on polarity-labeled data.
- `test_fc_model.ipynb` — Jupyter Notebook for evaluating the trained model and performing polarity classification on test samples.

## Environment and Dependencies

- Python 3.8 or higher
- Jupyter Notebook
- PyTorch 1.13.1
- torchvision 0.14.1
- numpy
- matplotlib
- scikit-learn

Install dependencies via:

```bash
pip install torch torchvision numpy matplotlib scikit-learn
```

## Software Requirements

### Oufti

This project relies on `.mat` files derived from microscopy data processed by **Oufti**, an open-source software for single-cell analysis of bacterial images.

- Oufti enables extraction of single-cell information (e.g., cell meshes and fluorescence intensities).
- A minimal MATLAB runtime is bundled with Oufti.
- Download: [https://oufti.org/download/register.php](https://oufti.org/download/register.php)
- Tutorials: [https://oufti.org/tutorial.htm](https://oufti.org/tutorial.htm)

## Execution Environment

### Google Colab

All notebooks in this repository were developed and tested using [Google Colab](https://colab.research.google.com/), a cloud-based platform for running Python notebooks with GPU support. Users can run the notebooks directly on Colab without needing to install any software locally.

## Raw Data Acquisition Workflow

To ensure correct data extraction and polarity analysis, follow the steps below when preparing raw `.mat` data with Oufti:

1. **Load phase contrast images** into Oufti as **channel 0**.  
2. **Load fluorescence images** for a unipolar marker (e.g., **PopZ-mRFP**) as **channel 1**.  
3. **Load fluorescence images** for the test protein (e.g., **sfGFP-PodJ**) as **channel 2**.

Once all image channels are loaded:

- Use Oufti to detect and isolate single cells (manually or automatically).
- A structured array will be created for each cell, storing geometry and signal data.
- Apply the **reuse mesh** function to align fluorescence signals to cell shapes and extract intensity features.

See detailed guidance in the Oufti application instructions:  
[https://oufti.org/application.htm](https://oufti.org/application.htm)

## Code Availability

This repository is publicly available at:  
**GitHub**: [https://github.com/Karasu744/Ecoli_polarity_FC_model](https://github.com/Karasu744/Ecoli_polarity_FC_model)  
**DOI (via Zenodo)**: [https://doi.org/10.5281/zenodo.15676584](https://doi.org/10.5281/zenodo.15676584)


