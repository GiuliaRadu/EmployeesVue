<template>
  <table id="dataTable">
    <thead>
      <tr>
        <th>First Name</th>
        <th>Last Name</th>
        <th>Email</th>
        <th>Sex</th>
        <th>Date of birth</th>
        <th>Profile picture</th>
      </tr>
    </thead>
    <tbody></tbody>
  </table>
</template>

<script>
export default {
  name: "Table",
};
</script>

<style scoped>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  border: 1px solid #dddddd;
  text-align: left;
  padding: 8px;
}
</style>