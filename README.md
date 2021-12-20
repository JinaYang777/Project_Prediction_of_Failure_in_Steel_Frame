# Project
STAT 451: Machine Learning at UW-Madison (Fall 2020)
# Prediction of Failures in Steel Frames

- **Intro**: As the structural failure may cause substantial loss of human life, protection against possible failure is of primary concern and the structure must neither fail locally nor globally. The objective of this paper is to predict whether steel frames experience a failure or not under uncertainties in material and geometric properties and structural loads, by evaluating the ultimate strength of the frames. Two example frames are investigated that have the same layout but different failure modes.
- Therefore, we are motivated to develop machine learning models that can quickly and accurately predict failures in Steel Frames.
- **Goal**: To find the best model to predict the failure of steel frames, k-Nearest Neighbors (kNN), decision trees, and random forests are utilized. The model with the highest prediction accuracy are selected as the best model. 

- **Tech used**: sklearn, mlxtend, pandas, numpy, matplotlib<br>

## Results

(1) Model & Algorithm Selection (5 x 2 Nested Cross-Validation) using Dataset 1
| Model Name \ Evaluation | Chosen Hyperparameter | Average Accuracy |
| :-----: |:--------:| :-----:| 
| kNN |  algorithm:auto, n_neighbors: 15, p:2|  92.80% +/- 0.28   |
| Decision Tree| criterion: entropy, max_depth: 15, min_samples_split:3 | **95.19% +/- 0.28** | 
| Random Forests| max_depth: None, min_samples_split: 3 |  **97.43% +/- 0.11** | 

(2) Comparing best models from two Algorithms

| Model Name \ Evaluation | Chosen Hyperparameter | Nested-CV ACC|Best 10-CV ACC|
| :-----: |:--------:| :-----:|:-----:|
| Decision Tree| criterion: entropy, max_depth: 15, min_samples_split:3 | 95.19% +/- 0.28 | 95.43% |
| Random Forests| max_depth: None, min_samples_split: 3 |  **97.43% +/- 0.11** | **97.54%** |


(3) Application of 3 best model on different dataset (dataset 2) 
| Model Name \ Evaluation |Best 10-CV ACC| Test ACC|
| :-----: |:--------:| :-----:|
| kNN | 97.88% | 97.95% |
| Decision Tree | 98.13% | 98.09% |
| Random Forests| 97.99% | 98.84% |

(4) Results: Dataset 1, Dataset 2
| Model | data_1 Accuracy | data_2 Accuracy |
| :-----: |:--------:| :-----:|
| kNN: algorithm:auto, n_neighbors: 15, p:2 | 93.26% | 97.95% |
| Decision Tree: criterion: entropy, max_depth: 15, min_samples_split:3 | 95.36%| 98.09% |
| Random Forests: max_depth: None, min_samples_split: 3| 97.77% | 98.84% |


## Dataset
- 50,000 finite element analyses were conducted in OpenSees with CHTC
-  Obtained load-displacement curves
-  Examples that caused convergence errors were removed
-  Normalized by dividing nominal values
-  6 random features with 2 class labels

Number of examples
|Failure|class|Frame 1|Frame 2|
| :-----: |:--------:| :-----:|:-----:|
|Failure|Class0|2424|7351|
|No Failure|Class1|47019|41978


## Files
* Code file: 451Report.ipynb
* Knitted Version of Code file: Final_Copy.pdf
* Report: STAT_451_report.pdf
* Presentation Slide: Project_Presentation.pdf
* Presentation Recording: group06.mp4
