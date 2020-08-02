
# King County Housing Analysis

[King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/king_county_pic.jpg)

For this analysis, we worked on the King County House sales dataset. The main objective is to create the best model and see which features best affect the home prices of King County. We will perform linear regression analysis on the data and perform various statistical methods to help predict prices of homes based on selected features.

# Process Overview

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/osemn_model.png)

# Technologies Used

## Python
* Pandas for Data Cleaning & Data Manipulation
* Matplotlib and Seaborn for Data Visualization
* Numpy for Calculations
* SciPy/Statsmodels/Scikit Learn for Linear Regression

# Description of Dataset

The dataset was originally from an user from Kaggle, but was modified by Flatiron School to allow the dataset to be more challenging. The original source can be found here:
https://www.kaggle.com/harlfoxem/housesalesprediction

## Column Description

* **id** - unique identified for a house
* **dateDate** - house was sold
* **pricePrice** -  is prediction target
* **bedroomsNumber** -  of Bedrooms/House
* **bathroomsNumber** -  of bathrooms/bedrooms
* **sqft_livingsquare** -  footage of the home
* **sqft_lotsquare** -  footage of the lot
* **floorsTotal** -  floors (levels) in house
* **waterfront** - House which has a view to a waterfront
* **view** - Quality of the view
* **condition** - How good the condition is ( Overall )
* **grade** - overall grade given to the housing unit, based on King County grading system
* **sqft_above** - square footage of house apart from basement
* **sqft_basement** - square footage of the basement
* **yr_built** - Built Year
* **yr_renovated** - Year when house was renovated
* **zipcode** - zip
* **lat** - Latitude coordinate
* **long** - Longitude coordinate
* **sqft_living15** - The square footage of interior housing living space for the nearest 15 neighbors
* **sqft_lot15** - The square footage of the land lots of the nearest 15 neighbors

## Feature Engineering

* **total_sqft** - Total square footage (square_living + sqft_lot)
* **total_sqft_inside** - Total square footage of inside (sqft_above + sqft_sqft_basement)
* **age_when_sold** - Age of the house when it was sold (year_sold - yr_built)
* **city** - City location of the house

# Exploratory Data Analysis

## Question 1: Does the distance between a house and downtown Seattle affect house prices?
From the plot shown below, more expensive houses are in the Northern side of King County. There are a cluster of expensive houses near Seattle that surrounds the Lake Washington. Generally expensive houses surround the lake such as the city Medina being the most expensive city in King County. If we magnify into downtown Seattle, houses are average priced. Another observation is that houses are clustered in specific regions which can possibly be an important feature (lat and long, city).

From my analysis, the correlation between the distance and price is -0.211, a weak negative correlation. In addition, R-squared value is 0.098 which is not represented by the prediction model. More preprocessing needs to be done. 

I originally wanted to create feature engineering for my data, but because the results weren't satisfying I decided to not use this feature.
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_1.png)

## Question 2: Which city, on average has the most expensive homes?
This was a personal question for myself in which I wanted to know what cities were most expensive in King County (in case I want to move to King County area). There is an obvious trend where there are less samples for more expensive cities and more samples for lower priced cities. Seattle, being the biggest city, have the most samples whereas Medina has the least samples.

The most expensive city is Medina in which the average house price is $2,200,000. Medina is home to many large CEOs and executives including Jeff Bezos and Bill Gates. The most popular city of King County is Seattle which is average priced, $540,000. The lowest priced city is Federal Way, average price of $290,000.
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_2_scatter.png)
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_2_bar.png)

## Question 3: Which features are most correlated with price?
In my analysis, I considered features that were above 0.10 correlation to be correlated with price. Anything below absolute value of 0.10, I removed from the model. Since categorical features/dummy variables automatically meet the linear assumption, these features are kept.
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_3_bar.png)

# Linear Regression Assumptions
If regression assumptions are not satisfied, we may not be able to get trustworthy results. IF violated, regression makes biased and unreliable predictions. We need to measure and check for the following assumptions:
* Linearity - lineary relationship between predictor and target variable
* Normality - model residuals should follow a normal distribution
* Homoscedasticity - dependent variable is equal across the range of values of the predictors
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/final_model_linearity.png)
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/final_model_normality.png)
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/final_model_homo.png)

# Multicollinearity
The assumption in linear regression is that the dependent variable changes based on a change in an independent variable, with all other variables held constant. The heatmap below shows which pairs are most correlated with each other. Outside of the target variable, we want to check if there is high correlation between the predictors and remove them as necessary.

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_3_multicollinearity.png)

# Final Model Results

In the form of the linear regression formula: y = b1x1 + b2x2 + … + bnxn + c:
* bn - beta coefficients
* xn - (1) independent variable
* y - (1) dependent variable
* c - intercept

## Final R-squared value: 0.705

Top Coefficients: 
* city_Medina
* city_mercerIsland
* latitude
* longitude 
* waterfront_1
