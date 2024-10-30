# README 

## Getting Started

This Github repository contains code and data to reproduce the results in our paper, "Human Expertise in Algorithmic Prediction".

The two main entry points are chest_xray.R and visual_prediction.R. These self-contained scripts will reproduce the experiments related to chest x-ray classification (adapted from [2]) and the escape the room visual prediction task (adapted from [3]), respectively. These experiments are described in Section 5 of our submission, with additional results presented in Appendix G and Appendix I. 

## Details

Each file is self-contained, and assumes the working directory is set to the root of this repository. All experiments can be run in 10-20 minutes on a standard personal laptop; most of the runtime is dedicated to producing bootstrap confidence intervals, and can be improved by reducing the number of bootstrap replicates. The number of replicates is a hyperparameter at the top of both code files. Upon completion, both files produce all the figures in our manuscript and save them to the ./plots/ directory.

The x-ray classification task relies on data (released with [1]) which is available in ./xray-data/. The visual prediction task relies on data (released with [3]) which is available in ./visual-prediction-data/.

The visual prediction task also relies on the predictions of the LSboost algorithm; code to produce these predictions is available in mcboosting.ipynb, and the predictions themselves are stored in mc_predictions.csv. This notebook is adapted from code which was released with [4]. 

helpers.R contains helper functions which are called in chest_xray.R and visual_prediction.R. LSboost.py and helper_functions.py contain helper functions for the mcboosting.ipynb notebook.

## Data Licensing

We use data for the x-ray classification task [1] which is freely available online under a CC-BY-SA license. We use data for the visual prediction task [3] which is freely available online under a CC0 1.0 license.

## Libraries

The R scripts depend on the following libraries:

library(tidyverse)  
library(glue)  
library(data.table)  
library(cluster)  
library(Cairo)  
library(boot)  
library(mltools)  

The python notebook depends on the following libraries

pip install scikit-learn  
pip install tqdm  
pip install pandas  
pip install seaborn  
pip install folktables  

## References

[1] Irvin, J., Rajpurkar, P., Ko, M., Yu, Y., Ciurea-Ilcus, S., Chute, C., ... Ng, A. Y. (2019). CheXpert: A Large Chest Radiograph Dataset with Uncertainty Labels and Expert Comparison.

[2] Rajpurkar, P., Joshi, A., Pareek, A., Ng, A. Y., & Lungren, M. P. (2021). CheXternal: Generalization of Deep Learning Models for Chest X-ray Interpretation to Photos of Chest X-rays and External Clinical Settings.

[3] Saveski, M., Awad, E., Rahwan, I., & Cebrian, M. (2021). Algorithmic and human prediction of success in human collaboration from visual features. Scientific Reports, 11, 2756.

[4] Globus-Harris, I., Harrison, D., Kearns, M., Roth, A., & Sorrell, J. (2023). Multicalibration as Boosting for Regression.

## Citation

If you find this work useful, please cite our paper:

@inproceedings{alur2024heap,  
    Author = {Rohan Alur and Manish Raghavan and Devavrat Shah},  
    Title = {Human Expertise in Algorithmic Prediction},  
    Year = {2024},  
    booktitle={Advances in Neural Information Processing Systems},  
    volume={38}  
}

