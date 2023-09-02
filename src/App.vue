<script setup>
import {RouterLink, RouterView } from "vue-router";
</script>

<template>
  <div class="flex justify-start ml-6 mr-6 pt-6 space-x-8 text-white">
    <RouterLink to="/">
      <button class="bg-white rounded-full p-2 text-primary font-semibold">
      Home
    </button>
    </RouterLink>
   
    <button
      class="hover:bg-white rounded-full p-2 hover:text-primary font-semibold"
    >
      Series
    </button>
    <button
      class="hover:bg-white rounded-full p-2 hover:text-primary font-semibold"
    >
      Movies
    </button>
    <button
      class="hover:bg-white rounded-full p-2 hover:text-primary font-semibold"
    >
      Sport
    </button>
    <button
      class="hover:bg-white rounded-full p-2 hover:text-primary font-semibold"
    >
      My list
    </button>


    

  </div>
  <RouterView />
</template>
