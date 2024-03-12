<template>
  <div class="container">
    <button class="btn" @click="resetArr">Generate New Array</button>
    <button class="btn" @click="mergeSortArr">MergeSort</button>
  </div>
  <div class="array-container">
    <div class="array-bar" v-for="n in arr" :style="{ height: n + 'px' }"></div>
  </div>
</template>

<script setup>
import { onMounted, ref } from "vue";
import randomIntFromInterval from "@/composables/getRandomInt";
import { mergeSort } from "@/composables/sortingAlgorithms";

const arr = ref([]);

const resetArr = () => {
  arr.value = [];
  for (let i = 0; i < 100; i++) {
    arr.value.push(randomIntFromInterval(5, 550));
  }
};

const mergeSortArr = () => {
  console.log("do merge sort");
};

onMounted(() => {
  resetArr();
});
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  gap: 20px;
}

.btn {
  width: fit-content;
  height: fit-content;

  font-weight: 600;
  font-size: 18px;
  color: #35495e;

  border: none;
  border-radius: 4px;
  background-color: #42b883;
  padding: 15px 30px;
  margin-bottom: 35px;

  cursor: pointer;
}

.btn:hover {
  color: #42b883;

  background-color: #35495e;
}

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
