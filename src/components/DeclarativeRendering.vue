<script setup>
import { ref } from 'vue'
const message = ref('Hello, VueJS!')

const updateMessage = () => {
  message.value = 'Selamat Datang , Hanif Di Vuejs!';
}

</script>

<template>
  <div>
    <h1>{{ message }}</h1>
    <button @click="updateMessage">Klik untuk mengubah pesan</button>
  </div>
</template>

<style scoped>
button {
  margin-top: 10px;
  padding: 10px;
  font-size: 16px;
  cursor: pointer;
}
</style>