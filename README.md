# PhoglyStruct

Code Usages

The codes in this repository are in two categories. 
One is based on commercial software (Matlab), while the other on non-commercial software (Octave).
In both the categories, one has the option to either train multilayer preceptron on WEKA based on train and test data used for implementing the PhoglyStruct classifier or generate a new set of train and test dataset and carry out the training process of multilayer preceptron on WEKA. Checking the performance of other methods (CKSAAP_PhoglySite and Phogly-PseAAC) against the same test set is available in both the options.

1. Commercial software (Matlab)

Option 1: Same train and test sets as PhoglyStruct classifier

The train and test datasets used for implementing PhoglyStruct are .mat files by the names 'train' and 'test' respectively. The datasets were converted to arff files to train multilayer perceptron on WEKA (arff files can be found in 'PhoglyStruct_arffs' folder). These datasets were also generated for the CKSAAP_PhoglySite method containing CKSAAP features and its arff files were used to train multilayer perceptron on WEKA for comparison (arff files can be found in 'CKSAAP_arffs' folder). The performance of test set was also obtained for Phogly_PseAAC method by comparing the lysine k predictions when FASTA format of the protein sequence was uploaded to its webserver. The Phogly_PseAAC predictions of all lysine k is stored in .mat file named 'Phogly_PseAAC_Result'. Since Phogly_PseAAC method was not implemented in our work, arff files for this method is not generated so the result is obtained by executing the .m file named 'Phogly_PseAAC'.    

Please see details on training MLP on WEKA and obtaining AUC at the end of this document.
 
Option 2: Different train and test sets as PhoglyStruct classifier

Please run the .m file named 'New_Test_and_Train'. This will generate new arff files for train and test dataset. Next, execute the .m file named 'CKSAAP'. The arff files generated by the two methods (our method and CKSAAP_PhoglySite method) are then used to train the MLP on WEKA. Finally, the same newly generated test dataset is compared against the Phogly_PseAAC method. To carry this out, please execute the .m file named 'Phogly_PseAAC_2'.

Please see details on training MLP on WEKA and obtaining AUC at the end of this document.
     

2. Non-commercial software (Octave)

Option 1: Same train and test sets as PhoglyStruct classifier
 
Option 2: Different train and test sets as PhoglyStruct classifier

WEKA details:

10-fold cross-validation of our method and CKSAAP_PhoglySite method is carried out using the arff files. The WEKA version 3.8.2 was used in this work. On WEKA, open file to train and on the classifier tab, choose MultilayerPerceptron under functions. Supply the corresponding test set. Please also choose csv format for output predictions under 'more options'. Use the confusion matrix to calculate the performance metrics sensitivity, specificity, precision, accuracy and mcc. For calculating AUC, copy and paste the predictions on test set into a txt file. To calculate the AUC, please execute the .R file named 'Calulating_AUC'.    
