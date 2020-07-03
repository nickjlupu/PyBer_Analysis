# PyBer Analysis Report

## Background and Results

### Purpose
The purpose of this project is to demonstrate the data visualization techniques in matplotlib.  As usual in this course, the weekly challenge builds upon the code that was developed throughout the modules for the subject matter in question.  

### Technical Analysis
The analysis begins with 2 csv files.  The first contains data of city names, number of drivers, and type of city.  The second contains city names, date & time, fare, and a ride ID.  These files are read into pandas dataframes and inspected to determine if there are any missing values by using the isnull function.  <br>
![](analysis/ReadCSV.png)
![](analysis/isnull.png)

Once the datasets are inspected and explored, they are combined with the pandas merge function.<br>  
![](analysis/merge.png)

After the dataframes are merged, we can subset the data into additional dataframes and use the groupby function to gather counts and means that will be used as the x & y axes for scatter & bubble plots.<br>
![](analysis/subset.png)
![](analysis/countsmeans.png)

Assembling all of the bubble charts together provides an appealing approach to review multiple sets of data at once.
**Fig. 1:**<br>

![](analysis/Fig1.png)

From here we begin to look at summary statistics and develop box and whisker charts for ride counts, fares, and driver counts.  These charts are helpful in visualizing central tendencies, spread, and outliers in one image.  
**Fig. 2:**<br>

![](analysis/Fig2.png)

**Fig. 3:**<br>

![](analysis/Fig3.png)

**Fig. 4:**<br>

![](analysis/Fig4.png)

Pie charts are developed to show percentages of total fares, number of rides, and number of drivers by city type.  
**Fig. 5:**<br>

![](analysis/Fig5.png)

**Fig. 6:**<br>

![](analysis/Fig6.png)

**Fig. 7:**<br>

![](analysis/Fig7.png)

A summary dataframe is built, formatted, and displayed.  Finally, a multi-line chart is developed by organizing the data using pandas pivot_table and resample functions to create weekly bins of data.  A great deal of formatting was done to create an attractive chart.  

### Results & Summary
As expected, there are fewer rides and fewer drivers in the rural and suburban areas as compared to the urban areas.  Average fares increase as we move away from the urban areas since the rides in suburban and rural areas tend to cover greater distances.  <br>

**Fig. 8:**<br>

![](analysis/Fig8.png)<br>

As

**Fig. 9:**<br>

![](analysis/Fig9.png)


### Summary






## Challenges Encountered and Overcome

### Challenges and Difficulties Encountered

* Programming:  One of the largest programming challenges for me was researching and discovering the pandas pivot_table function.  This was used to reconfigure the dataframe to set up the weekly bins by city type that would be used for plotting the multi-line chart.<br>

![](analysis/PC2.png)

* Programming:  Another challenge was figuring out that I did not need to "unpack" the Date column from the index in order to change its datatype to datetime.  This was accomplished with the code below.<br>

![](analysis/PC1.png)

* Data analysis:  Once the datasets are merged, the number of drivers for each city is duplicated throughout the dataframe (i.e. each instance of a city will show the number of drivers).  To overcome this, we must use the city data dataframe to calculate the total number of drivers per city type.  If the programmer does not recognize this, there will be a large error in the results.<br>

* Graphing, etc:  A lot of time was spent formatting the multi-line chart.  My largest challenge in this area was uncovering how to change the format of the timestamp x-axis labels to simply show the month abbreviation.  I discovered matplotlib.dates and, after reading some of the documentation, was able to use the DateFormatter to get the desired format.<br>

![](analysis/PC3.png)


## Recommendations and Next Steps

### Recommendations for Future Analysis

### Additional Analysis 1

* Description of Approach
As shown in the boxplots of Driver Counts, there is a lot of variation in the number of Urban drivers (see Fig. 4 above).  Which cities have the most drivers?  How do ride counts and total fares stack up to the number of drivers by city?  

* Technical Steps
Create bar chart for driver count by city
Format and sort to show city with highest driver count to lowest
Look in the Urban cities dataframe, groupby city, sum fares
Create bar chart for total fares by city
Look in the Urban cities dataframe, groupby city, count rides
Create bar chart for total rides by city
Combine bar charts and format accordingly (investigate multi-axes charts)
Depending on outcome, use average fare instead of total fare

### Additional Analysis 2

* Description of Approach
In order to optimize the number of drivers, we should look at the pattern over time that the number of drivers follow.  Do the number of drivers follow the same trend every week?  every day?  Unfortunately, the data provided only shows a static number of drivers per city.  If we are to ascertain the staffing level of drivers over time, we would need to have data on the number of drivers at the time of each ride.

* Technical Steps
Request data tracking 
Receive csv's, read into a dataframe
Inspect for missing data and explore data provided
Merge datasets if necessary
Groupby cities
Set index to datetime
Create pivot table to show data over time by city
Resample data to create weekly and then daily bins
Plot data on multi-line chart
