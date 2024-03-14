# Windows-PE-Adversarial-Attacks
### The repository contains code referred to the work:  
# Evaluating Realistic Adversarial Attacks against Machine Learning Models for Windows PE Malware Detection [under review] 
### Installation  
The dataset consists of harmful malware binary files, I suggest installing a virtual machine to replicate the experiments. To replicate the experiments, install the following packages.  

* python 3.6.13
* keras 2.6
* tensorflow 2.6.2
* scikit learn 0.24.2
* pandas 1.1.5
* numpy 1.19.5
* lief 0.9.0
* joblib 1.1.1
* lightgbm 4.1.0
* tqdm 4.64.1
* jupyter notebook 6.4.3
* secml_malware 0.2.4.1 (https://github.com/pralab/secml_malware)](https://github.com/pralab/secml_malware))
* ember 0.1.0 (https://github.com/elastic/ember/tree/master)https://github.com/elastic/ember/tree/master/)
* SHAP 0.41.4
### Description for this repository
To replicate the experiments of the referred work, the models and datasets have been saved in [Dataset and model](https://unibari-my.sharepoint.com/:f:/g/personal/muhammad_imran_uniba_it/Ev6oqwqm6sBEmXrl8sHx--0BbZNdJyQwYYoAn2yHcXWnYg?e=vmTrXP). **Please manage data carefully, by using a virtual machine, as the are  Windows PE malware** Parameters are saved in config.ini. First download the dataset and placed them in the relevant folder then run the notebook in the given order:
1. Run predicted_malware notebook to find the malware binary files that are predicted as malware by a pre-trained MalConv model.
2. Run adversarial_samples_generation notebook to generate Windows PE malware by attacking MalConv with the attack method: FullDOS, Extend_dos, Conetnt_shift, FGSM(padding+slack), and GAMMA. This step is optional as Windows PE malware files by each attacking method are included in the dataset. To skip this step, place these files into the folders by following the configuration in config.ini. 
3. Run malconv_evasion_performnce notebook to achieve Table 1, Table 2, and Figure 1 results against the MalConv model.
4. Run lightGBM_eval notebook to achieve Table 1, Table 2, and Figure 1 results against the lightgbm model.
5. Run corresponding_malware notebook to find the corresponding PE malware of the realistic adversarial PE malware.
6. Run gamma_subset notebook to find the gamma adversarial PE malware and its corresponding, that achieved transferability against lightgbm.
7. Run feature_extraction notebook to extract features from all PE adversarial malware and corresponding malware.
8. Run euclidean_distance notebook to achieve Figure 2 results in section 5.3
9. Run gamma_subset_euclidean_distance notebook to achieve Figure 3 results in section 5.3
10. Run XAI_beeswarm notebook to achieve Figure 4-8 results in section 5.4
11. Run Adversarial_training notebook to achieve Table 3 results in section 5.5
12. Run XAI_CV_beeswarm notebook to achieve Figure 9 results in section 5.5
## Acknowledgement
To generate realistic adversarial Windows PE malware by attacking MalConv with the attack methods: FullDOS, Extend_DOS, Content_Shift, FGSM(padding+slack), and GAMMA this work uses code from GitHub repository secml_malware (https://github.com/pralab/secml_malware)](https://github.com/pralab/secml_malware)).
To extract features from Windows PE malware, this work uses code from GitHub ember (https://github.com/elastic/ember/tree/master)https://github.com/elastic/ember/tree/master/).






