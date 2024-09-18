<template>
    <div class="card shadow-sm">
      <div class="card-body">
        <h5 class="card-title">Performance Tracker</h5>
        <div class="mb-3">
          <label>Math</label>
          <div class="progress">
            <div class="progress-bar bg-primary" role="progressbar" :style="{width: mathScore + '%'}">{{ mathScore }}</div>
          </div>
        </div>
        <div class="mb-3">
          <label>Reading</label>
          <div class="progress">
            <div class="progress-bar bg-secondary" role="progressbar" :style="{width: readingScore + '%'}">{{ readingScore }}</div>
          </div>
        </div>
        <div>
          <label>Writing</label>
          <div class="progress">
            <div class="progress-bar bg-info" role="progressbar" :style="{width: writingScore + '%'}">{{ writingScore }}</div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'PerformanceTracker',
    data() {
      return {
        mathScore: 85,
        readingScore: 60,
        writingScore: 70,
      };
    }
  }
  </script>
  
  <style scoped>
  </style>
  