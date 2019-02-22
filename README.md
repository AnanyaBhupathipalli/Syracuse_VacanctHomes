**Objective:** To predict vacant houses in Syracuse

**Data:** Collected data mainly from three sources:
  1. Syracuse Crime Data (2017) - [Type of Data: Block Level Data]
  2. Syracuse Vacant Property Data (2017) - [Type of Data: Parcel Level Data]
  3. US Census Data (2010) - [Type of Data: Block Group Level Data]
<br> Since the 3 datasets are at different levels, they need to be merged to perform analysis and build prediction models.
<br> **Merging the Data:** <br>
To perform analysis, first merged the crime data with the vacancy property data. Then, found latitude and longitude for the addresses of the merged dataset. 
To obtain the final dataset, used KNN algorithm to assign latitude, longitude points of the US Census data to the nearest latitude, longitude points of the merged dataset. 

Performed final analysis on this merged dataset by selecting the important and relevant columns. (Refer to FinalAnalysis.R file)
