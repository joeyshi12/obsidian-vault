- [[Datasets]]
- [[Sources]]


## Research Proposal
**Study A** uses the Fourier causality test to determine whether the number of COVID-19 cases causes a change in the unemployment rate in European countries. 
~~Study B assesses damages in various sectors (aviation, tourism, and retail) due to pandemic restrictions over time within Canada (won't use)~~
**Study C** correlates COVID-19 cases and unemployment and other socioeconomic factors in Norway
**Study D** investigates damage from anti-pandemic measures on unemployment rate in Slovakia. 

**Study A** finds that the number of COVID-19 cases causes unemployment in Germany, Italy, and the UK
~~Study B finds that ~~
**Study C** finds that low income groups (specifically immigrants) in Norway were highly correlated with number of COVID-19 cases ()
**Study D** finds 2-3% increase in unemployment compared to it's trend before the pandemic in Slovakia

Studies in the past have investigated the relationship between the number of COVID-19 infections and deaths and the unemployment rates in certain countries over time (Study A, B, C). Study A aims to determine whether the number of COVID-19 cases causes changes in the unemployment rate for certain European countries. Similarly, Study B also explores this relationship by observing the correlation analysis in another European country: Norway. Lastly, Study C assesses changes in unemployment rate due to the  COVID-19 pandemic by observing the differences between the trend of Slovakia's unemployment rate before the COVID-19 pandemic and the reported unemployment rates during the COVID-19 pandemic.

These studies 
using 
In particular, this paper aims to 

Many of these studies have investigated the association between the number of COVID-19 cases and unemployment rate over time in different European countries.
However, some critical questions remain: is there an association between number of COVID-19 cases and unemployment rate over different countries across the world. 



We will use the unemployment rates from the OECD database during the period of January 2020 to January 2021.
Each row in this dataset represents a country at the beginning of each month.
We will be primary focusing on the unemployment rate column.

We will also be using the daily COVID-19 cases reports from the WHO.
Each row in this dataset represents a country on a day during the period of January 2020 to the present.

We will also be using the international population distribution reports from the UN.
Each row represents a country or region's population over different years. 

Procedure:
- average covid cases in Jan 2020 - Jan 2021
- normalize the average number of people infected with COVID-19 as a percentage of people infected in different countries.
- Run correlation between percentage infected and covid-19 cases for each country


We will find the Pearson correlation coefficient (D) between the number of COVID-19 cases and unemployment rate at the beginning of each month across different countries around the world.


Study A: https://www.tandfonline.com/doi/full/10.1080/1331677X.2021.1912627
Study B: https://onlinelibrary.wiley.com/doi/full/10.1111/cjag.12288
Study C: https://journals.sagepub.com/doi/full/10.1177/14034948211015860
Study D: https://www.ceeol.com/search/viewpdf?id=1007580
Correlation coefficient interpretation: https://ovidsp.dc1.ovid.com/ovid-a/ovidweb.cgi?ID=shib%3Adc1%3A0x390f76670472413e91907893f3168729&PASSWORD=0x390f76670472413e91907893f3168729&CSC=Y&T=JS&D=ovft&SEARCH=0003-2999.is+and+%22126%22.vo+and+%225%22.ip+and+%221763%22.pg+or+%2210.1213%2FANE.0000000000002864%22.di&NEWS=N&PAGE=fulltext&entityID=https%3A%2F%2Fidp.ubc.ca%2Fopenathens 
Unemployment rate definition: https://data.oecd.org/unemp/unemployment-rate.htm