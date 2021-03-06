# PyBer_Analysis

## Purpose
  For this project, I was tasked with performing an analysis for PyBer, a python-based ride sharing app company, in which I was given two datasets. The datasets contained information for the type of city and the number of drivers and rider data. Merging the datasets into one allowed me to prepare visualizations that could illustrate the relationship between the datasets. Matplotlib is a graphing and plotting library for Python. Importing the Matplotlib library into jupyter notebook, is a useful tool to be able to create multiple chart types, for example, line, bar, scatter, or box and whisker plots. 

## Overview Of Analysis 
  The PyBer company wanted me to create a multiple-line graph, which would show the total weekly fares for each city type, and a summary report of how the rider data differed by city type. The city types being evaluated were in Urban, Suburban, and Rural areas.A visualization of the total weekly fares for each city type would make it easier to see the weekly fares for all 3 city types in one line chart, versus, looking at the total weekly fares of each type in 3 different charts. 
  
  By compiling the data into one graph, one can make a determination of the differences in rider count per city type in one glance, and it would also make easier to see how the total fares differed by city type on a weekly basis. This is why a multiple line graph was chosen, because it could provide all of this information on one graph. This information would allow PyBer to be able to see whether they needed to increase the access to their ride-sharing services and to help determine how affordable their app services are in different city types. 

## Resources 
* Data Source: city_data.csv, ride_data.csv
* Python 3.9.12, Anaconda 4.13.0 (Jupyter Notebook, Pandas Library, Matplotlib)

## The Data
  First, I had to determine total rides, total drivers, and total fares for each city type, which was done using the groupby() function, (Fig. A). Following those determinations, a mathematical equation was used to determine the average fares per ride, and average fares per driver, (Fig. B). 

Fig. A)
![groupby_total_ride_drivers](https://user-images.githubusercontent.com/104864579/178854884-dd907ed3-3594-42cd-8db7-4e30ac211cf4.png)

Fig. B) 
![math_calc_avg_fare_driver](https://user-images.githubusercontent.com/104864579/178854866-5e83e594-c47c-466f-bc53-d3978c17297c.png)

  The results of what was found, using the groupby() function and the averages fares calculations, were used to create the names of my "Columns" that would be separated into city type, upon creation of a new pandas DataFrame, pyber_summary_df, (Fig. C). Following a couple formatting changes to the column titles and the results provided in those columns, a table was produced that I could use to create my multiple line graph. 

Fig. C)
![columns_pyber](https://user-images.githubusercontent.com/104864579/178855084-6f79a033-74c8-4abb-b16f-846b36f8b177.png)

  Using the pyber_data_df dataframe, I created another dataframe, pyber_pivot_df (Fig. D), using the groupby() function again to show the sum of the fares for each date where two indices were used, date and city type. Then I used a reset_index() function, (Fig. E), to restart the index numbers of the data, so that I could create a pythonic pivot table. The reset_index() function was used so that I could use the pivot() function in the following steps of my python script. 

Fig. D)
![pyber_pivot_groupby](https://user-images.githubusercontent.com/104864579/178855156-4d67008c-1e08-40c5-8458-18f920e38dbd.png)

Fig. E)
![reset_index_pivot](https://user-images.githubusercontent.com/104864579/178855109-dba705b2-69b7-4a11-8c21-8fec9bcf96f8.png)

  Then I used the loc[] method to group together the given dates between January 1, 2019 and April 29,2019. The datatype for the dates had to be set to a datetime datatype, so that I was able to use the resample() method. The resample() function was used to be able to get the sum of the fares for each week (Fig. F), which would make the multiple line graph easier to read. By resampling the data to plot points by week, a line graph could be created to show line trends of each city type over the course of a four month period. 

Fig. F)
![resample_weeks](https://user-images.githubusercontent.com/104864579/178855191-603e1b58-5c90-49fe-bdeb-3125ea1fdf92.png)

  Now that all of the data was set up properly in a pivot table using python, I had to import a styling module from matplotlib, which would allow me to format my multiple line graph, add x- and y- axis labels, a chart title, and the ability to save the figure in an image (Fig. G). 

Fig. G)
![matplotlib_chart_format](https://user-images.githubusercontent.com/104864579/178855224-7772b5ca-2cf7-4a69-ad0d-99f5813b8c42.png)

## Results

  Based on the results of the pyber_summary_df (Fig. H), it can be concluded that there is a trend between the city type populations and the total number or rides given, as well as, the number of available drivers for each city type. 

Fig. H)
![pyber_df_summary](https://user-images.githubusercontent.com/104864579/178855250-95660a8e-73fd-4e7d-9350-06d67ba2751c.png)

  The "Urban" city type had the highest amount of rides given, and that positively correlated with the total drivers available, which had the highest driver count compared to the other two city types.

  The "Rural" city type showed a negative correlation because the lower the driver count, the lower the amount of rides given, which resulted in lower total fare amount. One reason could be that, travel time in rural areas probably takes longer in between one place to another, which can result in less rides able to be given by the drivers.

  Even though rural areas had the lowest total fares compared to suburban and urban areas, the average fare per ride and average fare per driver were higher than the other two city types. The high average fare prices could also be another reason that rural areas had the lowest total fares, total rides, and total drivers; in which prices increase as demand decreases. 

Fig. I)
![Fig8](https://user-images.githubusercontent.com/104864579/178855289-3d75d5f4-0701-45f4-a456-02829ab94137.png)

  The multiple line chart, "Total Fare by City Type" (Fig. I), might not provide as much detail as the data provided in the pyber_summary_df table, but what is seen in both the table and the chart, is that urban city types are the most profitable compared to suburban or rural city types. What the chart also shows is how the amount of profit for urban and suburban city types does flucuate from the months of January to April. The most profitable weeks for all city types seem to occur in mid-late February, while urban and suburban city types seem to be least profitable during the first week of January.



## Summary

  One business recommendation could be that they could increase the amount of drivers in rural areas during the weeks that had the highest total fare amount, which could lower the average prices, thus, influencing more riders in rural areas to use the PyBer ride-sharing app. Allocating more drivers during certain weeks for rural areas, could also increase overall profit margin while not losing money on weeks where less rides in rural areas are being taken.

  Also, the fact that the average fare per driver is so drastically different for each city type, could infer that driver allocation might need to be adjusted, and in this way, the average fares could be more evenly distributed among all city types. The company could increase the average fares in urban areas, to be able to decrease the average fares in urban and suburban areas, which could influence rural and suburban areas to use the ride sharing app more often, and increase overall profit for the ride-sharing app company. 

  Another could be to look into possible reasoning as to why all city type profits were highest in the last week of February and decreased substantially during the first week of March, for example, is there a special event that occurs where more people would need more rides one week versus the following week. 

 
