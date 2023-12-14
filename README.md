# 458_Project
A project for my BUS 458 honors class at NC State. Here we are given Kaggle survey data, in which we clean, model, and drive insights and decisions. We also create a dashboard model to give out a predicted salary.

# File Library
kaggle_survey_2022_responses (1).csv -- Original Data Set
kaggle.csv -- Initial cleaned-up data set via excel. Took our most deemed important variables and renamed columns
kaggleContinuous.csv -- Final data set. Cleaned up data typings, reworked our predictor variable (binned to continuous), and imputed the missing predictor values
458 FInal Project.Rmd -- the R Markdown file with our data cleaning and data modeling
458-FInal-Project.html -- an HTML output of the R Markdown file
Analytics Insights.pptx.pdf -- Our presentation. Note: We could not present this in person, so information is overloaded on the slides.
https://analyticsdashboard.streamlit.app/ -- Our deployable model

# Project Basis
To put our learnings into application, we decided to create a linear regression model to predict data scientist salaries based on factors such as one's education, type of industry you work in, what languages you know, which machine learning repos you currently use, and much, much, more. To make sure we create a strong model, we removed variables we deemed to have no significance in predicting salary, as well as variables that inflated the variance between all other variables as well. 

We also changed our predictor variable, Compensation/Salary, from a binned variable, to a continuous variable. To do this, we used a random number generator function in R that assigns numbers to values within that bin, giving us a perfectly distributed bin. This means our mean/median is equal to the bins median (ie. bin 1,000 to 3,0000 should have a median of 2000, output is a mean/median of 2000). From this, we used MICE to impute the missing values. Instead of sacrificing 2/3rd's of our data, or 16,000 data points, we salvaged it all. 

We also removed outliers, which boosted our R^2 from .21 to .42, and the reduction of some variables moved it up to .48. I did get it up to .52, but that model is not deployed due to assignment questions.
