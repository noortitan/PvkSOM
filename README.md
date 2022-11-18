# PvkSOM: Perovskite solar cells degradation data clustering using self-organizing map
This documentation is prepared as the workflow to accompany the following study:

**"Large data analysis of perovskite solar cell stability"**

*(Journal information and DOI to be added)*

Noor Titan Putri Hartono (1), Hans Köbler (1), Paolo Graniero (1), Mark Khenkin (1), Carolin Ulbrich (1), Antonio Abate (1)

Affiliations:

1. Helmholtz-Zentrum Berlin für Materialien und Energie GmbH, Berlin 12489, Germany

## Installation and Requirements
To install, just clone this repository and chemprop repository:

`$ git clone https://github.com/noortitan/PvkSOM.git`

`$ cd PvkSOM`

To install the required packages, create a virtual environment using Anaconda/ Miniconda (https://docs.conda.io/en/latest/miniconda.html). The optional but recommended setup on Anaconda/ Miniconda:

`$ conda env create -f environment.yml`

`$ conda activate PvkSOM`

`$ jupyter notebook`

## Workflow
The raw data (that comes in `.json` format; where each file corresponds to one degradation batch) is first converted into dataframes and saved in a pickle (`.pkl`) file on `degradation_preprocessing.ipynb` Jupyter Notebook.

Then, the dataframe `.pkl` files are loaded to `clustering_SOM.ipynb` Jupyter Notebook, where data pre-processing is performed, which involves excluding 'bad' dta, resampling, cutting down the data to 150 hours, smoothing (using Savitzky-Golay filter), and normalizing the data. At the end of the pre-processing, 2,380 data points are left, and we can start to train the dataset using self-organizing map (SOM). SOM is a popular unsupervised machine learning method for clustering data by converting the nonlinear statistical relationships of high-dimensional data into geometric relationships in low-dimensional nodes while preserving the topological structure of data, i.e. the relations between one data point and others (Kohonen, T., 1990, https://doi.org/10.1109/5.58325). The *k*-means clustering algorithm is also performed as a comparison to the SOM clustering method. 

## Authors
| |  | 
|---|---|
|**Author(s)** | Noor Titan Putri Hartono |
|**Version** | 1.0/ December 2022  |   
|**E-mail(s)**   | titan dot hartono at helmholtz-berlin dot de  |
| | |

## Attribution
This work is under an BSD 2-Clause License License. Please, acknowledge use of this work with the appropriate citation to the repository and research article.

## Citation

    @Misc{pvksom2022,
      author =   {The Perovskite SOM authors},
      title =    {PvkSOM: Perovskite solar cells degradation data clustering using self-organizing map},
      howpublished = {\url{https://github.com/noortitan/PvkSOM}},
      year = {2022}
    }