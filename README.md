# Bike-Sharing_Demand_Prediction

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
