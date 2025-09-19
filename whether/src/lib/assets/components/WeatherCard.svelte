<script>
    import { onMount } from 'svelte';
    import plot from 'simple-ascii-chart';
    let weatherData = null;
  
    onMount(async () => {
      const response = await fetch(
        'https://api.open-meteo.com/v1/forecast?latitude=52.52&longitude=13.41&daily=temperature_2m_max,temperature_2m_min&hourly=temperature_2m&forecast_days=3'
      );
      const data = await response.json();
      weatherData = data;
    });
  </script>
  
  {#if weatherData}
    <div id="container">
      {#each weatherData.daily.temperature_2m_max as maxTemp, i}
        <div class="weather-card">
          <h3>Day {i + 1}</h3>
          <p>Latitude: {weatherData.latitude}</p>
          <p>Longitude: {weatherData.longitude}</p>
          <p>Max Temp: {maxTemp}°C</p>
          <p>Min Temp: {weatherData.daily.temperature_2m_min[i]}°C</p>
        </div>
      {/each}
    </div>
  {:else}
    <p>Loading weather data...</p>
  {/if}
  