

### Overview
I am part of the City of Ames Housing division under the mayor-council government. As part of our growing population mission; providing decent, safe, affordable housing while enchancing the quality of life for econmically challenged inviduals', my team is tasked to find cost efficiency of in between house pricing and the features of it.


### Problem Statement
What are other features, apart from type of house and squarefeet, affects saleprice of houses?

### Assumptions
Nil



### Datasets
1)'new_test.csv': test data for y_predict to be submitted to kaggle
2)'train.csv': train data set to use for models fitting, and also for train-holdout
3)'cleaned_test.csv':cleaned test data for y_predict
4)'cleaned_train.csv':cleaned train data for train-holdout and train-test modelling



#### Data Dictionary
http://jse.amstat.org/v19n3/decock/DataDocumentation.txt

### Summary
After having cleaned up the data and running the various visualisations, i have decided to use correlation to saleprice as a the decision making for features to be used. Various models of linear regression, lasso, ridge and enet was ran to get the best models that can predict the least RMSE between the holdout train and test sets.

Using a linear regression model with 2 features as base, any score that drops below the rmse of holdout train and test set of base will be rejected. From there on i kept increasing the number of features to more accurately predict the root mean square error without over fitting.


With certain features chosen, we can see that while there is an decrease in hold_out for root mean squared error,it started to increas at 89 features. This is due to the model overpredicting and overfitting. As such, i scaled back to 86 features for the lowest holdour RMSE score.


The best models amongst all 4 models that gives the lowest holdout RMSE score amongst all varying number of features was then used to predict the kaggle test set. This is done so by fitting the whole train dataset after both train and holdout set has given the best models.


With the best number of features selected - top 50 of the features(excluding saleprice and pre-one hot encode) most highly correlated to saleprice - i was able to determine these features as the best predictability of saleprice.

### Conclusion
With the features identified - ['overall_qual', 'neighborhood', 'exter_qual','gr_liv_area', 'kitchen_qual', 'garage_area', 'garage_cars','total_bsmt_sf', '1st_flr_sf', 'bsmt_qual', 'age', 'garage_finish','age_remod/add', 'full_bath', 'fireplace_qu', 'foundation','mas_vnr_area', 'totrms_abvgrd', 'garage_type', 'fireplaces','heating_qc', 'ms_subclass', 'mas_vnr_type', 'bsmt_exposure','exterior_2nd', 'exterior_1st', 'wood_deck_sf', 'open_porch_sf','lot_frontage', 'ms_zoning', 'lot_area', 'lot_shape', 'bsmt_full_bath','half_bath', 'roof_style', 'house_style', 'garage_age', '2nd_flr_sf','bldg_type', 'fence', 'bedroom_abvgr', 'enclosed_porch', 'screen_porch','lot_config', 'kitchen_abvgr', 'overall_cond', '3ssn_porch','bsmt_half_bath', 'low_qual_fin_sf'] - we can help the ecnomically challenged decide which features do they deem more important than the other features.

For example, if a client determines that the kitchen quality is more important than the garage area or number of cars a garage can hold, the client can choose for a house with better kitchen quality and a smaller garage area or even a house with no garage. This can help to optimise their budget by choosing the specific quality or size of the features that they deem important or necessary.

Being able to identify these features allows economically challenged individuals to use these indicators as a guideline to further plan what they want vs their finanical capability for the type of house and state, quality of size of features they desired. So as to find the best fit of house that suits their needs and their budget.