<script setup lang="ts">
import { defineComponent } from "vue";
import ButtonComponent from './components/buttons/buttonLittle.vue';
import LittleTable from './components/tables/LittleTable.vue';
import Navbar from "./components/header/Navbar.vue";
import InformationCard from "./components/cards/InformationCard.vue";
import Grafic from "./components/grafics/Grafic.vue";

const chartData1 = {
  type: 'line', // Chart type (e.g., 'line', 'bar', 'pie', etc.)
  data: {
    labels: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun'], // Labels for the X-axis
    datasets: [{
      label: 'My Data', // Label for the dataset
      data: [10, 20, 30, 50, 40, 60], // Data points for the dataset
      borderColor: 'red', // Color of the line
      fill: false // Whether to fill the area under the line (optional)
    }]
  },
  options: {
    title: { // Chart title (optional)
      display: true,
      text: 'Line Chart Example'
    }
  }
};

const chartData2 = {
  type: 'pie', // Chart type
  data: {
    labels: ['A', 'B', 'C'], // Labels for pie slices
    datasets: [{
      data: [30, 50, 20], // Data points for each slice
      backgroundColor: ['#f44336', '#e91e63', '#9c27b0'] // Colors for slices
    }]
  },
  options: {
    title: {
      display: true,
      text: 'Pie Chart Example'
    }
  }
};


</script>

<template>
  <Navbar />
  <div class="button">
      <h1>Hello world</h1>
      <button-component type="primary" label="Clique em Mim!"> </button-component>
  </div>

  <div>
     <InformationCard/>
     <LittleTable />    
  </div>

  <div>
    <Grafic :chart-data="chartData1" :chart-width="450" :chart-height="300" />
    <Grafic :chart-data="chartData2" :chart-width="300" :chart-height="250" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

.button {
  margin-bottom: 12px;
}
</style>
