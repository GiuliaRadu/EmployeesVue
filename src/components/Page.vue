<template>
  <div>
    <Form />
    <Filters />
    <Table />
  </div>
</template>

<script>
import Form from './Form'
import Filters from './Filters'
import Table from './Table'


export default {
  name: 'Page',
  components: {
    Form,
    Table,
    Filters
  }
}
</script>