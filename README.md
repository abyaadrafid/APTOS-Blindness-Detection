# APTOS-Blindness-Detection

This Competition was hosted by Asia Pacific Tele-Ophthalmology Society (APTOS). The goal of this competition was to detect different stages of _Diabetic Retinopathy_ from a large set of retina images taken using _fundus photography_ under a variety of imaging conditions. The severity of this condition was classified into 5 categories:

* 0 - No DR
* 1 - Mild
* 2 - Moderate
* 3 - Severe
* 4 - Proliferative DR

Submission scores were based on Quadratic Weighted Kappa.

## Hypotheses and Approaches

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
* ArcFace 

## EDA
After some EDA on the dataset it was apparent that some image pre-processing was needed. Our major takeaways were following :

* Images were taken in different light conditions.
* Images of different classes had different sizes and aspect ratios.
* The data set was imbalanced.

We came up with approaches to normalize the dataset for better performance.

## Pre-processing and Augmentations 
### Image Pre-processing
While preprocessing the image, we needed to keep our findings from our EDA in mind. We decided to apply following pre-processing steps :

* Crop out black borders
* Center image
* Circular crop around image center
* Resized to 224\*224
### Image Augmentations
Following data augmentations were applied to generalize the data :

* Vertical Flip
* Horizontal Flip
* Full 360 degrees rotation
* Lighting

### External Data
We found that there was another competition dataset for _diabetic retinopathy_ with similar label hierarchy. We included this data with our exiting data to make our model more robust.

## Experiments
### Classification with BCEWithLogitsLoss


### Classification with FocalLoss on CrossEntropyLoss
As the competition dataset is quite imbalanced, overfitting on majority classes was a big hurdle. To combat this, we decided to use [focalloss](https://arxiv.org/abs/1708.02002). 
### Ordinal Regression
### Huber Regression
### ArcFace
