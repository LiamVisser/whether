<script>
    import { onMount } from 'svelte';
    let weatherData = $state("");
    let currentTime = new Date().toLocaleTimeString();

  
    onMount(async () => {
      const response = await fetch(
        'https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.41&hourly=temperature_2m,precipitation,precipitation_probability&current=temperature_2m,is_day,apparent_temperature&forecast_days=1'
      );
      const data = await response.json();
      weatherData = data;
    });
  </script>
  
  {#if weatherData != ""}
    <div class="weather-card">
      <h2>Current Weather</h2>
      <p><strong>Time:</strong> {currentTime}</p>
      <p><strong>Temperature:</strong> {weatherData.current.temperature_2m}°C</p>
      <p><strong>Feels Like:</strong> {weatherData.current.apparent_temperature}°C</p>
      <p><strong>Chance of Precipitation:</strong> {weatherData.hourly.precipitation_probability[0]}%</p>
    </div>
  {:else}
    <p>Loading weather data...</p>
  {/if}
  
  