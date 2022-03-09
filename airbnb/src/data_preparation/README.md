# Data Exploration & Preparation: Elaboration choices 
## Content 
1. Data Exploration  
1.1 Explore data using summary statistics  
1.2 Detect the origin of missing values  
1.3 Determine outliers in the data  

2. Data Preparation  
2.1 Create new variables as reference to the quarterly data  
2.2 Delete unnecessary columns  
2.3 Rename variables "neighbourhood_cleansed" and "calculated_host_listings_count"  
2.4 Rescale the variable "review_scores_rating"  
2.5 Change the variable "price" to numeric  
2.6 Removing NA's from the dataset  

## 1. Data Exploration
### 1.1 Explore data using summary statistics
TEXT

### 1.2 Detect the origin of missing values
TEXT

### 1.3 Determine outliers in the data
TEXT

## 2. Data Preparation
## 2.1 Create new variables as reference to the quarterly data
As the data of 2021 is collected per quarter, and the purpose of this research is to compare different time periods, several new variables named "quarter", "year" and "year_quarter" should be created. By doing this, a distinction can be made between the different periods in time. 

## 2.2 Delete unnecessary columns
As this research focuses on the main question "Which types of rooms in which neighbourhoods benefited the most from the Corona Pandemic in the United Kingdom?", some variables in the original dataset might not be needed to come to an answer. For that reason only the following variables are kept in the dataset to maintain a clear overview of the variables needed for this research:
* id: Airbnb's unique identifier for the listing.
* city: The city in which the Airbnb is located. 
* quarter: The quarter in which the Airbnb is listed.
* year: The year in which the Airbnb is listed. 
* year_quarter: The year and quarter in which in the Airbnb is listed.  
* neighbourhood_cleansed: The neighbourhood in which the Airbnb is located. 
* room_type: The type of room the Airbnb offers. 
* calculated_host_listings_count: The number of listings the host has in the current scrape, in the city / region geography. 
* review_scores_rating: The overall rating of the Airbnb based on the review scores on a 0 to 5 scale.
* price: The price at which the Airbnb is listed.

## 2.3 Rename variables "neighbourhood_cleansed" and "calculated_host_listings_count"
The variable names of "neighbourhood_cleansed" and "calculated_host_listings_count" are not revealing much of what they stand for. Therefore, these two variables need to be renamed so that their names are informative by themselves:
* neighbourhood_cleansed is from now on referred to as neighbourhood_name
* alculated_host_listings_count is from now on referred to as num_host_listings

## 2.4 Rescale the variable "review_scores_rating"
During the data exploration it was observed that the range of the variable "review_scores_rating" was a bit out of proportion. By inspecting the data it becomes clear that the range of this variables has changed over time. In quarter 1 of 2021 the variable "review_scores_rating" ranges between 0 and 100. However, in the following quarters (2, 3 and 4) the variable "review_scores_rating" ranges between 0 and 5. This will lead to problems while analyzing the data. Therefore this needs to be taken care off by rescaling the variable.

## 2.5 Change the variable "price" to numeric
From the data exploration became clear that the variable "price" in this data is imported as a character. For further analyses the variable "price" needs to be changed into a numeric. Before this can be done the dollar sign and the comma for prices above thousand had to be removed. 

## 2.6 Remove NA's from the dataset
In the data exploration attention was paid to NA's (= missing values) in the data, specific for the variable review_rating_score, by means of plots and summary statistics. From the plots and summary statistics it remains unclear what the direct cause is of the missing values in the dataset. However, it is expected that the missing values of the variable review_rating_score are caused by guests or hosts that do not write a review. As the observations with the missing values cannot be used for further analyses, they have been removed from the dataset. 