# APTOS-Blindness-Detection

This Competition was hosted by Asia Pacific Tele-Ophthalmology Society (APTOS). The goal of this competition was to detect different stages of _Diabetic Retinopathy_ from a large set of retina images taken using _fundus photography_ under a variety of imaging conditions. The severity of this condition was classified into 5 categories:

* 0 - No DR
* 1 - Mild
* 2 - Moderate
* 3 - Severe
* 4 - Proliferative DR

Submission scores were based on Quadratic Weighted Kappa.

## Hypotheses, Approaches and Experiments

### Task definition
This competition can be considered a classification as well as a regression problem. As there are distinct classes of images in the set, it could be seen as a classification task. On the other hand, the labels represented the severity of the _diabetic retinopathy_, turning it into an ordinal regression problem. We explored both of these hypotheses.

### Architectures

* Densenet 201
* Renet 101
* Efficientnet B4

### Approaches

* Classification with BCEWithLogitsLoss
* Classification with FocalLoss with CrossEntropy
* Ordinal Regression
* Huber Regression

## EDA
After some EDA on the dataset it was apparent that some image pre-processing was needed. The images were taken in different light conditions, with some of them too dark to use in neural models directly. Additionally, images in the dataset were also of irregular sizes.
