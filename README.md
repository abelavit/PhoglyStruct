# PhoglyStruct

Code Usages

The codes in this repository are in two categories. 
One is based on commercial software (Matlab), while the other on non-commercial software (Octave).

The train and test datasets used for implementing PhoglyStruct are .mat files by the names 'train' and 'test' respectively (the two features namely tau and pc are not present in train and test but in the .mat files 'original_train' and 'original_test' has all the features which can be viewed for reference). The datasets were converted to arff files to train multilayer perceptron on WEKA (arff files can be found in 'PhoglyStruct_arffs' folder). The algorithm (.m file) used for generating the test and train datasets is called 'PhoglyStruct'. These datasets were also generated for the CKSAAP_PhoglySite method containing CKSAAP features and its arff files were used to train multilayer perceptron on WEKA for comparison (arff files can be found in 'CKSAAP_arffs' folder). The algorithm (.m file) used for generating the test and train datasets is called 'CKSAAP'. The performance of test set was also obtained for Phogly-PseAAC and iPGK-PseAAC method by comparing the lysine k predictions when FASTA format of the protein sequence was uploaded to its webservers. The Phogly-PseAAC predictions of all lysine k is stored in .mat file named 'Phogly_PseAAC_Result' while for iPGK-PseAAC in 'iPGK_PseAAC_result'. Since these two methods were not implemented in our work, arff files for these methods is not generated so the result is obtained by executing the .m file named 'Phogly_PseAAC' for Phogly-PseAAC method and .m file named 'iPGK_PseAAC' for iPGK-PseAAC method that calculate performance based on predictions carried out on the respective webservers.    

Please see details on training MLP on WEKA and obtaining AUC below.
     
WEKA and AUC calculation details:

10-fold cross-validation of our method and CKSAAP_PhoglySite method is carried out using the arff files. The WEKA version 3.8.2 was used in this work. On WEKA, open file to train and on the classifier tab, choose MultilayerPerceptron under functions. The parameters of MultilayerPerceptron are kept as default. Supply the corresponding test set. Please also choose csv format for output predictions under 'more options'. After training is complete, use the confusion matrix to calculate the performance metrics sensitivity, specificity, G-Mean, accuracy, mcc and F-Measure (the excel file named 'MLP WEKA metric calculator' can be used for calculation). For calculating AUC, copy and paste the predictions on test set into a txt file (the predictions on test set are provided for PhoglyStruct method and CKSAAP_PhoglySite method by the names 'AUC_Data_PhoglyStruct' and 'AUC_Data_CKSAAP' respectively). To calculate the AUC, please execute the .R file named 'Calculating_AUC'. 

Footnotes:

To find in detail the CKSAAP_PhoglySite feature extraction method for each lysine k, please see the .m file named ‘CKSAAP_Preprocessing’. After the code execution, features are saved in the Final_Data variable. Final_Data is the same file used when comparing for the CKSAAP_PhoglySite method.

To verify the algorithm for calculating the CKSAAP features, code named 'CKSAAP_Preprocessing_Xu_Dataset' was developed to run on Xu's Dataset and the feature rank achieved by this alogorithm was compared to the rank achieved in CKSAAP_PhoglySite work and they come to the same ranking. The rank achieved by CKSAAP_PhoglySite method is highlighted in table 3 of their paper.  

The file also contains FASTA format of the phosphoglycerylation dataset which was used to obtained the predictions of all lysine k from the Phogly–PseAAC webserver accessible at http://app.aporc.org/Phogly-PseAAC/ and iPGK-PseAAC webserver accessible at http://app.aporc.org/iPGK-PseAAC/
