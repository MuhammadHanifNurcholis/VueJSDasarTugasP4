<script setup>
import { ref } from "vue";

const textColor = ref("black");
const colors = ["red", "blue", "green", "purple", "orange", "black"];

const changeColor = () => {
  textColor.value = colors[Math.floor(Math.random() * colors.length)];
};
</script>

<template>
  <div>
    <h2 :style="{ color: textColor }">Teks ini akan berubah warna!</h2>
    <button @click="changeColor">Ganti Warna</button>
  </div>
</template>

<style scoped>
button {
  margin-top: 10px;
  padding: 8px 12px;
  cursor: pointer;
}
</style>
