# gwas

The main objective of this project is to develop a parallel distributed computational pipeline that uses maxT permutation testing to determine which genomic variants are implicated in a disease.

---
## Contents
- Pre-requisites
- Installation
- Usage
---
## Pre-requisites

> We assume that your are working on a linux/unix  system.

To get started ensure that you have the following tools installed in a directory accessible by your  `$PATH` variable. We particularly recommend adding them to the `$HOME/bin` directory and adding this directory to your path variable.

- [nextflow](https://www.nextflow.io/docs/latest/getstarted.html#installation)
- [plink](http://zzz.bwh.harvard.edu/plink/download.shtml )
-[anaconda](https://docs.conda.io/en/latest/miniconda.html#linux-installers)

## Installation

To install the gwas project, clone this git repository and make the gwas folder your working directory.

```bash
git clone https://github.com/Andisani96/gwas.git
cd gwas/
```

Inside the folder, there is an environment.yml file which contains the dependencies for a python environment. Create the environment  and activate it.

```bash
conda env create -f environment.yml
conda activate gwas
```

## Usage

>You can select the number of permutations you wish to use by adding the `--mperm ` argument.

To run the pipeline on your local machine with 10 permutations use the following command:
```bash
nextflow run pipeline.nf -profile standard --mperm 10
```

To run the pipeline in a cluster with the slurm job scheduler for 10 permutations use the following:

```bash
nextflow run pipeline.nf  -profile slurm --mperm 10
```

The pipeline data is found in the inputs folder and the outputs are found in the outputs folder.
- In the outputs folder, the results are stored in directories that are numbered by the number of permutations you have selected.

- To change or assign your own inputs, edit the `param.input_pat` variable in the nextflow.config file.
