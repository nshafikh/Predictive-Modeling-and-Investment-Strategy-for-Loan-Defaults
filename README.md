# Predictive Modeling and Investment Strategy for Loan Defaults
### By Nima Shafikhani, Asad Shoaib, Hsiu-Yuan Yang, Karshni Mitra

This is a comprehensive end-to-end Machine Learning project where we leveraged predictive analytics models (Naïve Bayes, Lasso, Ridge, Random Forest, Decision Tree, Neural Network) to assess loan default likelihood, optimize model selection, implement ML-based investment strategies and evaluate returns using historical loan data.

## Data
The LendingClub loan data is from 2007-2018 and sourced from Kaggle.

## Investment Strategies
a. Random (Rand): randomly picking loans to invest in

b. Default-based (Def): using best performing model; particularly, sorting loans by their estimated Default likelihood, and selecting the ones with the lowest likelihood to invest in.

c. Return-based (Ret): training a simple regression model (e.g., linear, random forest, NN regressor) to predict the (calculated) return on historical loans directly. Then, sorting out-of-sample loans by their predicted returns and selecting the loans with the highest predicted returns to invest in.

d. Default-& Return-based (DefRet): training two additional models: one to predict the return on loans that did not default, and another to predict the return on loans that did default. Then, using the likelihood of Default predicted by best performing model to find the expected value of the return

## Results
The best performing model is the Random Forest Classifier. It’s accuracy is only slightly less than the other models, but its recall score is over 10x greater than the next best model. Even with this recall being so much greater, the precision of the Random Forest Classifier doesn’t take a big hit.

Although the Default based strategy performs the best in two of the four types of return, its poor performance in M1 (pessimistic return type) combined with the consistently high returns in all return types from Return based strategy makes us believe that a Return based strategy would be the best. The Random strategy performs the worst in 3 out of the 4 return types, as expected. It causes a loss for one of the return types (pessimistic). This is because there is no logic to the investments in this case, and one may make terrible investments that would never be chosen from the other three strategies. All of the data-driven strategies seem to perform better than the Random strategy, except for Default based in M3(2.3%). All of the data-driven strategies are considered the best with at least one of the return types
