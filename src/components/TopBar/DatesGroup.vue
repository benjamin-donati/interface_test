<template>
  <div class="dates">
    <div class="timestamp date">
      <label class="date">
        Depuis le
      </label>
      <SingleDate/>
    </div>
    <div class="timestamp time">
      <label class="time">
        à
      </label>
      <SingleTime/>
    </div>
    <div class="timestamp date">
      <label class="date">
        jusqu'au
      </label>
      <SingleDate/>
    </div>
    <div class="timestamp time">
      <label class="time">
        à
      </label>
      <SingleTime/>
    </div>
  </div>
</template>

<script>

  import SingleDate from './DatesGroup/SingleDate.vue'
  import SingleTime from './DatesGroup/SingleTime.vue'

  export default {
    name: 'DatesGroup',
    components: {
      SingleDate,
      SingleTime
    },
    props: ['startdate', 'enddate', 'lognum']
  }
  
</script>

<style>

  .dates {
    align-items: center;
    display: flex;
    flex-flow: row;
    flex: 1 1 auto;
    margin-left: 40px;
  }

  .dates .timestamp {
    align-items: center;
    display: flex;
    flex-flow: row;
    line-height: 26px;
  }

  .dates .timestamp.date label.date,
  .dates .timestamp.time label.time {
    color: #ccc;
    margin-bottom: 0;
    padding-left: 10px;
    padding-right: 10px;
    position: relative;
    transition: color 200ms cubic-bezier(.4,.0,.23,1);
  }

  .dates .timestamp.date label.date {
    width: auto;
  }
  .dates .timestamp.time label.time {
    width: auto;
  }

  .dates .timestamp.date:hover label,
  .dates .timestamp.time:hover label {
    color: #fff;
  }

</style>
