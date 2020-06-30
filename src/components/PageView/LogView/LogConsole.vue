<template>
  <div class="logconsole">
    <Log v-for="(n,index) in lognum" :types="types" :lognum="lognum" :logdate="random_timestamp()" :logtype="random_type(types)" :logtypenum="random_type_num()" :logstate="random_type_state()"/>
  </div>
</template>

<script>

  import Log from './LogConsole/Log.vue'

  export default {
    name: 'LogConsole',
    components: {
      Log
    },
    props: ['types', 'startdate', 'endenddateDate', 'lognum'],
    methods: {
      random_timestamp() {
        const options = {year: 'numeric', month: 'numeric', day: 'numeric', hour: 'numeric', minute: 'numeric' };
        var myDate = new Date(new Date(2012, 0, 1).getTime() + Math.random() * (new Date().getTime() - new Date(2012, 0, 1).getTime())).toLocaleDateString('fr-FR', options);
        return myDate;
      },
      random_type(types) {
        return types[Math.floor(Math.random() * types.length)].name;
      },
      random_type_num() {
        return Math.floor(Math.random() * Math.floor(10));
      },
      random_type_state() {
        const states = ['activé(e)', 'désactivé(e)'];
        return states[Math.floor(Math.random() * states.length)];
      },
    }
  }
  
</script>

<style>

  .logconsole {
    background: #243137;
    color: #ccc;
    display: flex;
    flex-flow: column;
    height: 100%;
    margin: 0;
    overflow: auto;
    padding: 20px;
    transition: all 200ms cubic-bezier(.4,.0,.23,1);
  }

  .logconsole::-webkit-scrollbar {
    transition: all 200ms cubic-bezier(.4,.0,.23,1);
    width: 2px;
  }

  .logconsole:hover::-webkit-scrollbar-thumb {
    background: #555;
  }

  .logconsole::-webkit-scrollbar-track {
    background: #243137;
  }

  .logconsole::-webkit-scrollbar-thumb {
    background: #243137;
    border-radius: 4px;
  }

  .logconsole p {
    font-family: "Courier New";
    margin: 0;
  }

  .logconsole p:before {
    content: "> ";
    font-family: "Courier New";
  }

</style>
