<template>
  <input type="date" class="date">
</template>

<script>

  export default {
    name: 'SingleDate',
    props: ['singledate']
  }

</script>

<style>

  .dates .timestamp.date input[type='date'].date {
    background-color: rgba(48, 75, 86);
    border: none;
    color: #ccc;
    height: 24px;
    margin-bottom: 0;
    outline: 2px solid #ccc;
    position: relative;
    transition: all 200ms cubic-bezier(.4,.0,.23,1);
  }

  .dates .timestamp.date:hover input[type='date'] {
    background: rgba(255,255,255,.1);
    outline: 2px solid #fff;
  }

  .dates .timestamp.date input[type='date'].date {
    width: 130px;
  }

  .dates .timestamp.date input[type='date'].date:focus {
    border: none;
  }

</style>
