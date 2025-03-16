<script setup>
import { ref } from 'vue'

const name = ref("");

</script>

<template>
  <div>
    <input v-model="name" placeholder="Masukkan Nama..."/>
    <P >Nama: {{ name }}</P>
  </div>
</template>

<style scoped>
input {
  padding: 5px;
  margin: 5px 0;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>