<template>
  <div class="logview">
    <LogConsole :types="types" :startdate="startdate" :enddate="enddate" :lognum="lognum"/>
  </div>
</template>

<script>

  import LogConsole from './LogView/LogConsole.vue'

  export default {
    name: 'LogView',
    components: {
      LogConsole
    },
    props: ['types', 'startdate', 'enddate', 'lognum']
  }
  
</script>

<style>

  .logview {
    flex: 0 1 40%;
    overflow: hidden;
  }

</style>
