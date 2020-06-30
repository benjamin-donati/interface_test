<template>
  <input type="time" class="time">
</template>

<script>

  export default {
    name: 'SingleTime',
    props: ['singledate']
  }

</script>

<style>

  .dates .timestamp.time input[type='time'].time {
    background-color: rgba(48, 75, 86);
    border: none;
    color: #ccc;
    height: 24px;
    margin-bottom: 0;
    outline: 2px solid #ccc;
    position: relative;
    transition: all 200ms cubic-bezier(.4,.0,.23,1);
  }

  .dates .timestamp.time:hover input[type='time'] {
    background: rgba(255,255,255,.1);
    outline: 2px solid #fff;
  }

  .dates .timestamp.time input[type='time'].time {
    width: 80px;
  }

  .dates .timestamp.time input[type='time'].time:focus {
    border: none;
  }

</style>
