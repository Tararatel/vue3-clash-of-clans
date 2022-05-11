<template v-slot:footer>
  <div class="card-stats">
    <div v-for="(stat, index) in item.info" :key="index" class="one-third">
      <div class="stat-value">{{ stat.value }}</div>
      <div class="stat">{{ stat.title }}</div>
    </div>
  </div>
</template>
