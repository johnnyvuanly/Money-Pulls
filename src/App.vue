<template>
  <h1>Money Pulls</h1>
  <yugioh-table />
</template>

<script>
import YugiohTable from './components/YugiohTable.vue'

export default {
  name: 'App',
  components: {
    YugiohTable
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
