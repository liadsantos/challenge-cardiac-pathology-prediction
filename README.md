# Kaggle Challenge - Cardiac pathology prediction

![image](https://github.com/liadsantos/challenge-cardiac-pathology-prediction/assets/115878785/d8073442-6489-4266-9ff1-02e955895e35)

The challenge focuses on four cardiac pathologies that might go unnoticed at first, but can ultimately become life-threatening. Complications include heart failure and sudden cardiac arrest.
The goal of this challenge is to classify MRI images of the heart among five different diagnostic classes:

1. Healthy controls
2. Myocardial infarction
3. Dilated cardiomyopathy
4. Hypertrophic cardiomyopathy
5. Abnormal right ventricle

In order to achieve this goal, I extract the volume of the anatomical structures at two different time points in the cardiac cycle (end of the cardiac contraction and end of the dilation), the thickness of the cardiac muscle, and the ejection fractions. After that, you will use machine learning algorithms to classify the subjects.

## Dataset
The dataset is composed of 150 subjects with their MRI images and, when available, their corresponding segmentations and metadata (subject height and weight). Data has already been randomly split into a training-validation set (two thirds = 100 subjects) and a test set (one third = 50 subjects). The classification of the trining-validation set is provided (made by clinicians). 

The class labels ("Category" field in the metadata) are mapped thusly to diagnostic classes:
- '0' - Healthy control
- '1' - Myocardial infarction
- '2' - Dilated cardiomyopathy
- '3' - Hypertrophic cardiomyopathy
- '4' - Abnormal right ventricle

For each subject, two MRI images are provided : one image at end diastole (end of dilation in the cardiac cycle) and one image at end systole (end of contraction). Each MRI image is a 3D volume containing the heart and adjacent structures.

## Metrics
As ranking metric, we will use the Categorization Accuracy, which is defined as:
$$Acc = \frac{1}{N} \sum_{i=1}^{n} I(y_i = f_i)$$
where $N$ is the number of test subjects, $y_i$ is the ground truth labels for subject $i$ and $f_i$ is the predicted label. 

## Results
In the provide code, different segmentation methods were tested and so different classification algorithms, such as SVM and ICA.
