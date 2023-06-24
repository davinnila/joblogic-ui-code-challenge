<script setup>
const props = defineProps(['employees', 'selectedEmployeeName']);

</script>

<template>
  <div class="side-bar">
    <div class="logo">
      <img src="../assets/images/the-godfather.svg" alt="">
    </div>
    <div class="list-name-employee">
      <div v-for="employee in props.employees" v-bind:key="employee.name" :class="{ active: props.selectedEmployeeName === employee.name }">
        <span @click="$emit('changeEmployee', employee.name)">
          {{ employee.name }}
        </span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.side-bar {
  z-index: 999;
  padding: 50px 0;
  background-image: linear-gradient(to right, rgba(255,0,0,0), rgba(0, 0, 0, 0.493));
}
.logo {
  padding: 0 60px;
}
.logo img{
  height: 100px;
}
.list-name-employee {
  padding-top: 75px;
}
.list-name-employee span {
  color: rgba(58,212,250,255);
  cursor: pointer;
  padding: 5px 0;
}
.list-name-employee .active {
  font-size: 24px;
  background-color: rgba(64,65,70,255);
}
</style>
