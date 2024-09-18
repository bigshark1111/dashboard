<template>
  <div class="ai-score-container">
    <h2>AI Predicted Score</h2>
    <div class="score">{{ predictedScore }}</div>
    <div class="sat-act">SAT → ACT: {{ satToAct }}</div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const predictedScore = ref(1520);
const satToAct = ref(26);

onMounted(() => {
  // fetchPredictedScore();
});
</script>

<style scoped>
.ai-score-container {
  text-align: center;
  padding: 20px;
}

.score {
  font-size: 64px;
  font-weight: bold;
  color: #333;
}

.sat-act {
  font-size: 18px;
  color: #666;
}
</style>
