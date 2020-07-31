<template>
  <div id="app">
    <!-- <formSample></formSample> -->
    <tree></tree>
  </div>
</template>

<script>
    import formSample from './components/form/index.vue';
    import tree from './components/tree/index.vue';
    export default {
      components:{
        formSample,
        tree
      },
      name: 'App'
    }
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
