# Machine Learning writeup
Eduardo B. Diez  
Tuesday, August 12, 2014  



# Introduction

The goal of your project is to predict the manner in which they did the exercise. 
This is the "classe" variable in the training set. 

You may use any of the other variables to predict with. 
You should create a report describing 

1. how you built your model, 

2. how you used cross validation, 

3. what you think the expected out of sample error is, 

4. and why you made the choices you did.



You will also use your prediction model to predict
20 different test cases.

1 Has the student submitted a github repo?

2 Do the authors describe what they expect the out of sample error to be and estimate the
error appropriately with cross-validation?
r: 
Trading off goodness of fit against model complexity
 If the model has as many degrees of
freedom as the data, it can fit the
training data perfectly
 But the objective in ML is generalization
 Can expect a model to generalize well if it explains the training data
surprisingly well given the complexity of the model

#Cleaning the Data





After inspection and work with the data we arrive to the conclusion that the variable we can considerer as real feature are:


<img src="img/DataInspection.png" title="Figure 1. Initial set of features selected; Roll, Pitch, Yaw and total acceleration." alt="Figure 1. Initial set of features selected; Roll, Pitch, Yaw and total acceleration." width="100%\textwidth" />

Finally we confirm that `roll_bell` was correlated with two other features therefore was remove, giving the final features as: 


```r
mypredictors <- c("pitch_belt", "yaw_belt", "total_accel_belt",
                  "roll_arm", "pitch_arm", "yaw_arm", "total_accel_arm",
                  "roll_dumbbell", "pitch_dumbbell", "yaw_dumbbell", 
                  "total_accel_dumbbell", "roll_forearm", "pitch_forearm", 
                  "yaw_forearm", "total_accel_forearm")
```



<img src="img/ROCplot.png" title="Figure 2. The ROC curves for the models with the total AUC (Area Under the Curve) with 95% confidence interval and the total process time running in Mobile Intel Core 2 T6400 at 2GHz with 4GB" alt="Figure 2. The ROC curves for the models with the total AUC (Area Under the Curve) with 95% confidence interval and the total process time running in Mobile Intel Core 2 T6400 at 2GHz with 4GB" width="100%\textwidth" />


