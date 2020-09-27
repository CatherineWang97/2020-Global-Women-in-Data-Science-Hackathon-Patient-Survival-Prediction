# 2020-Global-Women-in-Data-Science-hackathon-Patient-Survival-Prediction

Large data sets can include a variety of subgroups. The qualities of these subgroups may be quite different from each other. Each subgroup may have a different relationship between the outcome and the predictors in a supervised learning model. This raises a question of how to generate the best predictions. Some options (among others) would include:

• One Model: All of the subgroups are aggregated into a single data set that is used to inform the construction of a single model.
• Many Models: A separate model is constructed for each subgroup based upon the corresponding subset of the overall data.


These differing approaches have their respective advantages and disadvantages:
• One Model: It is easier to build, use, revise, and maintain one model. A larger overall sample size can be utilized. However, a single model will assume that each prediction’s association with the outcome is similar across all of the subgroups.
• Many Models: Modeling within a subgroup can provide a customized estimate of the relationships between the predictors and the outcome in that subgroup. This allows for differing effects across the models. However, each subgroup’s model will necessarily be based on a smaller sample size. Developing, using, and revising multiple models can also require substantially greater labor.
