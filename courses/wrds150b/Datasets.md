## Dataset Criteria
- Should be raw data for you to conduct analysis
- Require at least 30 data points / rows
- Statistics for provinces / territories will be problematic since there are less than <30 provinces, but for each state in US, data for each country ...


## Datasets
- **Dataset Links**
	- Monthly unemployment rate for each country: https://data.oecd.org/unemp/unemployment-rate.htm
        - Percentage of people unemployed in the labor force
        -  $rate = (\text{Number of people capable of working \& are unemployed}) / (\text{Number of people capable of working})$
    - Population distribution across different countries: https://population.un.org/wpp/Download/Standard/Population/
	- Daily cases of COVID-19 for each country: https://covid19.who.int/WHO-COVID-19-global-data.csv
- **What knowledge can be produced?**
	- Correlate percentage of population infected with COVID-19 to unemployment rate
- **Relevant variables / Nature of variables**
	- Location - Qualitative
	- Number of covid cases by country and time - Quantitative
	- Unemployment rate by country and time - Quantitative
    - Population by country - Quantitative


## Analysis Strategies
- Merge cumulative covid-cases and unemployment rate by the start of each month from 2020-2021
    - Compute correlation
- Correlate unemployment rate with percentage of population infected from 2 months earlier
$$
\text{Correlation Coefficient} =
\frac{\sum (x_i - \overline{x})(y_i - \overline{y})}{\sqrt{\sum (x_i - \overline{x})^2\sum (y_i - \overline{y})^2}}
$$