# MGCVAE_Multi-objective_Optimization

## Fork Information

This is a fork of the original [MGCVAE project](https://github.com/mhlee216/MGCVAE), improved by [LHH90538](https://github.com/LHH90538) with the following enhancements:

- Added `requirements.txt` file for easy dependency management
- Fixed command errors in the original project
- Improved project documentation and setup instructions

## Original Project

<img src="https://github.com/mhlee216/MGCVAE/blob/main/main.png">

#### MGCVAE: Multi-Objective Inverse Design via Molecular Graph Conditional Variational Autoencoder

<a href="https://doi.org/10.1021/acs.jcim.2c00487">https://doi.org/10.1021/acs.jcim.2c00487</a>

Myeonghun Lee<sup>+</sup>, Kyoungmin Min\*

Journal of Chemical Information and Modeling

## Installation

First, install the required dependencies:

```bash
pip install -r requirements.txt
```

**Note:** RDKit may require installation via conda:
```bash
conda install -c conda-forge rdkit
```

## Usage

### Step 1: Navigate to the code directory

```
cd ./code/
```

### Step 2: Run the MGCVAE model

#### Example 1: Quick test with small dataset
```
python mgcvae.py --dataset ../data/ZINC_logP_MR_sample.csv --data 10000 --size 10 --epochs 200 --gen 5000
```

**Parameters explanation:**
- `--dataset`: Path to the dataset file (default: `../data/ZINC_logP_MR.csv`)
- `--data`: Number of samples to use for training (default: 80000)
- `--size`: Maximum molecule size (default: 10)
- `--epochs`: Number of training epochs (default: 1000)
- `--gen`: Number of molecules to generate (default: 10000)

#### Example 2: Full training with large dataset
```
python mgcvae.py --data 1363452 --size 16 --gen 10000
```

**Parameters explanation:**
- `--data 1363452`: Use all available data samples
- `--size 16`: Set maximum molecule size to 16 atoms
- `--gen 10000`: Generate 10,000 molecules

### Additional Parameters

You can also customize other parameters:

- `--batch`: Batch size for training (default: 100)
- `--test`: Test set ratio (default: 0.1)
- `--lr`: Learning rate (default: 0.00005)
- `--output`: Output path for generated molecules (default: `../results/generated`)
- `--conditions`: Path to conditions file (default: `../data/conditions.csv`)


