<script setup>

const props = defineProps(['selectedEmployee']);

</script>

<template>
  <div class="main-content">
    <div class="avatar">
      <img v-bind:src="'src/assets/images/' + props.selectedEmployee.image" alt="avatar">
    </div>
    <div class="employee-information">
      <p class="name">
        {{ props.selectedEmployee.name}}
      </p>
      <div class="popularity">
        <div>
          Popularity
        </div>
        <div class="form-slider">
          <input type="range" min="1" max="100" :value="props.selectedEmployee.popularity" class="slider" id="myRange" disabled>
        </div>
      </div>
      <div class="biography">
        <div class="title">Biography</div>
        <div class="text">
          {{ props.selectedEmployee.biography }}
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.main-content {
  z-index: 999;
  margin: 70px 0;
  display: flex;
  gap: 30px;
  color: white;
  text-align: left;
  padding: 100px 40px 0;
}
.name{
  margin-top: 0;
  font-size: 28px;
}
.popularity, .biography .title {
  font-size: 20px;
}
.popularity {
  margin-top: 0;
  display: flex;
  gap: 20px;
  margin-bottom: 30px;
  align-items: center
}
.biography {
  padding: 15px;
  background-color: rgba(26,29,36,255);
}

.biography .text {
  font-size: 14px;
}

.avatar img {
  width: 100px;
  height: 100px;
  border: 1px solid rgba(80,68,69,255);
}
.form-slider {
  width: 100%;
}
.slider {
  -webkit-appearance: none;
  appearance: none;
  width: 100%;
  height: 2px;
  background: black;
  outline: none;
  opacity: 0.7;
  -webkit-transition: .2s;
  transition: opacity .2s;
}

.slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 20px;
  height: 20px;
  background: #fff;
  border-radius: 50%;
  cursor: pointer;
}
</style>