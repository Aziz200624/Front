<template>
    <div class="container mx-auto p-4">
      <h1 class="text-2xl font-bold mb-4">Видео и Аудио в Nuxt.js</h1>
  
      <!-- Видео -->
      <div class="mb-6">
        <h2 class="text-xl font-semibold mb-2">Видео</h2>
        <video controls class="w-full max-w-lg rounded-lg shadow-lg">
          <source src="/video/sample.mp4" type="video/mp4" />
          Ваш браузер не поддерживает видео.
        </video>
      </div>
  
      <!-- Аудио -->
      <div>
        <h2 class="text-xl font-semibold mb-2">Аудио</h2>
        <audio controls class="w-full max-w-md">
          <source src="/audio/sample.mp3" type="audio/mp3" />
          Ваш браузер не поддерживает аудио.
        </audio>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  
  // Пример реактивных данных
  const videoList = ref([
    { src: "/video/sample.mp4", type: "video/mp4" },
  ]);
  
  const audioList = ref([
    { src: "/audio/sample.mp3", type: "audio/mp3" },
  ]);
  </script>
  
  <style scoped>
  .container {
    text-align: center;
  }
  </style>
  