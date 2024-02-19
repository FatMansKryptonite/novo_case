# Novo Case
This is a project to solve the case given to me by Novo Nordisk. For any questions contact me!

I will be focusing on breadth rather than depth to display a variety of skills. I will not be focusing on implementing all potential changes to improve performance but will instead speculate on what could be done and how the changes would impact the model. 

Finally, I have said that my weakest point as a data scientist is MLOps, and I stand by that. Don't judge this project for it's hacky tackyness, it was done in haste!

# Notes
- We opt for an efficiency metric as our target variable as the number of patients enrolled will be heavily impacted by the time spent enrolling patients. This metric is not perfect however, as more funding on a project can mean that a larger effort can be exerted in a shorter period of time. This leads me to think a "cost efficiency" metric might be preferrable.
- Initial experiment displayed terrible results (TEST MAPE: ~52 %). Investiagtion shows that this is due to poor data quality of `enrolment_months` and the discrete nature of `no_of_patients`. These together lead to extreme outliers and negative efficiencies. 
    - Dropping data points with unusually low `enrolment_months` improves performance massively (Test MAPE: ~52 % -> ~7 %)
    - But we loose a lot of potential training data (~27 %)
    - Additionally, we probably have significantly worse performance in cases with few enrolment months

# TODO
- [x] Read in data
- [x] Do initial EDA with `ydata-profiling`
- [x] Feature engineer
    - [x] Target variable
    - [x] Trial length
    - [x] Trial multiclass labels
- [x] Build initial model
- [ ] Analyse feature importance with `SHAP`
- [ ] Consider definition of target metric.
    - Does it make sense to go with efficiency like we have defined it (`efficiency = no_of_patients / enrolment_months`)?
    - Should we try to estimate a "cost efficiency" instead as trials might have different funding?
- [ ] Consider methodology so we do not need to drop training data with few/low enrolment months
- [ ] Hyper parameter tuning
- [ ] Try different methodologies
    - Neural net
    - Linear regression
    - Gradient boosting machine
    - SVM
    - KNN
- [ ] Regularisation techniques
    - [ ] Do PCA on country variables
    - [ ] Tree pruning
    - [ ] Ridge/Lasso regularisation for a linear model?

# Conclusions

# Further work