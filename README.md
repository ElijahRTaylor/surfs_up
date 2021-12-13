# surfs_up

For this part of the Challenge, write a report that describes the key differences in weather between June and December and two recommendations for further analysis.

The analysis should contain the following:

## Overview

In an effort to provide our stakeholders with more information about temperature trends in Oahu before opening the surf shop, we are asked to provide them with  temperature data for the months of June and December in Oahu.  They're hoping to use this data to determine if the surf and ice cream shop business is sustainable as a year-round business.


## Results:

From doing our analysis on the temparature data for Oahu in the months of June and December, we got the following results.

1. During the month of June, the temparature in Oahu was on average around 75 degrees with the minimum temp being 64 degrees and the maximum temp being 85 degrees.

<img width="1143" alt="Screen Shot 2021-12-08 at 10 57 46 PM" src="https://user-images.githubusercontent.com/87248687/145332010-bef1ce3f-9d0c-40ae-8b06-7425ae4992b3.png">

2. During the month of December, the temperature in Oahu was similar to that of June.  The average temp was around 71 degrees with the minimum temp being 56 and the max being 83.

<img width="1139" alt="Screen Shot 2021-12-08 at 10 56 56 PM" src="https://user-images.githubusercontent.com/87248687/145331940-7749c4e2-121d-42ce-b56f-89cd05be6aaf.png">

3. We had a total of 1700 recorded temparatures being recorded in June months and 1517 temperatures recorded in December  months.


## Summary:
Based on the results of the analysis, we can see that the temperature in Oahu does not have major differences between June and December.  There's only a difference of 4 degrees between the average temperature in June and December.  It would also help if we also performed a query to gather the precipitation data during those months.  We could do so by using the below query for June and then updating it for December.
```
june_precip = session.query(Measurement.date, Measurement.prcp).filter(extract('month',Measurement.date) ==6).all()
for x in june_precip:
    print(x)
```

Another query we could potentially provide is to filter by most active station ID number as well as filtering by the month (June (6) or December(12))
One may feel that using the data from the most active weather station may provide more accurate and trusted results.

```
results = session.query(Measurement.tobs).\
filter(Measurement.station == 'USC00519281').\
filter(extract('month', Measurement.date) == 6).all()
```
