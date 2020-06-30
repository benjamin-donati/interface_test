<template>
  <div class="topbar">
    <TypesGroup :types="types"/>
    <div class="spacer"></div>
    <DatesGroup :startdate="startdate" :enddate="enddate" />
    <div class="spacer"></div>
    <LogsGroup :lognum="lognum" @update-logs-group="get_update_logs_group" @change="set_update_top_bar"/>
  </div>
</template>

<script>

  import TypesGroup from './TopBar/TypesGroup.vue'
  import DatesGroup from './TopBar/DatesGroup.vue'
  import LogsGroup from './TopBar/LogsGroup.vue'

  export default {
    name: 'TopBar',
    components: {
      TypesGroup,
      DatesGroup,
      LogsGroup
    },
    props: ['types', 'startdate', 'enddate', 'lognum'],
    methods: {
      get_update_logs_group (lognum) {
        this.lognum = lognum;
      },
      set_update_top_bar(lognum) {
        this.$emit('update-top-bar', lognum.target.valueAsNumber)
      }
    }
  }

</script>

<style>

  .topbar {
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    -o-user-select: none;
    user-select: none;

    background-color: rgba(48, 75, 86);
    box-sizing: border-box;
    display: flex;
    flex: 0 1 100px;
    padding: 37px;
  }
  .spacer {
    flex: 0 1 30px;
    height: 100%;
  }
  
</style>
