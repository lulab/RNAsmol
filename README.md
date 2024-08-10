# RNAsmol

[![python
\>3.7.16](https://img.shields.io/badge/python-3.7.16-brightgreen)](https://www.python.org/)

RNA-targeting drug discovery is undergoing an unprecedented revolution.
Despite recent advances in this field, developing data-driven deep
learning models remains challenging due to the limited availability of
validated RNA-small molecule interactions and the scarcity of known RNA
structures. In this context, we introduce RNAsmol, a novel
sequence-based deep learning framework that incorporates data
perturbation with augmentation, graph-based molecular feature
representation and attention-based feature fusion modules to predict
RNA-small molecule interactions.

## Datasets

RNAsmol was trained on

| dataset | #RNA targets | #small molecules | #interactions |
|---------|--------------|------------------|---------------|
| PDB     | 271          | 151              | 425           |
| ROBIN   | 27           | 2003             | 3742          |

## Installation

### RNAsmol environment

Download the repository and create the evironment for RNAsmol. It may take around 2 hours for setting all required packages.

Key requirements: rdkit, torch-geometric

``` bash
#Clone the RNAsmol repository from GitHub
git clone https://github.com/lulab/RNAsmol.git
cd ./RNAsmol
#Install the required dependencies
conda env create -n rnasmol -f RNAsmol.yml
```

## Usage

You should have at least an NVIDIA GPU and a driver on your system to run the training or inference.
In general, it will take 1-2 hours for the data preprocessing and model training

### 1.Activate the created conda environment

`source activate rnasmol`

### 2.Data preprocessing

```         
python src/preprocess.py pdb/rnaperturbation  
```

### 3.Model training

```         
python src/train.py --dataset pdb/rnaperturbation  --lr 5e-5 --batch_size 1024 --save_model
```

### 4.Model test

``` text
python src/test.py --dataset pdb/rnaperturbation  --model_path 'save/*.pt'
```

## License and Disclaimer

This tool is for research purpose and not approved for clinical use. The
tool shall not be used for commercial purposes without permission.

