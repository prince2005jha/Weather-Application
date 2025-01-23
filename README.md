# Weather App

## Overview
The **Weather App** is a simple and interactive web-based tool that allows users to check the current temperature and weather conditions of any location worldwide. Using the WeatherAPI service, the app fetches real-time weather data and displays it in an intuitive and user-friendly interface.

---

## Features
- **Location Input**: Users can input the name of any city or location to get the weather details.
- **Real-Time Weather Data**: Displays the current temperature (in Celsius and Fahrenheit), weather conditions, and location information.
- **Responsive Design**: A clean and minimalistic interface for a seamless user experience on any device.

---

## Prerequisites
- A modern web browser (Google Chrome, Firefox, Safari, etc.).
- Internet connection to fetch weather data from the WeatherAPI.

---

## How to Use
1. **Open the App**: Launch the application in your web browser.
2. **Enter Location**: Input the desired location (e.g., "London") in the text field.
3. **Get Weather**: Click the "Get Weather" button to fetch and display the weather information.

---

## Code Walkthrough

### HTML
- **Input Field**: Provides a text input for the user to specify the location.
  ```html
  <input type="text" id="location" placeholder="Enter Location">
  ```
- **Button**: Triggers the weather fetching process.
  ```html
  <button onclick="getWeather()">Get Weather</button>
  ```

### CSS
- **Styling**: Implements a responsive and visually appealing design with a gradient background and centered layout.
  ```css
  body {
      font-family: Arial, sans-serif;
      background: linear-gradient(to right, #6dd5fa, #2980b9);
      color: #fff;
  }
  ```

### JavaScript
- **Fetch Weather Data**: Sends a request to the WeatherAPI and processes the response to display the data.
  ```javascript
  async function getWeather() {
      const apiKey = 'your_api_key_here';
      const location = document.getElementById('location').value;
      const apiUrl = `http://api.weatherapi.com/v1/current.json?key=${apiKey}&q=${location}&aqi=yes`;
      const response = await fetch(apiUrl);
      const data = await response.json();
      document.getElementById('result').innerHTML = `Temperature: ${data.current.temp_c}°C`;
  }
  ```

---

## Future Enhancements
- Add support for weather icons to visually represent conditions.
- Include additional data like wind speed, humidity, and air quality.
- Implement autocomplete suggestions for location input.
- Optimize for offline use by caching recent weather data.

---

## License
This project is open-source and available under the MIT License. Feel free to modify and distribute it as needed.

