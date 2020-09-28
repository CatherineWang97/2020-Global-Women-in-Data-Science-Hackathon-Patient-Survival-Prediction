# 2020 Global Women in Data Science Hackathon Patient Survival Prediction

### Modeling in Subgroups: One Model or Many?


#### Goal: 
build a model to predict patient survival given these ICU visit information, and take a practical approach to evaluating the question of which modeling strategy leads to the most effective predictions. (More specifically, I designed an experiment to answer the question of whether to use one model or many models.)




#### Background:
Large data sets can include a variety of subgroups. The qualities of these subgroups may be quite different from each other. Each subgroup may have a different relationship between the outcome and the predictors in a supervised learning model. This raises a question of how to generate the best predictions. Some options (among others) would include:

• One Model: All of the subgroups are aggregated into a single data set that is used to inform the construction of a single model.

• Many Models: A separate model is constructed for each subgroup based upon the corresponding subset of the overall data.




#### These differing approaches have their respective advantages and disadvantages:

• One Model: It is easier to build, use, revise, and maintain one model. A larger overall sample size can be utilized. However, a single model will assume that each prediction’s association with the outcome is similar across all of the subgroups.

• Many Models: Modeling within a subgroup can provide a customized estimate of the relationships between the predictors and the outcome in that subgroup. This allows for differing effects across the models. However, each subgroup’s model will necessarily be based on a smaller sample size. Developing, using, and revising multiple models can also require substantially greater labor.




#### The Setting: Predicting Patient Survival

I used patient health data from MIT’s GOSSIS (Global Open Source Severity of Illness Score). This dataset was used in the 2020 Global Women in Data Science hackathon hosted by Kaggle (https://www.kaggle.com/c/widsdatathon2020/overview).The dataset includes information about more than 130,000 Intensive Care Unit (ICU) visits. Our goal is to build a model to predict patient survival given these ICU visit information.




#### Adversarial Validation:

In some instances, our training & testing sets do not appear to come from the same distribution (not i.i.d.). For example, some features may have high cardinality, and when we randomly split them into two sets, the features do not appear to come from the same distribution. We should omit those features from our modeling as they would lead to biased predictions. An approach to identify these features is called Adversarial Validation. Use adversarial validation to identify and remove features that may not generalize well to the overall dataset.




### The Experiement:

#### Outcome:

The outcome of each model will be a binary indication of whether a patient survived (1 or TRUE) or not (0 or FALSE).




#### Classification Approach:

Each model will be used to classify whether a patient survived (hospital_death). The values returned will either be:

• 1 (or TRUE): The patient survived.

• 0 (or FALSE): The patient did not survived.




#### Categories of Models:

• K Nearest Neighbors (Package: class; Function: knn)

• Logistic Regression (Function: glm)

• Lasso, Ridge, or Elastic Net Regression (Package: glmnet; Function: glmnet)

• Decision Tree (Package: rpart; Function: rpart)

• Boosting Models (Package: gbm; Function: gbm or Package: xgboost; Function: xgboost) 




#### Experimental Subgroups: Age

The age variable will be used as the basis of assessing the relative merits of fitting one model (on all of the data) or many models (one for each subgroup of age).

The age subgroups can be defined as: [0-50), [50-60), [60-70), [70-80), [80-100).

Each of the 5 models choosen will be fit in two ways: as One Model and as Many Models.

• One Model: fit a single model that includes all of the training data, including all of the subgroups of age.

• Many Models: fit separate models on each subset of the training data, one for each of the subgroups of age.


Please feel free to download the html!

