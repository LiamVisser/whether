<script>
	import DarkMode from "../lib/Components/Dark_mode.svelte";
  import WeatherCard from '$lib/assets/components/WeatherCard.svelte';
</script>
<DarkMode/>
<main>
  <h1>Weather Forecast</h1>
<a href="/">Daily temp</a>
<a href="/week">Week temp</a>
</main>

<style>
  main {
    font-family: sans-serif;
  }
</style>
<WeatherCard />



