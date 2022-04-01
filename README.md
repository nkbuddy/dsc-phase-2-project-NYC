Final Project Submission
Student name: Qilun Chen, Evan Serrano
Student pace: full time
Scheduled project review date/time: April/1/2022
Instructor name: Praveen Gowtham, Joe Comeaux
https://github.com/nkbuddy/dsc-phase-2-project-NYC
# Purpose
In this project, we are analyzing the data to answer a very simple question: What data feature related to home pricing should be the focus of developer/ builder/investorS?
# Data Pre-processing
We were provided housing data for home sales in King County, WA for the years 2014 and 2015. This data contains 21 columns of various datatypes. Some columns were objects that needed to be transformed. There was also an ID column that was strictly an identifier and contained no other pertinent information. We converted sqft_basement from object to float. All NaNs were dropped in the dataset as well as ID and date. Latitude and longitude were dropped as they were not particularly relevant to our analysis. Using ordinal encoding, we converted waterfront, view, condition, and grade to categories. We then created a function to drop outliers with a z-score greater than 3.49 which still leaves more than 99% of the data in each of the columns. 
# EDA
We created an initial heatmap to look at the correlation of the features to our target, which is price. We dropped Sqft_Above due to likelihood of multicollinearity issues. After analyzing the remaining features, we decided on Grade, Sqft_living, Sqft_living15 and created a scatter plot to graph linearity. We then drafted qq plots for the feature variables and obtain diagnostic statistics from the OLS regression results table
# Baseline Model
We created an initial model with independent variables of grade, sq footage of living space, and sqft_living15. Based on our R-squared score, only 48.5% of our results can be explained from the data. This is very low. Another model will have to be run, potentially with more/transformed variables in order to get a more trustworth result. Our Y-intercept and our coeff. for grade are very high meaning that some logging and/or more data transformations should be completed in oirder to create higher quality variables to insert into the model that can be easier to interpret. 
# Further data cleaning & Train-Test-Split
We observed histograms for the independent variables and log/scale as needed. The resulting scaled variables are heatmapped and checked for multicollinearity. We then recreated scatter plots to check for linearity with scaled variables. Updated qq plots. Zip codes were listed as integers when in reality they really contain categorical data. We used model.params to display the coefficients for each zipcode. We used Train-Test-Split to evaluate the model
# Conclusions and Recommendations
After running the second model we can confidently say that the variables zipcode, sqft_living, and grade are strong influencers of price in King County. According to this model, 83% of our results can be explained by the data from our chosen feature variables. To maximize home price: choose a house in a  favorable zipcode, with lots of interior space, made from quality materials that received a high grade from King County. 
