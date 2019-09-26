# Taxi-Demand-Prediction-in-New-York
Check documentations in detail inside the code files
Taxi Demand prediction of yellow cabs in different areas in NEW YORK
The taxicabs of New York City are widely recognized icons of the city and come in two varieties: yellow and green. 
##### In this case study, for a given location in New York City, our goal is to predict the number of pickups in that given location at
##### particular time interval. Some location require more taxis at a particular time than other locations owing to 
##### the presence schools, hospitals, offices etc. The prediction result can be transferred to the taxi drivers via Smartphone app,
##### and they can subsequently move to the locations where predicted pickups are high.

#### Objectives:
##### Our objective is to predict the number of pickups as accurately as possible for each region in a 10min interval. We will break up 
##### the whole New York City into regions, that we will discuss later in the blog. Now, the 10min interval is chosen
##### because in NYC one can commute 1 mile in approximately 10 minutes given the traffic is normal at that particular time.

#### Source- Data can be downloaded from here: https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page

##### Our data is very large in size. A single “csv” file is of more than 1GB in size, therefore loading all of the data at once
##### using “Pandas” library will take up all of the RAM, and subsequently it will throw memory error. In order to overcome this 
##### problem, we are using dask library. Dask library is extremely useful library to use, particularly when we have data size larger
##### than the RAM size. Dask does simple optimizations so that we can operate on data larger than the RAM size. Instead of loading all 
##### of the data at once in a RAM, dask load blocks of a file into RAM. It loads only those blocks of file that are required right now. 
##### As soon as the processing on the currently loaded block is done, it empties the RAM and load another block of file. 

##### Here, I have divided whole NYC into regions using “K-Means Clustering”. Here, big questions comes
##### that what will be the optimal number of clusters. Now K- Means has a property that it creates clusters roughly of same size.
##### Here, size refers to the number of points and not the area. Now, the Manhattan area of NYC has large number of pick up, so cluster 
##### size in Manhattan area will be small as compared to outskirts areas of NYC where cluster size will be large.
##### We want the minimum inter cluster distance between any two clusters to be at least 0.5 miles and when the number of clusters are
##### 30 then this condition is almost meeting. Therefore, we are considering number of clusters to be 30.
Source: https://blog.goodaudience.com/taxi-demand-prediction-new-york-city-5e7b12305475
