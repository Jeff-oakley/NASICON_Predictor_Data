# NASICON stability predictor

In our work of [NASICON stability predictor](https://arxiv.org/abs/2102.03627), we used SIS+MLR to identify the best feature for predicting NASICON stabilities from the set of millions of candidate features. This repo hosts necessary data and codes for computing the best feature and reproducing the machine-learning parts of our work.

## Compatibility map

To display the stabilities of NASICON compounds, we created an interactive compatibilty map in [Stability.html](Stability.html) ([Fig. 2a](https://arxiv.org/abs/2102.03627)). 

The raw data (i.e. Ehull values) of this interactive map can be found in `./RawData/test_2D.csv` and `./RawData/train_2D.csv`.


## Data files

All the raw data/processed datasets for machine learning are stored in the folder `./RawData`.

#### Input data files

* `KeyFeatureNames.txt`: Name of basic features used for SIS procedure (see details in [SI](https://arxiv.org/abs/2102.03627)) (will link to SI on publisher's website when available).
* `exp_comps.json`: Composition of experimentally synthesized materials in [Fig. 5b](https://arxiv.org/abs/2102.03627).

#### ML-related datasets

*  `train.csv`/`test.csv`: values of E<sub>hull</sub> and all basic features of 80-20 split train/test data for model selection. The optimal 2D SIS features is selected from ??? SIS+MLR models based on these data. 
* `train_2D.csv`/`test_2D.csv`: values of E<sub>hull</sub> and the optimal 2D SIS features of train/test data in train.csv/test.csv.
* `train_X_fold[1-5].dat`/`test_X_fold[1-5].dat`: values of 2D SIS features of train/test data for the five-fold cross-validation to evaluate the final model.
* `train_Y_fold[1-5].dat`/`test_Y_fold[1-5].dat`: 0/1 encodings of synthesizability of train/test data for the five-fold cross-validation to evaluate the final model.

## Scripts for reproducing results in our paper

The scripts for reproducing the machine learning model, metrics and all figures in our manuscript can be found in ./Script folder

* `Run_preprocess_feature_transformation.ipynb`: preprocess data by transforming basic features to 2D SIS features. 
* `Run_Ranked_SVM.ipynb`: train ranked SVM model to predict ranking of synthesizability (E<sub>hull</sub> values).
* `Run_five_fold_CV.ipynb`: train five-fold cross-validation to evaluate the effectiveness of a linear decision boundary to separate synthetically accessible/non-accessible NASICON compositions.

#### Figures

All high-resolution figures in [our manuscript](https://arxiv.org/abs/2102.03627) can be found in folder [Figures](Figures/).

## Citing

If you find this repo useful in your own projects, please consider citing our paper:

```
@article{ouyang2021synthetic,
  title={Synthetic accessibility and stability rules of NASICONs},
  author={Ouyang, Bin and Wang, Jingyang and He, Tanjin and Bartel, Christopher J and Huo, Haoyan and Wang, Yan and Lacivita, Valentina and Kim, Haegyeom and Ceder, Gerbrand},
  journal={arXiv preprint arXiv:2102.03627},
  year={2021}
}
```