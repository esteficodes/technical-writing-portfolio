# 🌤️ OpenWeather API Integration Guide

**Audience**: Beginner developers who want to fetch weather data into a website or app using JavaScript.  
**API Used**: [OpenWeather Current Weather Data API](https://openweathermap.org/current)

---

## 🔐 Step 1: Get Your API Key

1. Go to [https://openweathermap.org/api](https://openweathermap.org/api)
2. Create a free account and log in
3. Generate an API key in your dashboard
4. Your key will look like:
   
9a1b2c3d4e5f6g7h8i9j0k...

---

## 📤 Step 2: Make a Request (JavaScript)

Use `fetch()` to get the current weather for a city:

```js
const apiKey = 'YOUR_API_KEY';
const city = 'Copenhagen';

fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric`)
.then(response => response.json())
.then(data => {
 console.log('Weather in', city);
 console.log('Temperature:', data.main.temp, '°C');
 console.log('Condition:', data.weather[0].description);
})
.catch(error => console.error('Error fetching weather data:', error));

## 📦 Response Format (JSON)
Example response:
{
  "weather": [
    { "description": "clear sky", "icon": "01d" }
  ],
  "main": {
    "temp": 24.7,
    "humidity": 53
  },
  "name": "Copenhagen"
}
## Optional enhancements

1.Show weather icons using data.weather[0].icon

2.Add error handling for unknown cities

3.Use navigator.geolocation to fetch local weather

## Test it
Try it in the browser console or embed it into a small weather widget.

✅ This guide was created for portfolio demonstration purposes.
