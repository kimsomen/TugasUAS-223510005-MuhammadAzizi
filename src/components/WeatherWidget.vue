<template>
    <div class="weather-widget">
      <h2 class="widget-title">Weather Widget</h2>
      <div class="location-input">
        <label for="location">Enter Location :</label>
        <input type="text" id="location" v-model="location" />
        <button @click="fetchWeatherData">Enter</button>
      </div>
      <div v-if="weatherData" class="weather-data">
        <p class="location">Location : {{ weatherData.name }}</p>
        <p v-if="weatherData.main" class="temperature">
          Temperatur: {{ weatherData.main.temp }}°C
        </p>
        <p v-if="weatherData.weather" class="description">
          Description: {{ weatherData.weather[0].description }}
        </p>
      </div>
      <p v-else>Loading weather data...</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        location: '',
        weatherData: null
      };
    },
    methods: {
      async fetchWeatherData() {
        try {
          const apiKey = '99635c9c17e2858357c1ce6b4eee22fb';
          const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=${this.location}&appid=${apiKey}`;
  
          const response = await fetch(apiUrl);
          const data = await response.json();
  
          this.weatherData = data;
        } catch (error) {
          console.error('Error fetching weather data:', error);
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .weather-widget {
    border: 5px solid #ccc;
    padding: 100px;
    margin-bottom: 20px;
    text-align: center;
    background-color: #ffffff;
    border-radius: 15px;
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
    margin-top: 50px;
    transition: transform 0.3s, box-shadow 0.3s;
    position: relative;
  }
  
  .weather-widget:hover {
    transform: translateY(-10px);
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.2);
  }
  
  .weather-widget:before,
  .weather-widget:after {
    content: "";
    position: absolute;
    top: -5px;
    left: -5px;
    right: -5px;
    bottom: -5px;
    background: linear-gradient(135deg, #ff9a9e, #fad0c4, #fad0c4, #ff9a9e);
    z-index: -1;
    border-radius: 20px;
  }
  
  .weather-widget:after {
    filter: blur(15px);
  }
  
  .widget-title {
    margin-top: 0;
    color: #333;
    font-size: 24px;
    margin-bottom: 20px;
  }
  
  .location-input {
    margin-bottom: 20px;
  }
  
  .location-input label {
    margin-right: 10px;
    font-weight: bold;
  }
  
  .location-input input {
    padding: 8px;
    border-radius: 4px;
    border: 1px solid #ccc;
    margin-right: 10px;
  }
  
  .location-input button {
    padding: 8px 12px;
    border: none;
    background-color: #00796b;
    color: white;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }
  
  .location-input button:hover {
    background-color: #004d40;
  }
  
  .weather-data {
    margin-top: 20px;
    background-color: #fafafa;
    padding: 15px;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  }
  
  .location {
    font-size: 18px;
    font-weight: bold;
  }
  
  .temperature {
    font-size: 24px;
    color: #ff5722;
    margin: 10px 0;
  }
  
  .description {
    font-size: 16px;
    color: #757575;
  }
  </style>
  