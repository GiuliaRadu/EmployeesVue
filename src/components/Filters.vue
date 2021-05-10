<template>
  <div>
    <button id="sortButton" sort="up" @click="sortByDate()">
      Sort by date
    </button>
    <label>Filter By Gender: </label>
    <select id="filterGender" required @change="filterByGender()">
      <option value="" selected disabled hidden>Choose here</option>
      <option value="None">None</option>
      <option value="Male">Male</option>
      <option value="Female">Female</option>
      <option value="Other">Other</option>
    </select>
  </div>
</template>


<script>
// import $ from "jquery";
export default {
  name: "Filters",
  props: {},
  methods: {
    sortByDate() {
      let dataTable = document.getElementById("dataTable");
      var sortAttribute = document
        .getElementById("sortButton")
        .getAttribute("sort");
      if (sortAttribute == "up") {
        document.getElementById("sortButton").setAttribute("sort", "down");
      } else {
        document.getElementById("sortButton").setAttribute("sort", "up");
      }

      var rows, switching, index, x, y, shouldSwitch;
      switching = true;

      while (switching) {
        switching = false;
        rows = dataTable.rows;
        for (index = 1; index < rows.length - 1; index++) {
          shouldSwitch = false;
          x = new Date(rows[index].getElementsByTagName("td")[4].innerText);
          y = new Date(rows[index + 1].getElementsByTagName("td")[4].innerText);
          if (sortAttribute == "up") {
            if (x < y) {
              shouldSwitch = true;
              break;
            }
          } else if (sortAttribute == "down") {
            if (x > y) {
              shouldSwitch = true;
              break;
            }
          }
        }
        if (shouldSwitch) {
          rows[index].parentNode.insertBefore(rows[index + 1], rows[index]);
          switching = true;
        }
      }
    },
    filterByGender() {
      let dataTable = document.getElementById("dataTable");
      let filter = document.getElementById("filterGender").value;
      console.log(filter);
      let tr = dataTable.getElementsByTagName("tr");
      console.log(tr);

      for (var index = 1; index < tr.length; index++) {
        var td = tr[index].getElementsByTagName("td")[3];
        if (td) {
          var genderValue = (td.textContent || td.innerText).toLowerCase();
          if (
            genderValue == filter.toLowerCase() ||
            filter.toLowerCase() == "none"
          ) {
            tr[index].style.display = "";
          } else {
            tr[index].style.display = "none";
          }
        }
      }
    },
  },
};
</script>

<style scoped>
</style>