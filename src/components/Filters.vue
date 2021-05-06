<template>
  <div>
    <button id="sortButton" sort="up">Sort by date</button>
    <label>Filter By Gender: </label>
    <select id="filterGender" required>
      <option value="" selected disabled hidden>Choose here</option>
      <option value="None">None</option>
      <option value="Male">Male</option>
      <option value="Female">Female</option>
      <option value="Other">Other</option>
    </select>
  </div>
</template>


<script>
export default {
  name: "Filters",
};
</script>

<style scoped>
</style>