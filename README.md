# Which factors influence a home’s sales price?

**Author**: Samuel Rahwa


May 5, 2021

## Overview

I have been tasked to work for RE/MAX, a real estate agency that helps homeowners buy and/or sell homes. I need to provide advice to homeowners about how home renovations might increase the estimated value of their homes, and by what amount.


## Business Problem

You can assert some control over the value of your home with diligent upkeep and selective home updates. At the same time, dozens of factors large and small impact the state of housing as a whole and how real estate performs on a local level.

***
Questions to consider:
* Do various predicting factors which have been chosen initially really affect the home prices?
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
    - Feature Engineering
    - Replacing Missing or NAN values
* Selected columns 
* Using statsmodels to run our Multiple Linear Regression
    - Logging and Scaling features
* Checking the assumptions of our linear regression
* Creating Visualizations to confirm if the statistically tests are in line with the "eye test"



## Results

This model had 14 input features: Sqft_living_log, Sqft_lot15_log, Sqft_living15_log, Bedrooms_scaled, Bathrooms_scaled , Floors_scaled, Waterfront_scaled, View_scaled, Condition_scaled, Grade_scaled, Age_scaled, Year_sold_scaled, Renovated_scaled and Month_sold_scaled.

It had an r-squared of 0.606. This model did not violate the linearity assumption (p = 0.5559), but it did violate the normality (p < 0.001) and homoscedasticity (p < 0.001) assumptions. Based on the variance inflaction factor metric, it did not violate the independence assumption for 13 of the features.

However, the Q-Q Plot shows the points falling along a straight line, which provide strong evidence that these numbers truly did come from a normal distribution.

Finally, the residual scatter plot appears to meet homoscedasticity assumption since the scores appear to be concentrated in the center (about the 0 point) and distributed in a rough rectangularly pattern

### Q-Q Plot
![graph1](https://github.com/SamuelRahwa/My-First-Linear-Regression/blob/main/images/Q-Q%20Plot.png)


### Residual Scatter Plot
![graph2](https://github.com/SamuelRahwa/My-First-Linear-Regression/blob/main/images/Residual%20Scatter%20Plot.png)


## Conclusions

**1. Do the various predicting factors which have been chosen initially really affect the home prices?**

> We are able to account for about 60% of the variance within the King County House Sales dataset by using the 14 columns mentioned previously

> This model finds a significant relationship existed between Home Prices and the 14 features

> We have strong visually strong evidence that the model’s findings are reliable


**2. Which top factors might increase the estimated value of a home, for the buyer or the seller, and by what amount?**


> The three factors that would increase value of a home:

>> 1.) For each additional 1% increase in the square footage of interior housing living space for the nearest 15 neighbors, we expect a home's price to increase by a percentage change of 0.3248.

>> 2.) For each additional 1% increase in footage of the home's, we expect a home's price to increase by a percentage change of 0.3112. 

>> 3.) For each additional 1% percent increase in the standard deviation of the overall grade given to the  housing unit, we expect a home's price to increase by a percentage change of 0.2389


**3. Which top factors might decrease the estimated value of a home, for the buyer or the seller,
and by what amount?**


>The top three factors that would decrease value of a home:

>> 1.) For each additional 1% percent increase in the standard deviation of renovation, we expect a home's price to decrease by a percentage change of -2.4270.   

>> 2.) For each additional 1% increase in square footage of the land lots of the nearest 15 neighbors,  we expect a home's price to decrease by a percentage change of -0.0949.  


>> 3.) For each additional 1% percent increase in the standard deviation for bedrooms, we expect a home's price to decrease by a percentage change of -0.0337.



***
Next Steps: 

**Are there data points we don’t have, that could be included and meaningful for RE/MAX?**

> We could look at including additional data from King County’s:
>> Schools Districts
>> Economic Activity
>> Population Demographics 
>> Occupational Employment
>> Number of Households
>> Median and Average Income
>> Education Statistics
>> Marital Status
>> Environmental, Social and Corporate Governance

***

## For More Information

Please review our full analysis in [our Jupyter Notebook](https://github.com/SamuelRahwa/King_County_Multiple_Linear_Regression/blob/main/King_County_Housing_Pricing_Multiple_Linear_Regression.ipynb) or our [presentation](https://github.com/SamuelRahwa/King_County_Multiple_Linear_Regression/blob/main/King_County_Housing_Pricing_Factors_Presentation.pdf).

For any additional questions, please contact **Samuel Rahwa at samuelaaronrahwa@gmail.com**

## Repository Structure

```
├── data                                        <- Both sourced externally and generated from code
├── images                                      <- Both sourced externally and generated from code
├── Home_Pricing_Factors_Presentation.pdf       <- PDF version of project presentation
├── Multiple_Linear_Regression_.ipynb           <- Narrative documentation of analysis in Jupyter notebook
└── README.md                                   <- The top-level README for reviewers of this project
```
