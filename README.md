# Real-Estate-Prices-in-King-County

This document will cover an extensive exploratory data analysis using the King County Real Estate dataset. 
The main objective of the exercise was to preprocess the data to create an accuracte (multiple) linear regression model. 
I placed major emphasis on the feature engineering aspect, where I used the latitude and longitude coordinates to create neighborhood classifications to improve the model. The result of thise reverse geoengineering was two-fold: 

1. Adding the city feature significantly improved the accuracy of the regression model 
2. It brings the data alive as city district names are much more relatable than zipcodes

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
  
  
  
## 3. Data Cleaning 

In this section, I first replace all missing values either through median calculations or 0s. Next, I convert incorreclty classified data types and categorize the features. Lastly, I will determine and remove major outliers.

## 4. Feature Engineering

Now for the fun part! As they say, real estate prices are about location, location, location! So it is time to make something useful out of the latitude and longitude data as well as the zip codes.
I will begin this chapter looking at where King County is and plotting the lat and long data on a graph and continue be using the `reverse_geocode`libary to create a new column with city names. Using this feature, I am able to provide interesting recommendations to the imaginary client as of goal1. 

![image]('Boxplot.png')

**Recommendations:**
* *Maximizing space for price:*
    * The homes in Burien have both the lowest price per living and lot square meter while offerings the largest lot size under satisfaction of all other criteria

* *Total exclusivity:*
    * Mercer Island and the Sammamish region are a level above all other regions both in absolute prices as well as prices per square meter

* *Finding the best of both worlds:*
    * Get more for your money in Byrn Mawr-Skyway which offers better prices for large homes with decent lot sizes in the city center
    
## 5. Model Prediction

As mentioned, the focus of this section is to set up a simple linear regression and then gradually add complexity.
For the multiple regression model, based on the previous analysis I have selected the following features:
  
  **Categorical**
   1. city # added feature
   
  **Numeric**
   1. basement_sqm # less correlated with the other numerical features
   2. grade 
   3. waterfront
   4. view 
   5. floors
   6. bedrooms
   7. bathrooms
   8. renovated
   
  **Omitted**
   1. above_sqm 
   2. living15_sqm
   3. yr_built
   4. zipcode 
   5. lat
   6. long
   7. zipcode 
   8. condition # high correlation to other features
   
## 6. Conclusion and Visualization of Results

Using the geographical feature 'city' the model achieved an r-square of 0.79. 
While this could certainly be improved, it offers a solid starting point for the road ahead. 

![residual plot]("/Users/tobiasseidel/Projects/First_Project/2020-ds-Project-EDA/Residual Plot.png")

