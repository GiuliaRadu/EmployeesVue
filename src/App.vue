<template>
  <div id="app">
    <Form/>
    <Filters/>
    <Table/>
  </div>
</template>

<script>
import Form from './components/Form.vue'
import Table from './components/Table.vue'
import Filters from './components/Filters.vue'

export default {
  name: 'App',
  components: {
    Form,
    Table,
    Filters
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
