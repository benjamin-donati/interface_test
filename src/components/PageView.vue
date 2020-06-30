<template>
  <div class="pageview">
    <LogView :types="types" :startdate="startdate" :enddate="enddate" :lognum="lognum"/>
    <ChartBar/>
  </div>
</template>

<script>
  import LogView from './PageView/LogView.vue'
  import ChartBar from './PageView/ChartBar.vue'

  export default {
    name: 'PageView',
    components: {
      LogView,
      ChartBar
    },
    props: ['types', 'startdate', 'enddate', 'lognum']
  }
</script>

<style>

  .pageview {
    display: flex;
    flex: 1 1 auto;
    flex-flow: row;
    overflow: auto;
  }

</style>
