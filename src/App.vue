<template>
  <div id="app">
    <AddEmployee :list="list"/>
  </div>
</template>

<script>
import AddEmployee from './components/AddEmployee.vue'

export default {
  name: 'app',
  components: { AddEmployee },
  data(){
    return {
      list: [
        { name: 'Richard Henricks', email: 'richard@piedpiper.com' },
        { name: 'Bertram Gilfoyle', email: 'gilfoyle@piedpiper.com' },
        { name: 'Dinesh Chugtai', email: 'dinesh@piedpiper.com' }
      ]
    }
  }
}
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
  }
</style>
