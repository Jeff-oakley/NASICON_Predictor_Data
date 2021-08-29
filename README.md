# NASICON stability predictor
This is the repo that host data and codes for NASICON stability predictor.

Whenever you have used the data here for publication or other purposes, please consider citing the following paper:

B. Ouyang, J. Wang, T. He, C. J. Bartel, H. Huo, Y. Wang, V. Lacivita, H. Kim and G. Ceder, Synthetic accessibility and stability rules of NASICONs, arXiv, 2021.

## Raw data
* All the raw data for machine learning are stored in the folder ./RawData
* `KeyFeatureNames.txt`: Name of basic features used for SIS procedure (see details in [SI](https://arxiv.org/abs/2102.03627)) (to be uploaded?).
* `exp_comps.json`: Composition of experimentally synthesized materials in [Fig. 5b](https://arxiv.org/abs/2102.03627).
*  `train.csv`/`test.csv`: values of E<sub>hull</sub> and all basic features of 80-20 split train/test data for model selection. The optimal 2D SIS features is selected from ??? SIS+MLR models based on these data. 
* `train_2D.csv`/`test_2D.csv`: values of E<sub>hull</sub> and the optimal 2D SIS features of train/test data in train.csv/test.csv.
* `train_X_fold[1-5].dat`/`test_X_fold[1-5].dat`: values of 2D SIS features of train/test data for the five-fold cross-validation to evaluate the final model.
* `train_Y_fold[1-5].dat`/`test_Y_fold[1-5].dat`: 0/1 encodings of synthesizability of train/test data for the five-fold cross-validation to evaluate the final model.

## Scripts for reproducing results in our paper
* The scripts for reproducing the machine learning model, metrics and all figures in our manuscript are displayed in ./Script folder
* `Run_preprocess_feature_transformation.ipynb`: preprocess data by transforming basic features to 2D SIS features. 
* `Run_Ranked_SVM.ipynb`: train ranked SVM model to predict ranking of synthesizability (E<sub>hull</sub> values).
* `Run_five_fold_CV.ipynb`: train five-fold cross-validation to evaluate the effectiveness of a linear decision boundary to separate synthetically accessible/non-accessible NASICON compositions.

## Compatibility map
* The interactive compatibilty map corresponding to [Fig. 2a](https://arxiv.org/abs/2102.03627) can be found as a static webpage "Stability.html". The raw data (i.e. Ehull values) can be found as ./RawData/test_2D.csv and ./RawData/train_2D.csv

## Figures
* The folder that contains high resolution figures generated from the machine learning model in [our manuscript](https://arxiv.org/abs/2102.03627).

