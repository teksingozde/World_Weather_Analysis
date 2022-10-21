# World_Weather_Analysis

## Project Overview
PlanMyTrip requested a program that will present weather information for cities that fall between the maximum and minimum values requested by its customers. In response to this program request; Weather, city and hotel information are collected by APIs. Subjects were asked to identify four places, provided that they were close to each other and in the same city, in accordance with their current data, suitable for their desired travel style, and were shown on the map.

## Resources
Data is obtained through its own Google Cloud Platform and OpenWeather API Keys. In case the hotel information cannot be provided, “WeatherPy_vacation_backup.csv “file is additionally provided to us so that we can add it to the analysis. However, its use was not required in this study analysis.

### Software:
- Python 3. 9. 12
- Jupyter Notebook 6. 4. 8
- Pandas 1. 4. 2
- Numpy 1. 21. 5
- Matplotlib 3. 5. 1
- CitiPy 0. 0. 5
- Requests 2. 27. 1  
- SciPy 1. 7. 3
- Gmaps 0. 9. 0

### Other Resources:
- OpenWeather – API Key
- Google Cloud Platform – API Key

## Overview of the Analysis

First, the weather file was studied, and many weather-related variables were examined thanks to the API Key created by OpenWeather. These examinations were made with the help of scatter plots.

Afterwards, vacation_search and vacation_itinerary files were examined with the API Key that we created via Google Cloud Platform.

WeatherPy allows us to generate coordinates by examining latitude and longitude on a large number of randomly generated numbers. To create a list of cities closest to these coordinates, Python uses the citipy module. In order to examine the weather data of these cities, the API Key, which is used through Google Cloud Platform, is used as stated at the beginning of the study. The weather data includes the maximum and minimum temperature, humidity, rain and cloud rate and wind speed, which are qualified for necessary investigations. Even though the temperature degrees are given in Fahrenheit, we have the opportunity to examine this information in detail on Google Map. Of course, in some cases, the necessary results about a city are not returned. In such cases, thanks to the "try-except block", we see that we have more than 500 cities to examine as a result of the necessary investigations. In our work, you can see the "cities.csv" file and four scatter plots in the weather_data folder. This study shows how the weather data is exported with the help of DataFrame and the obtained graphs show the maximum temperature, humidity percentage, cloudiness percentage and wind speed values of latitude degrees. Values refer to 10/19/2022 at 4:59 PM. Scatter plots give us information about whether there is a correlation between the variables. In the Fig1 distribution graph between latitude and maximum temperature, it was determined that there was a correlation, that is, a relationship between the variables. However, it is not possible to say that there is any relationship between latitude and values in other distribution charts.

## Overview of the Challenge 

In the Weather_Database study, we generated random coordinates, just like in the WeatherPy study. The closest cities to these coordinates were listed and we obtained the weather data of the locations with the help of OpenWeather API Key. This data is saved as "WeatherPy_Database.csv" in the Weather_Data folder.

In Vacation_Search work, a table is created with the WeatherPy_Database.csv folder and maximum and minimum temperature information is obtained from the user for this table. The minimum temperature value determined for this study is 75 and the maximum temperature value is 100. Since these values are not specifically stated, it may be more accurate to say that I preferred them to be within these ranges. In the table created for this study; The hotel name column is created at the end with cities, country, current weather information, latitude and longitude. With the help of Google API, the closest hotel to the location is listed. In some cases, hotels belonging to nearby locations may not be listed, and as seen in the study, those locations are cleared from the data set and a new list is created. This data set is saved as "WeatherPy_vacation.csv" in the Vacation_Search folder.

Based on the minimum and maximum temperature data in the Vacation_Itinerary study, necessary filters were made in the light of the data in the WeatherPy_vacation.csv file with the help of the Google Directions API key. What is requested from us is that the four points requested for the visit are located within the same region, provided that these points are close to each other. The way of traveling to these cities depends on the people, and there are options for driving, walking and bicycling. As a result of the necessary examinations made in the WeatherPy_vacation.csv file, it is seen that some countries do not have four regions. A departure and return route was created by choosing four cities from the French Guiana (country code GF) region in the French region. Traveling to these regions is preferred as walking. The first stop of the four regions is Sinnamary, the second stop is Mana, the third stop is Cayenne and the fourth stop is Iracoubo. This map is saved as "WeatherPy_travel_map.png" in the Vacation_Itinerary folder. The map with information about these points is recorded as "WeatherPy_travel_map_markers.png".


