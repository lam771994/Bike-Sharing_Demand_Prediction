# Bike-Sharing_Demand_Prediction

*Source codes can be found in the repository under Bike_Sharing_Demand_Prediction


*HTML version of the source codes: [HTML_Bike-Sharing_Demand_Prediction](file:///Users/lamyingxian/Desktop/Desktop%20-%20iMac%20Lam/DSBA_2021/4.%20Applied%20Machine%20Learning/3.%20Assignments-20210215/Assignment%20-%20Part%20B/LAM_YING_XIAN_TP063038_Codes.html)

## Problem Statement

One of the biggest challenges faced in the bike-sharing system is the unavailability or shortage of bike. This issue has attracted numerous researchers to predict the demand of bike-sharing so that the company is able to redistribute the bikes efficiently and accurately. Correctly predicting the count of the bikes can be challenging especially when the data collected are often imbalance (Sathiskumer and Cho, 2020a). Moreover, despite the several efforts to train models to predict the demand, there is no consensus on which machine learning techniques that will provide the best performance due to the different features applied (Albuquerque et al., 2021). Meanwhile, no standardised features have proven to be the variables that will significantly improve the models (Albuquerque et al., 2021). Lastly, it is observed that feature engineering is heavily focused in Kaggle kernels, but not in published journal articles. As a result, this report will investigate three main areas such as the best performing machine learning techniques, the feature engineering methods and the features that will significantly enhance the prediction of the bike-sharing demand.

## Project Objectives

A.	To explore and critique multiple machine learning techniques to accurately predicting the demand of bike-sharing;

B.	To optimise, fine-tune and explore the feature engineering methods and hyperparameter for better performance of predictive model; and

C.	To explore the correlation between features and discover the most relevant features that bring better accuracy to the predictive model.


## Analysis of Other Related Projects

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Related_Works_1.png)
![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Related_Works_2.png)
![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Related_Works_3.png)

#### Summary of the Related Projects:

There are several techniques within the feature engineering which will be listed and numbered below:
(1) imputation; 
(2) outliers management; 
(3) binning; 
(4) data transformation; 
(5) one-hot encoding; 
(6) data sampling; 
(7) data scaling;  
(8) data extraction; 
(9) data splitting; and 
(10) No information available but feature engineering is directly or indirectly stated 

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Summary_Related_Projects_1.png)
![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Summary_Related_Projects_2.png)

Based on the analysis of related projects, there are a few takeaways:

1.	Higher accuracy and lower error can be observed in the feature engineered data, especially when the data is normalised and transformed. It can be obviously seen in the RF model trained by Harding (2021), Gradient Boosting built by Taranu (2020) as well as KNN and DT model produced by Salahat (2021). A significant observation from these models is the application of data transformation;

2.	Gradient Boosting is arguably the most stable method because it has the lowest error among all the models (Taranu, 2020);

3.	Kaggle contributors trained the most stable kernels as compared authors that published their models. This can be observed in the RF model trained by a Kaggle master, Harding (2021) where the RMSLE is only 2.03 as compared to the published model built by Xu et al. (2020) who produced RMSLE of 4.28. Another observation can be found in the Gradient Boosting model built by Taranu (2020) where the Kaggle contributor has RMSLE of 0.28 as compared to the published model that has 11.43;

4.	Majority of the authors have applied RMSE as the evaluation score, however, it should be noted that RMSE is not the best evaluation metric, so other metrics should be explored for better model evaluation (Hossin and Sulaiman, 2015); and

5.	Using GridSearch have significantly lowered down the error which can be seen in Harding (2021) RF model, Baek (2021) LR and RR model;


## Gap & Scope Analysis

The analysis presented above have clearly demonstrated the strengths and weaknesses of the techniques used to predict the bike-sharing demand. This section will introduce some questions to address the loopholes within the related projects to achieve the objectives of this project.

1.	Do regression models perform better with the more parameter tuning?

2.	Does outlier treatment improve the prediction since it is not widely used in the related works?

3.	Does data scaling enhance the model performance?


The evaluation of the related projects has presented some gaps within the researched area. This part will scope down the problems identified to reach the stated objectives:

1.	Model improvement will only be done on kernels of Decision Tree, Random Forest, and Gradient Boosting;

2.	Outlier treatment will be performed on necessary variables to investigate whether it will enhance the performance of the models; and

3.	Data scaling will be carried out to test the model performance.


## Exploratory Data Analysis 

#### 1. Description of Features

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Descriptions_Features.png)

#### 2. Overview of the Features

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Diagonal_Network.png)

As shown in the diagonal network, there are 13 features in the dataset. 7 of the independent variables (i.e., instant, temp, atemp, humidity, windspeed, casual, registered) are integer whereas 4 of them are factor. The dependent variable (i.e., count) that predicts the demand of the bike-sharing is integer. Additionally, the date of the bike rented (i.e., datetime) is datetime type.

