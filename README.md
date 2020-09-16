# Real-Estate-Prices-in-King-County

This document will cover an extensive exploratory data analysis using the King County Real Estate dataset. 

## 1. Goal of the analysis: 

**Goal 1**:
Find the most interesting house offers for an imaginary client, a wealthy business man, in search for a spacius place to host ravish uptown parties. Since money is not a constraint, he has his eyes only on the most exclusive properties in the Seattle area. The client has a particular appetite for modern buildings and a waterfront view is a must. There is should be no less than 2 bedrooms and 2 bathrooms. The living_sqm space is to be maximized and more important than purchase price.

**Goal 2**:
Construct a linear regression model to predict the housing prices using a selection of the most relevant features. The aim is to achieve an r-square above 0.7. 

**Goal 3**:
Optimize the model accuracy to minimize the RMSE

Throughout the analysis, I will closely follow the typical data science lifecycle and cover all areas from data mining, to data cleaning, feature engineering, modelling up to the visualization. 

## 2.  Data Mining:**

Now that the targets are defined, I will begin by loading the data and taking an initial look at the respective features

*Column Names and Descriptions for Kings County Data Set*
  * id - unique identified for a house
  * dateDate - house was sold
  * pricePrice - is prediction target
  * bedroomsNumber - of Bedrooms/House
  * bathroomsNumber - of bathrooms/bedrooms
  * sqft_livingsquare - footage of the home
  * sqft_lotsquare - footage of the lot
  * floorsTotal - floors (levels) in house
  * waterfront - House which has a view to a waterfront
  * view - Has been viewed
  * condition - How good the condition is ( Overall )
  * grade - overall grade given to the housing unit, based on King County grading system
  * sqft_above - square footage of house apart from basement
  * sqft_basement - square footage of the basement
  * yr_built - Built Year
  * yr_renovated - Year when house was renovated
  * zipcode - zip
  * lat - Latitude coordinate
  * long - Longitude coordinate
  * sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
  * sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors
  
  Loading the data and using the `info.()` command yields the following overview. 
  ![alt text](/Users/tobiasseidel/Projects/First_Project/2020-ds-Project-EDA/Bildschirmfoto 2020-09-17 um 00.36.11.png)
  
  
