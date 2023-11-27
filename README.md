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

![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/a55ec356-9c7e-435b-8d16-e4245bda6727)
![image](https://github.com/tianlimin2/Python-Data-analysis-A4-Project/assets/150067932/fa56f31b-beb3-4134-982d-6da0b02e2ad3)

Modeling
Using GaussianNB, we evaluated the performence by cross-validation, model achieves an average accuracy of approximately 88%.
