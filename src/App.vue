<script setup>
import PushUpCounter from './components/PushUpCounter.vue';
import BarChart from './components/BarCharts.vue';

</script>

<script>
export default {
  name: 'App',
  components: { BarChart }
}
</script>

<template>
  <main>
    <PushUpCounter />
    <div class="chart-container">
      <BarChart />
    </div>
  </main>
</template>

<style scoped>
.chart-container {
   width: 1000px;
   height:600px
}
</style>
