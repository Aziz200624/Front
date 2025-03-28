<template>
    <div class="flex flex-col gap-4 p-12 justify-center min-h-screen items-center bg-gradient-to-b from-gray-200 to-blue-300 hover:to-red-300 flex-wrap">
      <div class="flex flex-row gap-4 flex-wrap">
        <label><input class="mx-2" type="radio" value="tursynbek" v-model="selectedPic">Tursynbek</label>
        <label><input class="mx-2" type="radio" value="kanat" v-model="selectedPic">Kanat</label>
        <label><input class="mx-2" type="radio" value="erkebulan" v-model="selectedPic">Erkebulan</label>
      </div>
  
      <div class="flex flex-row gap-4 flex-wrap">
        <div class="block p-4" v-if="selectedPic == 'tursynbek'">
          <img :src="pic1.image" class="w-60 h-50">
          <p class="text-black text-xl">{{ pic1.name }}</p>
        </div>
  
        <div class="block p-4" v-if="selectedPic == 'kanat'">
          <img :src="pic2.image" class="w-60 h-50">
          <p class="text-black text-xl">{{ pic2.name }}</p>
        </div>
  
        <div class="block p-4" v-if="selectedPic == 'erkebulan'">
          <img :src="pic3.image" class="w-60 h-50">
          <p class="text-black text-xl">{{ pic3.name }}</p>
        </div>
      </div>
  
      <div class="flex flex-row gap-4 flex-wrap">
        <div class="block p-4" v-for="(pic, index) in genpic" :key="index">
          <img :src="pic.image" class="w-60 h-50">
          <p class="text-black text-xl">{{ pic.name }}</p>
        </div>
      </div>
    </div>
  </template>
  <script setup lang="ts">
  import { reactive, ref } from "vue";
  
  interface Person {
    name: string;
    image: string;
  }
  
  const pic1 = reactive<Person>({
    name: "Tursynbek",
    image: "/img/tursynbek.png",
  });
  
  const pic2 = reactive<Person>({
    name: "Kanat",
    image: "/img/kanat.png",
  });
  
  const pic3 = reactive<Person>({
    name: "Erkebulan",
    image: "/img/erkebulan.png",
  });
  
  const genpic = reactive([
    { name: "Kanat", image: "/img/kanat.png" },
    { name: "Tursynbek", image: "/img/tursynbek.png" },
    { name: "Erkebulan", image: "/img/erkebulan.png" },
  ]);
  
  const selectedPic = ref<string>("");
  </script>
  <style scoped>
  .block p {
    display: flex;
    flex-direction: column;
    gap: 2;
    border: 2px solid blue;
    width: 7rem;
    justify-content: center;
    align-items: center;
    border-radius: 1rem;
    transition: 0.3s;
  }
  
  .block:hover {
    border-color: red;
    background-color: red-300;
  }
  </style>
  