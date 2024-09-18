<template>
  <div class="sidebar">
    <ul>
      <li v-for="item in menuItems" :key="item.name">
        <a :href="item.link">{{ item.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script setup>
const menuItems = [
  { name: 'Home', link: '#' },
  { name: 'Math', link: '#' },
  { name: 'Reading', link: '#' },
  { name: 'Writing', link: '#' },
  { name: 'Test', link: '#' },
  { name: 'Report', link: '#' }
];
</script>

<style scoped>
.sidebar {
  width: 200px;
  background-color: #f8f9fa;
  padding: 20px;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  margin-bottom: 10px;
}

a {
  text-decoration: none;
  color: #333;
}
</style>
