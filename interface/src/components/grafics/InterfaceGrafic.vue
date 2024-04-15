<template>
    <div class="chart-interface">
      <div class="chart-options">
        <slot name="options"></slot>
      </div>
      <canvas ref="chartCanvas" :width="chartWidth" :height="chartHeight"></canvas>
    </div>
  </template>
  
  <script>
  import { ref, watch } from 'vue';
  import { Chart } from 'chart.js';
  
  export default {
    props: {
      chartData: {
        type: Object,
        required: true
      },
      chartWidth: {
        type: Number,
        default: 400
      },
      chartHeight: {
        type: Number,
        default: 300
      }
    },
    setup() {
      const chartCanvas = ref(null);
  
      watch(chartCanvas, (canvas) => {
        if (canvas) {
          const ctx = canvas.getContext('2d');
          new Chart(ctx, chartData);
        }
      }, { immediate: true });
  
      return {
        chartCanvas
      };
    }
  };
  </script>
  
  <style scoped>
  .chart-interface {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
  
  .chart-options {
    margin-bottom: 15px;
  }
  </style>
  