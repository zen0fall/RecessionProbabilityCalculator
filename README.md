# RecessionProbabilityCalculator
The goal of this notebook is to test if treasury spreads 10Y-2Y, 10Y-3M along with SPX and VIX are successful in indicating impending economic recession. This concept is based on paper: https://www.frbsf.org/economic-research/publications/economic-letter/2018/march/economic-forecasts-with-yield-curve/

# Modeling Strategy

* Based on the graph of data in notebook, we observe that 10Y2Y and 10Y3M spreads attain their local minima a few months prior to the recession, so for now we manually chose the lag to be 6m (180days) on all feature variables, later we will use a grid search to find the optimized lag. It also makes modelings sense to introduce lags in x-variables as we want some future prediction capability in our model. i.e if we have today's data we should be able to predict probability of recession 6months ahead. 

* We will create test and train test based on stratification on the recession indicator variable - because out of all the data we are in recession only 12% of time. Thus the training split should indicate the same split. 

* Use Logistic Regression - only on training data

* Our regression equation in log space will be of form y(t) = a*[X(t-6M)] +[C]

* Evaluate Regression on test data
