# LP-One-Project
A Data Analytic Project On the Indian Startup Ecosystem
# Introduction

The Indian Startup Ecosystem is the third largest in the world and this is a feat which did not happen by mere chance rather through planning, innovation, and supportive government interventions through the Startup Indian Initiative. The Ecosystem is made up of businesses from various sectors, in different locations, funding stages and intricate profile of the companies involved.
The period between 2018 and 2021 was particularly fascinating for the Indian startup scene. This era witnessed a confluence of factors that shaped the landscape, including regulatory changes, technological advancements, economic shifts, and societal dynamics. Startups across various sectors, including technology, e-commerce, healthcare, fintech, and more, made significant strides during this time. 
Understanding the key parameters that enabled these ventures to thrive is essential for those seeking to embark on their entrepreneurial journey within this ecosystem.
 For a new business looking to penetrate the India startup ecosystem there is the need to investigate the existing systems with the help of available data and know how feasible and appropriate it will be in other for the business to thrive, this is what the project seeks to know and achieve.

# Project Structure
Four data sets from the year 2018 to 2021 were provided and it comprised of the following column Amount, Sector, Headquarters, Company Name, Founded Year, About the company, Investors, Founders and Stage.
Importation
The libraries or tools required for this project are listed below:
import pandas as pd
import numpy as np
import pyodbc
from dotenv import dotenv_values
import warnings 
warnings.filterwarnings('ignore')
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.impute import SimpleImputer

# Loading the dataset

The 2018 dataset was retrieved from the the Azubi Africa github repository, the 2019 data set was downloaded from the Azubi Africa OneDrive whiles the 2020 and 2021 datasets were stores in a database that had to be accessed using credentials provided and stored in an .env file  and a gitignore was created and the datasets were retrieved from the database connector pyodbc.
Exploratory Data Analysis 
To gain insight and understanding of the various datasets some Pandas functions were used, these are: 
.shape() for checking the number of rows and columns. 
.info() probing for further information about the columns 
.duplicate () checking for the duplicate values
.unique ()to check for the different values in the dataset.
.isna().sum() used to checked for the missing values
.head() to view the rows and columns
.describe () used to get the descriptive statistics of the datasets.

Having done this, there were a lot of data quality issues observed from the datasets, below are some outstanding ones.
Missing data, duplicate values, columns having the wrong datatype eg the Amount columns having object values, inconsistent column names, Amount columns containing different currency symbols, the stage column having NAN values, the columns 10 in the 2020 data set which played no role , these are to mention a few of the data quality issues realized. 

# CLEANING AND MERGING THE DATA
Before merging the four data sets a thorough cleaning had to done in other to address the data quality issues. 
The following steps were taken to clean the datasets: 
Duplicate values were dropped, the Industry column was well defined, the location column which had country, state and city names were streamlined to contain only the city names. 
An assumption was also adequate regarding the Amount column where Amounts in Rupees were converted to dollars, the currency symbol was stripped off and the empty fields replaced with 0; all Amount values are addressed in dollars. 

The data type of the Numeric values which had their .dtypes as objects were all converted to float values, missing values in the Amount column were dropped, renaming of the columns in othere to ensure uniformity.
 These are a few data cleaning done on the individual datasets.

The data was then merged however there were still issues with the merged datasets and the following actions were taken:
Missing values in the Amount column were dropped. 
Null values in the stage column were replaced with unknown. 
Null values in the Headquarters column were replaced with unknown. 
Null values in the Industry column were replaced with unknown. 

# Analyzing the Questions 

# Which Top 5 Industries have the highest funding?
The clustered bar chart shows the distribution of funds in the various industries over the period. 
For a startup looking to venture in the Indian Startup Ecosystem this information is extremely useful as it helps to identify the industry that tends to receive a lot of funding which ultimately translates in the growth and profit margins.

# Which Year Had The Highest Funding 
The above chart shows the year with the highest funding and shows the continued interest of investors in the Indian Startup Ecosystem. From funding of 7bn in 2018 to to 180bn 2021 which shows more than 85% growth in the Startup system one can be rest assured of experience tremendous growth and available funding should other important aspects of the business be maintained well.

# Which Top 5 Headquarters had the highest funding. 
Location of every business plays a vital role in the various aspects of the business, eg the access to urban population etc . Mumbai which is the capital city of India and houses a number of startups received the highest number of funding in the amount of 228bn. According to this data provided the location of the startup headquarters greatly influences the funding received so for startup looking to venture into the Indian Startup Ecosystem and looking to receive some good funding , the location of the startup should be made priority. 

# How many companies received funding every year?
Between 2018 and 2019, there was a notable drop in the quantity of startups that obtained investment from investors. Between 2019 and 2021, there was an exponential rise in the number of businesses receiving investment.

# Which top 10 sectors had the highest number of startup?
As an investor wishing to enter the ecosystem, one of these industries should be your goal in terms of where you will be investing. Additionally, the demands of the populace dictate where start-up owners venture. These charts highlight the leading industries in the India Startup
 Ecosystem.

# Find the maximum amount invested in sector Fintech in each year

It is prudent to find out how much money is invested in the FinTech industry, which leads the way in both funding and startup counts. With $1,000,000 invested in 2018 and a consistent rise over the years, it is encouraging to invest in the fintech sector because it appears to be growing at an exponential rate.


 

 
