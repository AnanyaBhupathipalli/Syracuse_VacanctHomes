**Objective:** To predict vacant houses in Syracuse

**Data:** Collected data mainly from three sources:
  1. Syracuse Crime Data (2017) - [Type of Data: Block Level Data] (Refer to nygeo2010.7z)
  2. Syracuse Vacant Property Data (2017) - [Type of Data: Parcel Level Data] (Refer to nygeo2010.7z)
  3. US Census Data (2010) - [Type of Data: Block Group Level Data] (Refer to 2017.1-2018.1.csv)
<br> Since the 3 datasets are at different levels, they need to be merged to perform analysis and build prediction models.

<br> **Data Pre-processing - Merging the Data:** <br>
To perform analysis, first filter the Census data to only reflect census for Syracuse city. Since the data is on block-group level and does not have any column for city, it cannot be directly filtered with city names. To filter it, follow this steps in this R file -> (Filter US Census to Syracuse level.R)
Then, merge the crime data with the vacancy property data. Then, find latitude and longitude for the addresses of the merged dataset. (LatLong.csv and vacany_crime_merging.R)
To obtain the final dataset, used KNN algorithm to assign latitude, longitude points of the US Census data to the nearest latitude, longitude points of the merged dataset. (Merging_GeoLocation.R, TargetExcel.csv)
<br> **Data Cleaning and Analysis:** <br>
Performed final analysis on this merged dataset by selecting the important and relevant columns. (Refer to FinalAnalysis.R and finaldata.csv file). <br>
This involved data cleaning, using exploratory data analysis and apriori algorithms to choose columns for final analysis. Then applied Naive Bayes, Logistic Regression and Random Forest to build prediction models.

**Interpreting Results obtained from modeling different algorithms:** <br>
Random Forest - More the number of open violations higher the probability of land being vacant. Landuse is another important predictor. <br>
Apriori - If number of open violations are more than 2 and water services are inactive, higher is the probability of land being vacant. <br>
Logistic - When the Assessed Value of the property is moderate i.e. between the price range of $75000 and $2000000, there are higher chances of the property being vacant. <br>
Odds for very old buildings (before 1900’s) to be vacant is 139% higher than odds of a new building (1976 - 2017) being vacant. <br>
Odds for old buildings (1975 - 1900’s) to be vacant is 120% higher than odds of a new building (1976 - 2017) being vacant. <br>
For a unit increase in open violations, there is an 18% increase in the odds of a building being vacant. <br>



