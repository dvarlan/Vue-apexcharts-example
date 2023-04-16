<script setup lang="ts">
import Chart from './components/Chart.vue';
</script>

<template>
  <div class="wrapper">
    <h1>A simple Vue Apexchart example</h1>
    <hr>
    <Chart></Chart>
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
  }
}
</style>
