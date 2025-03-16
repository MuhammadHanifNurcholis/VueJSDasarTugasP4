<script setup>
import { ref } from "vue";

// Variabel reaktif
const count = ref(0);

// Fungsi event listener untuk menambah angka
const increment = () => {
  count.value++;
};
</script>

<template>
  <div class="counter-box">
    <h2>Counter</h2>
    <p>Jumlah Klik: {{ count }}</p>

    <!-- Attribute Binding dan Event Listener -->
    <button :disabled="count >= 10" @click="increment">Tambah (+)</button>

    <p v-if="count >= 10" class="warning-text">
      Anda telah mencapai batas maksimal!
    </p>
  </div>
</template>

<style scoped>
.counter-box {
  margin-top: 20px;
  padding: 15px;
  border-radius: 10px;
  background: #fff;
  box-shadow: 0px 4px 6px rgba(0, 0, 0, 0.1);
  text-align: center;
}

.warning-text {
  color: red;
  font-weight: bold;
}
</style>
