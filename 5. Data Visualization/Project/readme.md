<h1><center> Ford GoBike System (Bay Wheels) Communicate Data Findings Project</center></h1>

<h3><center>by Kueh Seow Teck</center></h3>

## Introduction

**Ford GoBike** System, now known as [**Bay Wheels**](https://en.wikipedia.org/wiki/Bay_Wheels) is a regional public bicycle sharing system in California's San Francisco Bay Area. The operation first begane in August 2013 as **Bay Area Bike Share**, then re-launched as **Ford GoBike** in June 2017 in partnership with Ford Motor Company. In June 2019, after the operatior Motivate's acquisition by Lyft, the system is renamed to **Bay Wheels**.

For this project, the system data is compiled by Lyft and is available for public use and can be download [here](https://www.lyft.com/bikes/bay-wheels/system-data). The data available for download are from 2017 till August 2020 as of now.

In general, each trip contains the data below:

- Trip Duration (seconds)
- Start Time and Date
- End Time and Date
- Start Station ID
- Start Station Name
- Start Station Latitude
- Start Station Longitude
- End Station ID
- End Station Name
- End Station Latitude
- End Station Longitude
- Bike ID
- User Type (Subscriber or Customer – “Subscriber” = Member or “Customer” = Casual)

## Python Libary used for this project

1. Pandas: for manipulating dataset
2. OS and glob: interacting with windows file path
3. numpy: for calculations
4. seaborn and matplotlib: for data visualization


## Files submitted for this project

Below are the list of files submitted for this project:

1. *readme.md* : General information about the project
2. *Exploration.html* : Exploratory data analysis codes and visualization
3. *Explanatory.html* : Explanatory anaysis codes and visualization
4. *Explanatory.slides.html* : Explanatory analsyis plots and summaries
5. Multiple .png files containing figures used in the htmls above.

## Data Wranggling

I have downloaded all the excel files for the Bay Wheel's trip data up to date and saved it into a folder named 'Files'.
I then read all the files and concat it into a dataframe and noticed that the excel files starting from April 2020 have different column names and a lot of missing data. So I have decided to only include data up till March 2020 for this visualization exercise.

### Preliminary accessment of the database

The cleaned database contains data for each trips taken by the users from 2017 till March 2020. The columns primarily can be devided into five categories: 

1. **Trip duration related data**: This category of data contains date and time related info for each of the trip such as *duration_sec* taken for each trip, *start_time* and *end_time* of each trip.
2. **Station related data**: This category contains string data for each trips such as the *start_station_name* and *start_station_id*, *end_station_name* and *end_station_id*, *start_station_latitude* and *start_station_longitude*, *end_station_latitude* and *end_station_longitude*
3. **User related data**: *user_type* which describes if the user is a subscriber to the service or just a regular customer
4. **Bike related data**: *bike_id* describes the unique identification number of the bike used for each particular trip
5. **Derived variables**: From the datetime objects, I also derived the *duration_min*, *start_date*, *start_hour*, *start_day*, and *start_month* to assist me with the data exploration and analysis process

### Points of interest

From the dataset, I would like to investigate the ride count distribution for a given time of the day, day of the week and month in a year. I am also interested in investigating the distribution of the total duration of each ride across a given time of the day, day of the week and month in a year. Other than that, I also would like to investigate the ride count distribution difference between the subscribed users and casual users. 
Below are some of the key questions:
- When is the ride most popular in terms of time of day, day of the week or month of the year?
- Who are the main customer group: subscribers or normal customers?
- What is the average trip duration?
- Does the count of usage of subscriber and customer users changes throughout a year?
- Does subscriber and customer uses the system similarly in terms of when they take their ride? 

## Exploratory Analysis

Three methods of exploration below are used in exploring the data:
1. Univariate Exploration
2. Bivariate Exploration
3. Multivariate Exploration

##  Summary from Explanatory Analysis

1. Duration spend on a ride for customer is longer than subscribers.
2. The peak usage period of this service during weekday for subscribers and customers are the same; which is at 8am and 5pm.
3. The total ride counts by month has a positive correlation with temperature.
