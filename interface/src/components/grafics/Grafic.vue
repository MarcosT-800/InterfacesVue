<template>
    <div id="app">
      <chart-interface :chart-data="chartData1" :chart-width="450" :chart-height="300">
        <template #options>
          <div>
            <label for="chartType">Tipo de Gráfico:</label>
            <select id="chartType" v-model="chartType">
              <option value="line">Linha</option>
              <option value="bar">Barra</option>
              <option value="pie">Torta</option>
            </select>
          </div>
          <div>
            <label for="chartColor">Cor do Gráfico:</label>
            <input type="color" id="chartColor" v-model="chartColor">
          </div>
        </template>
      </chart-interface>
      <chart-interface :chart-data="chartData2" :chart-width="300" :chart-height="250">
        <template #options>
          </template>
      </chart-interface>
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
  data() {
    return {
      // Adicione propriedades para armazenar as opções selecionadas
      chartType: 'line', // Tipo de gráfico padrão
      chartColor: '#f44336' // Cor de gráfico padrão
    };
  },
  setup() {
    const chartCanvas = ref(null);

    watch(chartCanvas, (canvas) => {
      if (canvas) {
        const ctx = canvas.getContext('2d');
        new Chart(ctx, updateChartData()); // Use updateChartData()
      }
    }, { immediate: true });

    const updateChartData = () => {
      // Função para atualizar dados do gráfico com base nas opções
      const updatedData = JSON.parse(JSON.stringify(this.chartData)); // Cópia do chartData
      updatedData.type = this.chartType;
      updatedData.data.datasets[0].backgroundColor = this.chartColor;
      return updatedData;
    };

    return {
      chartCanvas
    };
  }
};
</script>
  