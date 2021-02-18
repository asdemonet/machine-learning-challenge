# machine-learning-challenge
By Autumn Demonet

I experimented with two models in completing the machine learning homework (Model 1: Logistic Regression and Model 2: Random Forest). The goal of this exercise was to correctly classify exoplanet data into three types: Confirmed, False Positive, or Candidate. Of the two models, Model 2 was the clear winner.

## Logistic Regression
### Model_1

I was not entirely surprised to find that the Logistic Regression did not prove to be a fruitful model for accurate predictions because of the linear boundaries that limit the model. With a Training Data Score of 0.5872592027465192 and a Testing Data Score of 0.5760869565217391, this model did not succeed at predicting exoplanet status.

## Random Forest
### Model_2
The Random Forest did prove to be a useful model, though there were some areas that needed tweaking.

I started by randomly selecting 10 columns to feed into the model ('koi_period', 'koi_time0bk', 'koi_impact', 'koi_duration', 'koi_depth', 'koi_prad', 'koi_teq', 'koi_insol', 'koi_slogg', 'koi_srad'). These columns clearly did not represent the best features to predict exoplanet status, with a Training Data Score if 1.0 and a Testing Data Score of 0.6267874165872259.

I then back-tracked and set a model to test all available features. This provided a much better result, with the resulting Training Data Score of 1.0 and Testing Data Score of 0.8732125834127741.

Finally, I ran a model that only used features with an importance score of > 0.03 ('koi_fpflag_ss', 'koi_fpflag_nt', 'koi_insol_err2', 'koi_depth_err2', 'koi_duration_err1', 'koi_fpflag_co', 'koi_duration', 'koi_prad_err1', 'koi_steff'). This trimming did not significantly improve the model, with final results of Training Data Score: 1.0 and Testing Data Score: 0.8760724499523356.

I then ran GridSearch to verify that the model was operating optimally and with the best parameters of {'max_features': 'auto', 'n_estimators': 700}, the score was only marginally improved at 0.8794145355115921.

## Conclusions
The Random Forest Model had much greater success at accurately predicting the classification of exoplanet data, with 88.