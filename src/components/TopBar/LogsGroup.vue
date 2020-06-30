<template>
  <div class="logsgroup">
    <label class="rangelabel">Logs à afficher</label>
    <RangeSlider :lognumber="lognum" @update-range-slider="get_update_range_slider" @change="set_update_logs_group"/>
  </div>
</template>

<script>

  import RangeSlider from './LogsGroup/RangeSlider.vue'

  export default {
    name: 'LogsGroup',
    components: {
      RangeSlider,
    },
    props: ['lognum'],
    methods: {
      get_update_range_slider (lognumber) {
        this.lognum = lognumber;
      },
      set_update_logs_group(lognum) {
        this.$emit('update-logs-group', lognum.target.valueAsNumber)
      }
    }
  }
  
</script>

<style>

  .logsgroup {
    align-items: center;
    display: flex;
    flex-flow: row;
    flex: 0 1 350px;
  }

  .logsgroup:hover {
    color: #fff;
  }

  .rangelabel {
    border: none;
    color: #ccc;
    /* flex: 0 1 130px; */
    flex: 0 1 auto;
    margin-bottom: 0;
    margin-right: 15px;
    position: relative;
    transition: color 200ms cubic-bezier(.4,.0,.23,1);
  }

  .rangelabel:hover  {
    color: #fff;
  }

</style>
