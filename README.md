# MDS-proiect
## Weather forecasting

This program is a weather forecasting web application written in Java.

### Team members:
- [Soydan Alperen](https://github.com/soydan7419/Weather.git)
- [Shahsavari Mohammad](https://github.com/MohammadShahsavarii/MDS-proiect.git)

### Description of application:
This program is a weather forecasting web application written in Java.
Usually, people plan their trip so that they can make the best use of their time. Also, in terms of agriculture, weather forecasting is a very important issue for planting, spraying and harvesting. In other matters, even such as airline companies, tourism tours, maritime and military affairs, weather forecasting is one of the principles of planning the above matters.
In this program, we can see the weather forecast. For example, if you plan to travel to another country, you can use this app to see the weather there. The program analyzes itself every time. In other words, it recalculates the weather forecast.

### UML diagram
UML diagram of the model
![overall-architecture](https://github.com/MohammadShahsavarii/MDS-proiect/assets/127997195/3770ce14-8572-4751-9879-d75079f1239e)

### How does the application works?
Application receives the requested via /v1/api/open-weather/{city} url with {city} path variables
There is a validation for city parameter. City value can not be decimal or a blank value.
If the city value is not valid, api returns 400 - Http Bad Request response
Current weather report can be fetch either from database or WeatherStackAPI with the API_KEY
If the latest data is not older than 30 minutes for that city value, data is fetching from db.
Either city does not exist or older than 30 minutes in DB, a request sends to WeatherStackAPI and the result puts to Cache
If there is a value with city filter as key in cache, the response is returns from cache directly
On the swagger page you can find the relevant api endpoint. You can reach the openapi page by http://localhost:8080/swagger-ui/index.html url.

You can define WEATHER_STACK_API_KEY in the .env file


