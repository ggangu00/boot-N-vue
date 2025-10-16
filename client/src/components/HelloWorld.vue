<template>
  <div class="hello container">
    <div id="table"></div>
    <h1>{{ msg }}</h1>
  </div>
</template>

<script setup>
import { Tabulator } from 'tabulator-tables'; //import Tabulator library
import { onMounted, ref } from 'vue';
import 'tabulator-tables/dist/css/tabulator.min.css'

const tabulator  = ref(null);
const tableData  = ref([
    { id: 1, name: "Oli Bob", progress: 12, gender: "male" },
    { id: 2, name: "Mary May", progress: 1, gender: "female" },
    { id: 3, name: "Christine Lobowski", progress: 42, gender: "female" },
]);

onMounted(() => {
    tabulator.value = new Tabulator("#table", {
      data: tableData.value, 
      columns: [
      { title: "ID", field: "id", width: 50 },
      { title: "Name", field: "name" },
      { title: "Progress", field: "progress", hozAlign: "right" },
      { title: "Gender", field: "gender" },
    ],
    });
})
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>