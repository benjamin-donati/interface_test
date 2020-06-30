<template>
  <div class="typesgroup">
    <CheckBox v-for="type in types" :type="type"/>
  </div>
</template>

<script>

  import CheckBox from './TypesGroup/CheckBox.vue'

  export default {
    name: 'TypesGroup',
    components: {
      CheckBox
    },
    props: {
      types: {
        type: Array,
        required: true
      }
    }
  }

</script>

<style>

  .typesgroup {
    display: flex;
    flex-flow: row;
    flex: 0 1 350px;
    height: 100%;
  }
  
</style>
