<script setup>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import api from '../api';

const movie = ref({})
const route = useRoute()

onBeforeMount(() => {
    fetch(`https://www.omdbapi.com/?apiKey=${api.apiKey}&i=${route.params.id}&plot=full`)
    .then((response) => response.json())
      .then((data) => {
        console.log(data)
       movie.value = data

      });
})
</script>
<template>
    <div class="movie flex gap-8 ml-8 mr-8 mt-10 select-none">
        <img :src="movie.Poster" :alt="movie.Poster" class="cover">
        <div to="" class="text-gray-300 gap-4 ml-4 mr-4">
        <h1 class="text-4xl font-bold mb-4"><span class="text-university">Title:</span> {{ movie.Title }}</h1>
        <p class="text-university font-semibold">Actors: <span class="font-light text-gray-300">{{ movie.Actors }}</span></p>
        <p class="text-university font-semibold">Released year: <span class="font-light text-gray-300">{{ movie.Released }}</span></p>
        <p class="text-university font-semibold">Genre: <span class="font-light text-gray-300">{{ movie.Genre }}</span></p>
        <p class="text-university font-semibold">Rated: <span class="font-light text-gray-300">{{ movie.Rated }}</span></p>
        <p class="text-university font-semibold">Language: <span class="font-light text-gray-300">{{ movie.Language }}</span></p>
        <p class="text-university font-semibold">Description: <span class="italic font-light text-gray-300">{{ movie.Plot }}</span></p>
        <p class="text-university font-semibold">Runtime: <span class="font-light text-gray-300">{{ movie.Runtime }}</span></p>
        </div>  
    </div>
</template>