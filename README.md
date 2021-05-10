# Which factors influence a home’s sales price?

**Author**: Samuel Rahwa


May 5, 2021

## Overview

I have been tasked to work for RE/MAX, a real estate agency that helps homeowners buy and/or sell homes. I need to provide advice to homeowners about how home renovations might increase the estimated value of their homes, and by what amount.


## Business Problem

You can assert some control over the value of your home with diligent upkeep and selective home updates. At the same time, dozens of factors large and small impact the state of housing as a whole and how real estate performs on a local level.

***
Questions to consider:
* Does various predicting factors which have been chosen initially really affect the home prices?
* Which top factors might increase the estimated value of a home, for the buyer or the seller, and by what amount?
* Which top factors might decrease the estimated value of a home, for the buyer or the seller, and by what amount?*
***

## Data

This project uses the King County House Sales dataset, which can be found in  `kc_house_data.csv` in the data folder in this repo. The description of the column names can be found in `column_names.md` in the same folder.

From the King County House Sales dataset, I used the following features:

* sqft_living
* sqft_lot15
* sqft_living15
* bedrooms
* bathrooms
* floors
* waterfront
* view
* condition
* grade
* age
* year_sold
* renovated
* month_sold

## Methods

* Data Exploration
* Data Cleaning
* Creating a subset dataframe to answer business questions
    - Logging continuous variables
    - Scaling non-continuous features
* Using statsmodels to run our Multiple  Linear Regression
    - Checking the assumptions of our linear regression
    - Creating Visualizations to confirm if the mathematically tests are in line with the "eye test"


## Results

Our final model had an r-squared of 0.597. This model did not violate the linearity assumption (p = 0.8494), but it did violate the normality (p < 0.001) and homoscedasticity (p < 0.001) assumptions. Based on the variance inflaction factor metric, it did not violate the independence assumption.

However, the Q-Q Plot shows the points falling along a straight line, which provide strong evidence that these numbers truly did come from a normal distribution. Finally, the residual scatter plot appears to meet homoscedasticity assumption since the scores appear to be concentrated in the center (about the 0 point) and distributed in a rough rectangularly pattern.

### Q-Q Plot
![graph1](https://github.com/SamuelRahwa/My-First-Linear-Regression/blob/main/images/Q-Q%20Plot.png)


### Residual Scatter Plot
![graph2](https://github.com/SamuelRahwa/My-First-Linear-Regression/blob/main/images/Residual%20Scatter%20Plot.png)


## Conclusions

**1. Does various predicting factors which have been chosen initially really affect the home prices?**

> With 14 features we are able to explain about 60% of the variance in home prices in house sales, from a northwestern county. This indicates that these factors truly are explanatory. More analysis is required to understand how much additional explanatory power would be provided by incorporating features with less multicollinearity.


**2. Which top factors might increase the estimated value of a home, for the buyer or the seller, and by what amount?**


> The three factors that would increase value of a home:

>> 1. Square Foot Living

>> 2. Square Foot Living 15

>> 3. Grade


**3. Which top factors might decrease the estimated value of a home, for the buyer or the seller,
and by what amount?**


>The top three factors that would decrease value of a home:

>> 1. Renovated

>> 2. Waterfront

>> 3. Square Foot Living 15




***
Questions to consider:

**What would you recommend the business do as a result of this work?**

> We can advise homeowner's who are looking to sell for the highest price possible, to increase the square footage of their home, make sure the county gives you the highest grade rating possible (when they come to evaluate), and compare the square footage of your home against your nearest 15 neighbors.

**What are some reasons why your analysis might not fully solve the business problem?**

> Multicollinearity was a problem because it undermines the statistical significance of an independent variable (Price). Other things being equal, the larger the standard error of a regression coefficient, the less likely it is that this coefficient will be statistically significant.

**What else could you do in the future to improve this project?**

> The use of an expanded dataset with more home features or our various datasets included from the surrounding cites and counties

***

## For More Information

Please review our full analysis in [our Jupyter Notebook](https://github.com/SamuelRahwa/My-First-Linear-Regression/blob/main/Multiple_Linear_Regression.ipynb) or our [presentation](https://github.com/SamuelRahwa/My-First-Linear-Regression/blob/main/Home_Pricing_Factors_Presentation.pdf).

For any additional questions, please contact **Samuel Rahwa at samuelaaronrahwa@gmail.com**

## Repository Structure

```
├── data                                        <- Both sourced externally and generated from code
├── images                                      <- Both sourced externally and generated from code
├── Home_Pricing_Factors_Presentation.pdf       <- PDF version of project presentation
├── Multiple_Linear_Regression_.ipynb           <- Narrative documentation of analysis in Jupyter notebook
└── README.md                                   <- The top-level README for reviewers of this project
```
