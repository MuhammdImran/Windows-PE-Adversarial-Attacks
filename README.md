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
To replicate the experiments of the referred work, the models and datasets have been saved in [Dataset and model](https://unibari-my.sharepoint.com/:f:/g/personal/muhammad_imran_uniba_it/Ev6oqwqm6sBEmXrl8sHx--0BbZNdJyQwYYoAn2yHcXWnYg?e=fKyZ8f). 
For more detailed information about each malware sample, including the specific malware family to which each file belongs, please visit [Malware Family](https://unibari-my.sharepoint.com/:x:/g/personal/muhammad_imran_uniba_it/EVDHYTtz9rJEjFWSfbDlxI8BAPJkopNUffevM71T8qNOfQ?e=p1zHAc)
To provide a visual understanding of the distribution of malware families in the dataset, a pie chart is available [Pie chart](https://unibari-my.sharepoint.com/:i:/g/personal/muhammad_imran_uniba_it/Ee3BHpjWRpJIvgQuGqz__coBZ4m6W-L0KR8LSkVJUMeszA?e=BjQdsf).
**Please manage data carefully, by using a virtual machine, as the are  Windows PE malware**. Parameters are saved in config.ini. First, download the datasets and place them in the relevant folders. Subsequently, run the notebooks in the following order:
1. Run predicted_malware notebook to find the malware binary files that are predicted as malware by a pre-trained MalConv model.
2. Run adversarial_samples_generation notebook to generate Windows PE malware by attacking MalConv with the attack methods: FullDOS, Extend_dos, Conetnt_shift, FGSM(padding+slack), and GAMMA. This step is optional as the Windows PE malware files produced by each attacking method are already included in the datasets. To skip this step, place these files into the folders by following the configuration in config.ini. 
3. Run malconv_evasion_performnce notebook to achieve results reported in Table 1, Table 2, and Figure 1 on the performance of the MalConv model.
4. Run lightGBM_eval notebook to achieve results reported in Table 1, Table 2, and Figure 1 on the performance of the lightGBM model.
5. Run corresponding_malware notebook to find the corresponding PE malware of the realistic adversarial PE malware.
6. Run gamma_subset notebook to find which adversarial PE files produced by GAMMA evade the lighGBM model.
7. Run feature_extraction notebook to extract LIEF features from all PE adversarial malware and corresponding original files.
8. Run euclidean_distance notebook to achieve the results shown in Figure 2 of section 5.3.
9. Run gamma_subset_euclidean_distance notebook to achieve the results shown in Figure 3 of section 5.3.
10. Run XAI_beeswarm notebook to achieve Figure 4-8 results in section 5.4.
11. Run Adversarial_training notebook to achieve Table 3 results in section 5.5.
12. Run XAI_CV_beeswarm notebook to achieve Figure 9 results in section 5.5.
## Credits and Acknowledgement
To generate the realistic adversarial Windows PE malware by attacking MalConv with the attack methods: FullDOS, Extend_DOS, Content_Shift, FGSM(padding+slack), and GAMMA this work uses code from GitHub repository secml_malware (https://github.com/pralab/secml_malware)](https://github.com/pralab/secml_malware)).

To extract features from Windows PE malware and their adversarial counterparts and to train lightGBM model this work uses code from GitHub ember (https://github.com/elastic/ember/tree/master)https://github.com/elastic/ember/tree/master/).

The malware Windows PE files are collected from VirusShare (https://virusshare.com/about).  

The goodware Windows PE files are collected from (https://practicalsecurityanalytics.com/pe-malware-machine-learning-dataset/).

The malware_categories_percentage.doc File contains information about malware categories and the number of files in each category. Figure Windows_PE_malware_types_percentage.png is a Pie chart showing the percentage of each malware category.


**Note: The extension has been removed from all the files in the samples directory to prevent accidental execution.**






