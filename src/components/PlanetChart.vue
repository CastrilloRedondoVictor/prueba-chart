<template>
  <div style="width: 1000px;">
    <canvas id="planet-chart"></canvas>
  </div>
</template>

<script>
import { Chart, registerables } from 'chart.js'; // Import Chart and registerables
import planetChartData from '../planet-data.js'; // Ensure this imports correctly

Chart.register(...registerables); // Register all necessary components

export default {
  name: 'PlanetChart',
  data() {
    return {
      planetChartData: planetChartData // Use the chart data defined above
    };
  },
  mounted() {
    const ctx = document.getElementById('planet-chart').getContext('2d'); // Get the 2D context of the canvas
    new Chart(ctx, this.planetChartData); // Create a new Chart instance with the data
  }
};
</script>

<style scoped>
/* Add any styles you want for the chart container */
</style>