#### 3. Missing Values

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Missing_Values.png)

Based on the missing values plot, there is no missing values in the dataset.

#### 4. Frequency Distribution of Continuous Variables

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Histogram.png)

The summary of the observations based on the histogram can be found below:

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Histogram_Findings.png)

#### 5. Normality of Data Distribution

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/QQ_Plot.png)

QQ plot is another clearer tool to observe the distribution of the continuous data by looking at the head and tail curve. The closer the tail to the normality line, the distribution is more normal. The QQ plot above supports the observation in the histogram where the tails of count, casual and registered significantly move away from the normality line which means there are extreme data within these variables.

#### 6. Frequency of Discrete Variables

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Bar_Chart_Frequency.png)

The frequency of each variables can be observed in the tables and the bar chart. Winter, not holiday, working day and clear weather are observed to have the most frequency in the dataset.

#### 7. Correlation Analysis

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Correlation_Analysis.png)

Heatmap is a visualization used to analyse the relationship between different features. The darker the red colour means the features are more correlated. Contrary, the darker the blue colour indicates the features are less correlated. Highly correlated features should be removed as they may affect the performance of the model. Based on the heatmap above, count and registered are highly correlated as well as temp and atemp. 

#### 8. Outliers Identification

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Box_Plot.png)

The purpose of boxplot is to identify any outliers in the data. According to the box plot shown above, casual and windspeed have the most extreme outliers.

#### Exploratory Data Analysis Findings

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/EDA_Findings.png)

The following are the data pre-processing that have been performed which can be explored in the source codes:

A.	Data splitting: split the data into train and test dataset with the proportion of 70%-30%;

B.	Data cleaning: outliers will be removed;

C.	Data sampling: the data will be up-sampling to neutralise the dependent variable;

D.	Data scaling: to rescale the non-normally distributed continuous data;

E.	Data transformation: the skewed data will be transformed with logarithm; and

F.	Feature selection: highly correlated features will be manually removed.

## Model Implementation & Validation

#### 1. Dataset for Each Pre-Processing Technique

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Dataset.png)

#### 2. Model Experimentation Plan

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Model%20Experiment%20Plan.png)

#### 3. Summary of Results for the Experiments of **Decision Tree Regression**

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Decision_Tree_Regression.png)

#### 4. Summary of Results for the Experiments of **Random Forest Regression**

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Random_Forest_Regression.png)

#### 5. Summary of Results for the Experiments of **Gradient Boosting Regression**

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Gradient_Boosting_Regression.png)

#### 6. Models Assumptions vs Observations in Experiments

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Models%20Assumptions%20vs%20Observations%20in%20Experiments.png)

#### 7. The Effect of Hyperparameter & Data Pre-Processing Techniques on Models Performance

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Effects_of_Hyperparameter_Tuning%26Pre_processing_Techniques_on_Models_Performance.png)

#### 8. Models Performance in Experiments

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Models_Performance_in_Experiments.png)

#### 9. Models Performance: Experiments vs Related Projects

![alt text](https://github.com/lam771994/Bike-Sharing_Demand_Prediction/blob/main/Photos/Experiments%20vs%20Related%20Works.png)

It can be concluded that the model of gradient boosting regression that have undergone hyperparameter tuning and outlier treatment is the most suitable predictive model for the topic and the dataset.

## Results Analysis & Recommendations

**The part will provide the answers that discovered from the analysis above for the gap analysis.**

1.	Do regression models perform better with the more parameter tuning?

Based on the comparison between experiments and the related works, the tree-based regression models perform better with the hyperparameter tuning.

2.	Does outlier treatment improve the prediction since it is not widely used in the related works?

According to the analysis above, the application of outlier treatment has significantly improved the performance of the three tree-based models.

3.	Does data scaling enhance the model performance?

Surprisingly, data scaling does not enhance the performance of the three tree-based models and this could be caused by the high dimensional data and the insufficient training sample.




**After the analysis of the experiments and the related works, several recommendations will be provided as follows:**

1.	Previous works performed by the journal article authors and Kaggle contributors should be evaluated together because significant insights could be observed as both researchers and contributors have different approaches in training a model;

2.	Experiment plan should be conducted to provide clear aim and objectives for the report;

3.	Plots are important to understand the patterns of the data, however statistical numbers should be emphasised more rather than making assumptions from the plots;

4.	 Understanding the parameters for each model are essential because not all parameters will provide significant outcomes;

5.	Random forest model may not be the best model if the dataset is high dimensional; and

6.	In the aspect of the domain knowledge, the location of the bike-sharing system, age of the bike user and income of the user should be collected for better understanding of the bike-sharing demand.

7.	Deep learning method such as the neural network should be explored deeper as it could potentially provide better accuracy in the prediction of the bike sharing demand.

