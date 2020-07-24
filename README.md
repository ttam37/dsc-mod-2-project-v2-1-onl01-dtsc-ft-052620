
# King County Housing Analysis

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/README%20images/king_county_pic.jpg)

For this analysis, we worked on the King County House sales dataset. The main objective is to create the best model and see which features best affect the home prices of King County. We will perform linear regression analysis on the data and perform various statistical methods to help predict prices of homes based on selected features.

# Process Overview

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/README%20images/osemn_model.png)

# Technologies Used

## Python
* Pandas for Data Cleaning & Data Manipulation
* Matplotlib and Seaborn for Data Visualization
* Numpy for Calculations
* SciPy/Statsmodels/Scikit Learn for Linear Regression

# Description of Dataset

The dataset was originally downloaded from an user from Kaggle. The original source can be found here:
https://www.kaggle.com/harlfoxem/housesalesprediction/metadata

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

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_1.png)

## Question 2: Which city, on average has the most expensive homes?

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_2_scatter.png)
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_2_bar.png)

## Question 3: Which features are most corrected with price?

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_3_bar.png)

# Linear Regression Assumptions

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/final_model_linearity.png)
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/final_model_normality.png)
![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/final_model_homo.png)

# Multicollinearity

![King County House](https://github.com/ttam37/dsc-mod-2-project-v2-1-onl01-dtsc-ft-052620/blob/master/images/EDA_3_multicollinearity.png)

# Final Model Results

# Conclusion
