<script setup>
import { ref } from 'vue';
import SideBar from './components/SideBar.vue';
import MainContent from './components/MainContent.vue';
import employees from './data/employees';

const selectedEmployee = ref(employees[0]);

function changeEmployee(employeeName) {
  const currentEmployee = employees.find(employee => employee.name === employeeName);
  selectedEmployee.value = currentEmployee;
}

</script>

<template>
  <div class="main-page">
    <div class="background-image">

    </div>
    <img src="./assets/images/Godfather-header.jpg" alt="background image">
    <SideBar :employees="employees" :selectedEmployeeName="selectedEmployee.name" @change-employee="changeEmployee"/>
    <MainContent :selectedEmployee="selectedEmployee"/>
  </div>
</template>

<style scoped>
.main-page {
  /* background-image: url('./assets/images/Godfather-header.jpg'); */
  /* background-position: 100% 30%; */
  background-color: rgba(46,46,54,255);
  display: flex;
  max-width: 1200px;
  height: 70vh;
}
.background-image {
  max-width: 1200px;
}
img {
  position: absolute;
  height: 210px;
  width: 1200px;
}
</style>
