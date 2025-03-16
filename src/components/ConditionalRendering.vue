<script setup>
import { ref } from "vue";

const isLoggedIn = ref(false);

const toggleLogin = () => {
  isLoggedIn.value = !isLoggedIn.value;
};
</script>

<template>
  <div>
    <button @click="toggleLogin">
      {{ isLoggedIn ? "🚪 Logout" : "🔑 Login" }}
    </button>

    <p v-if="isLoggedIn">🎉 Selamat datang, User! 😃</p>
    <p v-else>🔒 Silakan login terlebih dahulu. ⛔</p>
  </div>
</template>

<style scoped>
button {
  margin-bottom: 10px;
  padding: 8px 12px;
  font-size: 16px;
  cursor: pointer;
}
p {
  font-size: 18px;
}
</style>
