salesforce-weather
==================

Gets 10 days of weather from WeatherUnderground (Wunderground) and displays it in a VF page on your Case object. Logic in place to grab historical data if its in the past, current conditions if today, and forecast data up to 10 days in the future. Uses a data picker to set the approx date you want to see.

Requirements:
-------------

* Access to Cases object
* jQuery as a Static Resource
* YOUR_API_KEY get it FREE from their devloper site: http://www.wunderground.com/weather/api/

Note: Since every single request for a day of weather data counts, I end up hitting their API 10 times all at once, with the limit being something like 15/minute. I found that using multiple keys helpful for past, present and future data as well as a different key for testing on Sandboxes. There is also some code that will disable the button for 1 minute so it won't hit the API limits if they click twice and use a "raindrop" (WUnderground's occasional exceptions to their API limits). Run out of raindrops and your key is pretty much toast though (banned for the rest of the month I believe). I have not used any raindrops since I put these limits in place. I seriously have about 30 raindrops per key at the moment.

In the future, I intend to move things over from Wunderground to Forecast.io since they have a lot saner API limits: 1000 requests/day free, and a $1 for every 10,000 requests after that. 1000 requests/days is equal to hitting the button 100 times a day, something were are nowhere near btw. 100 clicks *per month* would cover my needs...
