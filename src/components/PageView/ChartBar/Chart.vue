<template>
  <div class="chart">
  </div>
</template>

<script>

  export default {
    name: 'Chart'
  }

</script>

<style>

  .chart {
    background-color: rgba(36, 49, 55, 1);
    flex: 1 1 auto;
  }
  .chart + .chart {
    margin-top: 15px;
  }
  
</style>
