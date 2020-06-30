<template>
  <div class="log">
    Le {{logdate}} - {{logtype}} {{logtypenum}} {{logstate}}
  </div>
</template>

<script>

  export default {
    name: 'Log',
    props: ['types', 'lognum', 'logdate', 'logtype', 'logtypenum', 'logstate']
  }

</script>

<style>

  .log {
    font-family: "Courier New";
    margin: 0;
  }

  .log:before {
    content: "> ";
    font-family: "Courier New";
  }
  
</style>
