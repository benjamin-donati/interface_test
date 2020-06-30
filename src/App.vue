<template>
  <div id="app">
    <TopBar :types="types" :startdate="startdate" :enddate="enddate" :lognum="lognum" @update-top-bar="get_update_top_bar"/>
    <PageView :types="types" :startdate="startdate" :enddate="enddate" :lognum="lognum"/>
  </div>
</template>

<script>
  import TopBar from './components/TopBar.vue'
  import PageView from './components/PageView.vue'

  var typeId = 0;

  export default {
    name: 'App',
    components: {
      TopBar,
      PageView
    },
    data() {
      return {
        types: [
          {id: typeId++, name:"Caméra", state: 1},
          {name:"Serveur", state: 1},
          {name:"Utilisateur", state: 1}
        ],
        startdate: ['2015-00-01'],
        enddate: [],
        lognum: 500
      };
    },
    methods: {
      get_update_top_bar(lognum) {
        this.lognum = lognum;
      }
    }
  }
</script>

<style>

  body {
    background-color: #243137;
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    text-align: left;
  }

  html, body, #app {
    height: 100%;
    margin: 0;
    padding: 0;
    width: 100%;
  }

  #app {
    display: flex;
    flex-flow: column;
  }
  
</style>
