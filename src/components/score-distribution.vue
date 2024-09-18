<template>
  <div class="card shadow-sm p-3">
    <div class="card-body">
      <h5 class="card-title">SAT Score Distribution</h5>
      <canvas ref="satScoreChart"></canvas>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { Chart, registerables } from 'chart.js';
Chart.register(...registerables);

const satScoreChart = ref(null);

const renderChart = () => {
  const ctx = satScoreChart.value.getContext('2d');
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: [400, 600, 800, 1000, 1200, 1350, 1400, 1600],
      datasets: [{
        label: 'Test Takers',
        data: [2000, 4000, 8000, 12000, 16000, 14000, 8000, 4000],
        borderColor: 'rgba(75, 192, 192, 1)',
        backgroundColor: 'rgba(75, 192, 192, 0.2)',
        borderWidth: 2,
        fill: true,
        tension: 0.4
      }]
    },
    options: {
      responsive: true,
      scales: {
        x: {
          beginAtZero: true,
          title: {
            display: true,
            text: 'SAT Score'
          }
        },
        y: {
          beginAtZero: true,
          title: {
            display: true,
            text: 'Test Takers'
          }
        }
      },
      plugins: {
        legend: {
          display: false
        },
        tooltip: {
          callbacks: {
            label: function(context) {
              return `${context.dataset.label}: ${context.raw}`;
            }
          }
        }
      }
    }
  });
};

onMounted(() => {
  renderChart();
});
</script>

<style scoped>
canvas {
  width: 100%;
  height: 400px;
}
</style>
