<template>
  <div id="app">
    <Sidebar />
    <div class="main-content">
      <AIPredictedScore />
      <SATScoreDistribution />
      <PerformanceTracker />
    </div>
    <ChatBox />
  </div>
</template>

<script setup>
import Sidebar from './components/sidebar.vue';
import AIPredictedScore from './components/predicted-score.vue';
import SATScoreDistribution from './components/score-distribution.vue';
import PerformanceTracker from './components/performance-tracker.vue';
import ChatBox from './components/chatbox.vue';
</script>

<style>
#app {
  display: flex;
  flex-grow: 1;
}

.main-content {
  flex: 1;
  padding: 20px;
}
</style>
