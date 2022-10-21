# World Weather Analysis

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

## Results

### Table 1. Weather Database DataFrame
![Table 1](https://user-images.githubusercontent.com/26927158/197097660-fd4a185b-25c4-43c2-b182-f7184ddbaf07.png)

The table above contains the first 10 rows of data obtained via the OpenWeather API Key. When the table is examined; The columns contain city, latitude, longitude, maximum temperature, humidity, cloudiness, wind speed, country and current description values.
If we examine the city in the first place,
- The city name is Benguela,
- Latitude 12.5763 ,
- Longitude 13.4055 ,
- Maximum temperature value is 73.33,
- Humidity 79,
- cloudiness 69,
- Wind Speed 4.05,
- Country AO (Angola - Central Africa),
- Current Description is broken clouds.
It should be noted that the latitude and longitude degrees above are randomly generated with the help of the API Key, and the closest unique city to these latitude and longitude values is listed.


### Table 2. Vacation Search DataFrame
![Table 2](https://user-images.githubusercontent.com/26927158/197097777-dbe86710-eb5a-440a-82c5-e57113c3de03.png)

The table above shows the cities obtained using the Google Places API Key, based on the data set obtained with the help of Weather_Database.
Before this table, another table was created and it was seen that the hotel name was not included. This table appeared when the cities with missing hotel names were deleted from the table. If the table is to be interpreted, the first 10 rows of our data set are shown. In the table; The city name, the abbreviation of the country name, the maximum temperature, the current description, the name of the hotel closest to the city with latitude and longitude are displayed.


### Google Map 1. Vacation Search Markers
![WeatherPy_vacation_map_markers](https://user-images.githubusercontent.com/26927158/197097907-b70a4b41-d534-4ed1-8ff4-28bbf23cae45.png)

As seen on Google Map 1, the information of some points located at the determined locations on the map is shown. Each of these information is called a marker. First of all, although these locations are the locations in our data set, the state of markers is examined in terms of visualization. There are hotel names, city name, country, temperature and current description information of four regions that we have determined on a random map.
If more information is desired, selecting different points on the map will result in the same markers image.


### Google Map 2. Vacation Itinerary Travel Map
![WeatherPy_travel_map](https://user-images.githubusercontent.com/26927158/197098159-bd32d698-6890-4e13-8a4c-c4692b4d7b57.png)

In the table above, the travel table of the four cities we filtered from our own dataset is given. These regions are; Mana has been chosen as Cayenne, Sinnamary and Iracoubo. Walking is preferred as the mode of travel. These regions are located at close distances from each other and within the same region. While the city was located in France, the region was named French Guiana. In terms of population, it has been studied as sufficient for a touristic trip. However, it can be clearly interpreted on the map that the closest distance is between Iracoubo and Sinnamary.


### Google Map 3. Vacation Itinerary Travel Map Markers 
![WeatherPy_travel_map_markers](https://user-images.githubusercontent.com/26927158/197098399-af36a591-7368-4d1e-8968-686f534042bb.png)

The above map is essentially the same as Google Map 2. However, the difference is that only the information we call markers is included. If we examine the necessary region for travel,
For the city of mana;
- Hotel Name: Le Samana
- Country: GF (French Guiana)
- Current Weather: Broken Clouds and 80.02 F

For the city of Iracoubo;
- Hotel Name: Le Gite d'Iracoubo
- Country: GF (French Guiana)
- Current Weather: Broken Clouds and 79.33 F

For the city of Sinnamary;
- Hotel Name: Aletheia Appartement Sinnamary
- Country: GF (French Guiana)
- Current Weather: Broken Clouds and 79.0 F

For the city of Cayenne;
- Hotel Name: Hotel Le Dromni
- Country: GF (French Guiana)
- Current Weather: Clear Sky and 80.64 F


## Summary

The regions and countries included in this study are randomly selected regions that we obtained with the help of API Key. Only four cities from the randomly selected regions were determined for travel purposes. Each time the codes in the study are run, different data sets will be obtained and the tables and maps will differ. When it is desired to do a different study, it would be correct to create a random data set again.



