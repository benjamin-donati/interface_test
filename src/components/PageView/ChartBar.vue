<template>
  <div class="chartbar">
    <Chart/>
    <Chart/>
    <Chart/>
  </div>
</template>

<script>

  import Chart from './ChartBar/Chart.vue'

  export default {
    name: 'ChartBar',
    components: {
      Chart
    }
  }
  
</script>

<style>

  .chartbar {
    background-color: rgba(20, 37, 45);
    display: flex;
    flex: 0 1 60%;
    flex-flow: column;
    padding: 15px;
  }

</style>
