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
import $ from "jquery";
 
export default {
  name: "Table",
  data() {
    return {
      employeesList: [],
    };
  },
  async created() {
    let self = this;
    $.ajax({
      method: "GET",
      url: "https://localhost:5001/employee/Employee",
      success: function(data) {
        this.employeesList = data;
        self.loadEmployees(this.employeesList);
      },
      error: function() {
        alert(`Failed to get employees list.`);
      },
    });
  },
  methods: {
    loadEmployees(employeesList){
        let dataTable = document.getElementById('dataTable');
        for (var index = 0; index < employeesList.length; index++)
        { 
            this.appendDataToTable(dataTable,employeesList[index])
        }
    },
    appendDataToTable(tableNode, data) {
        const row = document.createElement('tr');

        for(const key in data){
            const cell = document.createElement('td');
            if(key === "id"){
                continue;
            }
            if (key === "img") {
                // const img = document.createElement('img');
                continue;
                
            }
            if(key === "birthdate"){
                cell.innerText = data[key].split("T")[0];
            }   
            else{
                cell.innerText = data[key];
            }            
            row.appendChild(cell);
        }
        if (tableNode.children.length < 2) {
            console.log("Table doesent contain body")
            return;
        }
        let button = document.createElement('button');
        row.appendChild(button)
        button.onclick = function() {
            row.remove();
            $.ajax({
            method: "DELETE",
            url: `https://localhost:5001/employee/Employee/${data.id}`,
            error: function () {
                alert(`Failed to remove employee from list`);
            },
        });
        };

        tableNode.children[1].appendChild(row);
    },

  },
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

tr{
    border: 1px solid black;
}
</style>