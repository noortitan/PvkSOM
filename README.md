# PvkSOM: Perovskite solar cells degradation data clustering using self-organizing map
This documentation is prepared as the workflow to accompany the following study:

**"Stability follows efficiency based on the analysis of a large perovskite solar cells ageing dataset"**

*Nat Commun 14, 4869 (2023) https://doi.org/10.1038/s41467-023-40585-3*

Noor Titan Putri Hartono (1), Hans Köbler (1), Paolo Graniero (1,2), Mark Khenkin (1), Rutger Schlatmann (1), Carolin Ulbrich (1), Antonio Abate (1)

Affiliations:

1. Helmholtz-Zentrum-Berlin für Materialien und Energie, 14109 Berlin, Germany
2. Department of Business Informatics, Freie Universität Berlin, 14195 Berlin, Germany

## Installation and Requirements
To install, just clone this repository:

`$ git clone https://github.com/noortitan/PvkSOM.git`

`$ cd PvkSOM`

To install the required packages, create a virtual environment using Anaconda/ Miniconda (https://docs.conda.io/en/latest/miniconda.html). The optional but recommended setup on Anaconda/ Miniconda:

`$ conda env create -f environment.yml`

`$ conda activate PvkSOM`

`$ jupyter notebook`

## Workflow

The processed data in `.pkl` format is available on Zenodo (https://doi.org/10.5281/zenodo.8185882), along with the dataset in this repository (`PCE_df_grouping.csv`).

**Use `20230816_degradation_analysis_revision_11_cleaned.ipynb` Jupyter Notebook with this data.** This notebook loads the `.pkl` and `.csv` files, further pre-processing me (including smoothing (using Savitzky-Golay filter), and normalizing the data). At the end of the pre-processing, 2,245 data points are left, and we can start to train the dataset using self-organizing map (SOM). SOM is a popular unsupervised machine learning method for clustering data by converting the nonlinear statistical relationships of high-dimensional data into geometric relationships in low-dimensional nodes while preserving the topological structure of data, i.e. the relations between one data point and others (Kohonen, T., 1990, https://doi.org/10.1109/5.58325). The *k*-means clustering algorithm is also performed as a comparison to the SOM clustering method. 

**The other Jupyter Notebooks (which can't be run),** `20221122_degradation_preprocessing_2.ipynb` and `20230227_degradation_analysis_revision_10_cleaned.ipynb`, are meant to demonstrate how the initial raw data is generated from the High-Throughput Ageing Test setup is first processed. The raw data (that comes in `.json` format; where each file corresponds to one degradation batch) is first converted into dataframes and saved in a pickle (`.pkl`) file on `20221122_degradation_preprocessing_2.ipynb` Jupyter Notebook. Then, the dataframe `.pkl` files are loaded to `20230227_degradation_analysis_revision_10_cleaned.ipynb` Jupyter Notebook, where data pre-processing is performed, which involves excluding 'bad' data, resampling, cutting down the data to 150 hours, smoothing (using Savitzky-Golay filter), and normalizing the data. After that, the subsequent steps are similar to the `20230816_degradation_analysis_revision_11_cleaned.ipynb` Jupyter Notebook.

## Authors
| |  | 
|---|---|
|**Author(s)** | Noor Titan Putri Hartono |
|**Version** | 1.1/ August 2023  |   
|**E-mail(s)**   | titan dot hartono at helmholtz-berlin dot de  |
| | |

## Attribution
This work is under an BSD 2-Clause License License. Please, acknowledge use of this work with the appropriate citation to the repository and research article.

## Citation

    @software{noortitan_2023_8181602,
      author       = {noortitan},
      title        = {noortitan/PvkSOM: First Release},
      month        = jul,
      year         = 2023,
      publisher    = {Zenodo},
      version      = {v1.0},
      doi          = {10.5281/zenodo.8181602},
      url          = {\url{https://doi.org/10.5281/zenodo.8181602}}
    }
