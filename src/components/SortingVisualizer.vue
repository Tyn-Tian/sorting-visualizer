<template>
  <div class="array-container">
    <div class="array-bar" v-for="n in arr" :style="{ height: n + 'px' }"></div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";

const arr = ref([]);

const resetArr = () => {
  arr.value = [];
  for (let i = 0; i < 100; i++) {
    arr.value.push(randomIntFromInterval(5, 550));
  }
};

const randomIntFromInterval = (min, max) => {
  return Math.floor(Math.random() * (max - min + 1) + min);
};

onMounted(() => {
  resetArr();
});
</script>

<style scoped>
.array-container {
  width: 100%;
  display: flex;
  justify-content: center;
}

.array-bar {
  width: 10px;
  display: inline-block;

  background-color: #42b883;
  margin: 0 1px;
}
</style>
