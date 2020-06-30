<template>
  <div class="rangegroup">
    <input type="range" id="log-range" :value="lognumber" @input="set_update_range_slider" class="rangeslider" min="1" max="500">
    <input type="number" id="num" :value="lognumber" @input="set_update_range_slider" class="rangevalue" min="1" max="500">
  </div>
</template>

<script>

  export default {
    name: 'RangeSlider',
    props: ['lognumber'],
    methods: {
      set_update_range_slider(lognum) {
        this.$emit('update-range-slider', lognum.target.valueAsNumber)
      }
    }
  }

</script>

<style>

  .rangegroup {
    align-items: center;
    display: flex;
    flex-flow: row;
  }

  .rangeslider {
    appearance: none;
    background: #ccc;
    border-radius: 6px;
    flex: 1 1 auto;
    height: 4px;
    outline: none;
    margin-top: 4px;
    transition: all 200ms cubic-bezier(.4,.0,.23,1);
    -webkit-appearance: none;
  }

  .rangeslider::-moz-range-thumb {
    background: rgba(20, 37, 45);
    border-radius: 100%;
    border: 2px solid #ccc;
    height: 15px;
    moz-transition: all 200ms cubic-bezier(.4,.0,.23,1);
    width: 15px;
  }

  .rangeslider::-webkit-slider-thumb {
    -webkit-appearance: none;
    -webkit-transition: all 200ms cubic-bezier(.4,.0,.23,1);
    appearance: none;
    background: rgba(20, 37, 45);
    border-radius: 100%;
    border: 2px solid #ccc;
    height: 15px;
    width: 15px;
  }

  .logsgroup:hover .rangeslider {
    background: #fff;
  }

  .logsgroup:hover .rangeslider::-moz-range-thumb {
    border: 2px solid #fff;
    height: 20px;
    width: 20px;
  }

  .logsgroup:hover .rangeslider::-webkit-slider-thumb {
    border: 2px solid #fff;
    height: 20px;
    width: 20px;
  }

  .rangevalue {
    -moz-appearance: textfield;
    -webkit-appearance: textfield;
    appearance: textfield;
    background-color: rgba(48, 75, 86);
    border: none;
    border: none;
    color: #ccc;
    font-family: -apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,"Noto Sans",sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
    font-size: 1rem;
    font-weight: 400;
    line-height: 1.5;
    margin-bottom: 0;
    margin-left: 5px;
    outline: none;
    padding-left: 10px;
    padding-right: 10px;
    position: relative;
    text-align: left;
    transition: color 200ms cubic-bezier(.4,.0,.23,1);
    width: 50px;
  }

  .rangevalue:focus {
    border: none;
    color: #fff;
    outline: none;
  }

  .rangevalue:focus:hover {
    border: none;
    color: #fff;
    outline: none;
  }
  
  .rangevalue::-webkit-inner-spin-button,
  .rangevalue::-webkit-outer-spin-button {
    -webkit-appearance: none;
  }

</style>
