<script setup>
import { ref } from 'vue'

const count = ref(0)
const increment = () => {
  count.value++;
};

</script>

<template>
  <div>
    <p>Jumlah Klik; {{ count }}</p>
    <button @click="increment">klik Saya!</button>
  </div>
</template>

<style scoped> 
button {
  margin-top: 10px;
  padding: 10px;
  cursor: pointer;
}
</style>