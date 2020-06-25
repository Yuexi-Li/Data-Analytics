# Regressions
**Outline**
<ul>
<li><a href="#L1">Regression</a></li>
<li><a href="#L2">Multilinear Regression</a></li>
<li><a href="#L3">Logistic Regression</a></li>
</ul>

****

<a id='L1'></a>
## Regression
<img src="Notes/../Pics/mindmap_regression.png">
- The most common way to visualize simple linear regression is using a scatter plot. 
#### Correlation Coefficient
  - Correlation coefficients provide a measure of the strength and direction of a linear relationship.
    - strength:  closeness of points 
    - direction: positive or negative 
  - **Calculation**:
    $r =
  \frac{ \sum_{i=1}^{n}(x_i-\bar{x})(y_i-\bar{y}) }{%
        \sqrt{\sum_{i=1}^{n}(x_i-\bar{x})^2}\sqrt{\sum_{i=1}^{n}(y_i-\bar{y})^2}}$
  - **Rule of thumb:** 
    - Strong relationship  $0.7≤∣r∣≤1.0$   
    - Moderate relationship $0.3≤∣r∣<0.7$
    - Weak relationship $0.0≤∣r∣<0.3$ 
    > Note: a correlation coefficient of 0 there is no **linear** relationship between two variables. 

#### Define the line 
* Component:
  - **intercept**: the predicted value of the response when the x variable is zero
  - **slope**: the predicted change in the response for every 1 unit increase in the x variable 
* Regression Line:
  - Method: MSE
  - minimize $\sum_{i=1}^{n}(y_i-\hat{y})^2$ 
  - find the minimum value of: for each data point in the dataset, look at the distance between the predicted and actual values, square these and sum them all together. 
  - Manual calculation
  <img src="Notes/../Pics/Regression_calculation1.png">

#### Code Practice and interpretation 

  ```
  import statsmodels.api as sm

  df['intercept'] = 1

  lm = sm.OLS(df.y, df[[x1, intercept]])
  result = lm.fit()
  result.summary()
  ```
Interpretation ([v1](https://www.youtube.com/watch?time_continue=13&v=eLk0XGGMaCE&feature=emb_logo),[v2](https://www.youtube.com/watch?time_continue=7&v=0vPtPAqMHJE&feature=emb_logo))
<img src = "Notes/../Pics/OLS_regression_results.png" >

* **p-value:** 
  -> if the variable is statistically significant for predicting the dependent variable 
  > the p-value associated with area is very small, which sugguests there is a statistical evidence that population slope associated with area in relating to price is non-zero. 
* **R-squared:** 
  -> square of correlation coefficient, between 0 and 1 
     the more closer to 1, the better fit. 
  -> amount of varibility in the dependent variable y explained by the model.
   > e.g. 67.8% of the varibility in area can be explained by the price of a house. 
* **coef:**  
   > e.g. for ever one unit increase in area, the predicted increaase in price is 348.5.
* **intercept:**
   > e.g. Based on our predicted values, it would be unexpected to have a price below 9588, because this is the predicted price of a house with no area.
****

<a id='L2'></a>
## Multilinear Regression

****

<a id='L3'></a>
## Logistic Regression