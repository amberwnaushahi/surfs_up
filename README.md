# Surfs_Up

## Overview

This project uses Advanced Data Storage and Retrieval techniques to analyze the the temperature trends in Oahu, Hawaii for the months of June and December based on weather data to determine if a prospective surf and ice cream shop business can sustainably operate throughout the year. To analyze Hawaii's weather data, SQLAlchemy was used to query the SQLite database.

Data for the months was filtered through the following queries:

june_temps = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date) == 6).all()

dec_temps = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date) == 12).all()

The results from the query were then converted into a list, which was subsequently created into a Dataframe. Summary statistics were then generated using the describe() function. 

## Results

The following summary statistics were generated from the describe() function:

![image](https://github.com/amberwnaushahi/surfs_up/blob/main/Resources/Stats%20Comparison.png)

* The average recorded temperature in June is about 5% higher than December ( 75F versus 71F).
* The standard deviation of June tempratures is lower than December, pointing to a lesser skewed bell-curve than December and lower variations in temperatures. 
* The differential of minimum and maximum temperatures is higher in December versus June, indicating a higher variance.

## Summary

While at first glance it may seem that December temperatures vary more than December, the actual numbers themselves are indicative of favorable weather conditions at both times of the year. The difference in average temperatures in June and December is only 4 degrees. However, before making a final decision based only on temperature data, some additional queries should also be run to check other weather conditions and statistics:

* Variances in other weather statistics such as wind and precipitation, that would be correlated to surfing and consuming icecream, should be identified to understand patterns and determine customer footfall
* Summary statistics can be observed for each station in these months. This can help determine where in Oahu, geographically, can the business be potentially built (somewhere with least variations etc)

