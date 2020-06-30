<template>
  <div class="checktype">
    <input type="checkbox" v-bind:id="type.name" :checked="type.state == 1">
    <label v-bind:for="type.name" class="checklabel">{{type.name}}</label>
  </div>
</template>

<script>

  export default {
    name: 'CheckBox',
    props: {
      type: {
        type: Object,
        required: true
      }
    }
  }

</script>

<style>

  .checktype {
    align-items: center;
    display: flex;
    flex-flow: row;
    flex: 0 1 calc(100% / 3);
    line-height: 100%;
  }

  .checktype input[type=checkbox] {
    -webkit-appearance: none;
    -moz-appearance: none;
    -ms-appearance: none;
    outline: 2px solid #ccc;
    height: 16px;
    margin:0px;
    transition: all 200ms cubic-bezier(.4,.0,.23,1);
    width: 26px;
  }

  .checktype input[type="checkbox"]:checked {
    background: white;
    color: black;
    content: '\f00d';
    font-family: FontAwesome;
    font-size: 13px;
    margin:0px;
    outline: 2px solid #fff;
    position: relative;
  }

  .checktype label {
    color: #ccc;
    flex: 1 1 auto;
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    margin-bottom: 0;
    padding-left: 10px;
    position: relative;
    text-align: left;
    transition: color 200ms cubic-bezier(.4,.0,.23,1);
  }

  .checktype:hover input[type='checkbox']:not(:checked) {
    outline: 2px solid #fff;
  }

  .checktype:hover label {
    color: #fff;
  }

  .checktype input[type='checkbox']:checked + label{
    color: #fff;
  }
  
</style>
