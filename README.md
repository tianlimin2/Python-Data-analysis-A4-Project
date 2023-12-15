# Python-Data-analysis-A4-Project
## Page Blocks Classification
The problem consists of classifying all the blocks of the page layout of a document that has been detected by a segmentation process. The goal is to classify each block into one of five classes.

### Overview
Relevant Information Paragraph:<br The 5473 examples comes from 54 distinct documents.

Each observation concerns one block.

All attributes are numeric.

Data are in a format readable by C4.5.

Number of Instances: 5473.
the five classes are:
text (1)
horizontal line (2)
picture (3)
vertical line (4)
graphic (5)

Number of Attributes :
height: integer. | Height of the block.
lenght: integer. | Length of the block.
area: integer. | Area of the block (height * lenght);
eccen: continuous. | Eccentricity of the block (lenght / height);
p_black: continuous. | Percentage of black pixels within the block (blackpix / area);
p_and: continuous. | Percentage of black pixels after the application of the Run Length Smoothing Algorithm (RLSA) (blackand / area);
mean_tr: continuous. | Mean number of white-black transitions (blackpix / wb_trans);
blackpix: integer. | Total number of black pixels in the original bitmap of the block.
blackand: integer. | Total number of black pixels in the bitmap of the block after the RLSA.
wb_trans: integer. | Number of white-black transitions in the original bitmap of the block.

### Data processing
#### Data pre-processing
There was no missing value. Then datasets have been normalized (with Z-normalization).

#### Exploratory Data Analysis
Some Data Visualizations

![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/f7456a25-3ad0-4901-84b5-31df98682dcc)
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/dae7b987-9ead-48a9-8b96-adb575477deb)

![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/a55ec356-9c7e-435b-8d16-e4245bda6727)
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/fa56f31b-beb3-4134-982d-6da0b02e2ad3)
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/bab88862-b38c-4618-b0da-30219546bc2f)
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/ce5bf3d6-bff7-441b-bd6e-26aad1b76632)

### Modeling analysis

#### Use logistic regression to build a baseline model
The dataset involves continuous and integer features, and the goal is classification.
For binary classification problems, this is a good starting point because it is simple and easy to implement, while the output probabilities provide a clear classification decision.
#### Random forest model
Random Forest is an ensemble learning method that improves the performance and robustness of the overall model by combining multiple decision trees.
#### Predicting a single target (regression problem)
Accuracy: 0.7974335472043996
Feature Importance:
eccen: 0.2399
area: 0.1587
length: 0.0946
mean_tr: 0.0909
blackand: 0.0903
blackpix: 0.0878
p_black: 0.0830
p_and: 0.0805
wb_trans: 0.0584
class: 0.0160
#### Multi-objective regression problem
Mean Squared Error: 46276.27958392911
### Model evaluation
#### Gaussian NB
K-Fold :
That method is known as “k-fold cross validation”. It’s easy to follow and implement. 
#### 5-Fold Cross-validation
MIN -  0.7873510540788268
AVG -  0.813858172369428
MAX -  0.8652612282309807
#### 10-Fold Cross-validation
MIN -  0.781651376146789
AVG -  0.8087139160533656
MAX -  0.8846153846153846
#### Calculate the cross validation score on different split point in k-fold
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/27ac9b08-a244-412f-9b34-fae72b282fe4)
#### Stratified K-Fold
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/a8f180ca-f65f-4996-a10a-34918f98e95b)

### Results and Discussion
Using GaussianNB, the model achieves an average accuracy of approximately 88%.
In the 5-fold and 10-fold cross-validation, the interval between the minimum and maximum accuracy values is not large, indicating that the model has a certain stability.
Try to create new features or transform existing features to improve the performance of the model. Handle imbalanced data sets through oversampling or undersampling.



