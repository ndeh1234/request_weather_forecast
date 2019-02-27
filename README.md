# request_weather_forecast

import requests

from datetime import datetime


# Taking input from users
city = input('Enter name of city: ')
url = 'http://api.openweathermap.org/data/2.5/weather?q={}&units=imperial&'\
'APPID=17959c71c1522324a3b9e201a9ce81a6'.format(city)


res = requests.get(url)
data = res.json()
temp= data['main']['temp']
wind_speed = data['wind']['speed']

description = data['weather'][0]['description']

#print('Temperature: ', temp)
#print('wind speed: {}'.format(wind_speed))

#print('Description: {}'.format(description))

print(f'The weather is {description},the wind speed is {wind_speed}, and the temperature is {temp:.2f}F.')


