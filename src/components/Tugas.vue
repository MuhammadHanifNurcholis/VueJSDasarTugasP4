<script setup>
import { ref } from "vue";
import CounterComponent from "./CounterComponent.vue";
// Variabel reaktif
const message = ref("👋 SELAMAT DATANG !!!");
const userInput = ref("");
const isVisible = ref(true);

// Fungsi toggle teks
const toggleVisibility = () => {
  isVisible.value = !isVisible.value;
};
</script>

<template>
  <div class="container">
    <!-- Text Interpolation -->
    <h1 class="title">{{ message }}</h1>

    <!-- Form Binding -->
    <div class="input-container">
      <label for="inputBox">Masukkan Nama Anda:</label>
      <input
        id="inputBox"
        v-model="userInput"
        placeholder="Ketik nama Anda..."
      />
      <p v-if="userInput" class="greeting">
        ✨ Halo, <strong>{{ userInput }}</strong
        >! 👋
      </p>
    </div>

    <!-- Conditional Rendering dengan Animasi -->
    <button @click="toggleVisibility" class="toggle-btn">
      {{ isVisible ? "🙈 Sembunyikan" : "👀 Tampilkan" }} Pesan
    </button>

    <transition name="fade">
      <p v-if="isVisible" class="message-box">🎉 Semangat Belajas Vue js</p>
    </transition>

    <!-- Komponen terpisah untuk counter -->
    <CounterComponent />
  </div>
</template>

<style scoped>
/* Container utama */
.container {
  font-family: "Poppins", sans-serif;
  text-align: center;
  margin: 50px auto;
  max-width: 420px;
  padding: 25px;
  border-radius: 12px;
  background: linear-gradient(135deg, #f8f9fa, #e9ecef);
  box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease-in-out;
}

.container:hover {
  transform: translateY(-5px);
}

/* Judul */
.title {
  font-size: 24px;
  font-weight: bold;
  color: #333;
  margin-bottom: 15px;
}

/* Input Container */
.input-container {
  margin-bottom: 20px;
}

label {
  font-weight: bold;
  display: block;
  margin-bottom: 5px;
}

input {
  padding: 10px;
  width: 85%;
  border: 2px solid #007bff;
  border-radius: 6px;
  outline: none;
  font-size: 16px;
  transition: 0.3s;
}

input:focus {
  border-color: #0056b3;
  box-shadow: 0px 0px 8px rgba(0, 91, 187, 0.5);
}

/* Greeting */
.greeting {
  margin-top: 10px;
  font-size: 18px;
  color: #007bff;
}

/* Tombol */
.toggle-btn {
  margin: 15px 0;
  padding: 12px 18px;
  font-size: 16px;
  font-weight: bold;
  border: none;
  background: #007bff;
  color: white;
  border-radius: 6px;
  cursor: pointer;
  transition: background 0.3s, transform 0.2s;
}

.toggle-btn:hover {
  background: #0056b3;
}

.toggle-btn:active {
  transform: scale(0.95);
}

/* Pesan yang bisa disembunyikan */
.message-box {
  padding: 10px;
  font-size: 18px;
  color: #28a745;
  background: #d4edda;
  border-radius: 8px;
  margin-top: 10px;
}

/* Animasi Fade-in/Fade-out */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
