<script setup>
import { ref } from "vue";
import { RouterLink } from "vue-router";
import api from "../api";

const search = ref("")
const movies = ref([])

const searchMovie = () => {
  if (movies.value != " ") {
    fetch(`https://www.omdbapi.com/?apiKey=${api.apiKey}&s=${search.value}`)
    .then(response => response.json())
    .then(data => {
      console.log(data)
    })
  }
  
}
</script>

<template>
  <div class="grid md:grid-cols-2 ml-12 mr-12 pt-14 m-auto sm:grid-cols-2">
    <div>
      <img src="../assets/guardian.jpg" alt="Gardian Of Galaxy" />
    </div>

    <div class="pl-10 mt-10">
      <h1 class="text-white text-4xl font-semibold tracking-wide pb-4">
        Guadians Of The Galaxy
      </h1>
      <p class="text-white text-sm">
        Guardians of the Galaxy (retroactively referred to as Guardians of the
        Galaxy Vol. 1)[4][5] is a 2014 American superhero film based on the
        Marvel Comics superhero team of the same name. Produced by Marvel
        Studios and distributed by Walt Disney Studios Motion Pictures, it is
        the 10th film in the Marvel Cinematic Universe (MCU). Directed by James
        Gunn, who wrote the screenplay with Nicole Perlman, it features an
        ensemble cast including Chris Pratt, Zoe Saldaña, Dave Bautista, Vin
        Diesel, and Bradley Cooper as the titular Guardians, along with Lee
        Pace, Michael Rooker, Karen Gillan, Djimon Hounsou, John C. Reilly,
        Glenn Close, and Benicio del Toro. In the film, Peter Quill and a group
        of extraterrestrial criminals go on the run after stealing a powerful
        artifact.
      </p>
      <div class="md:gap-2 sm:gap-2 space-x-4">
        <RouterLink to="/movie/a814f15d">
          <button
            class="bg-white text-primary p-2 rounded-full w-40 mt-8 font-semibold tracking-wider hover:bg-primary hover:text-white hover:border hover:border-1 hover:border-white"
          >
            Movie details
          </button>
        </RouterLink>
        <button
          class="hover:bg-white hover:text-primary p-2 rounded-full w-40 mt-8 font-semibold tracking-wider bg-primary text-white border border-1 border-white"
        >
          Play Now
        </button>
      </div>
    </div>
  </div>
  <div class="flex flex-wrap gap-4 text-center justify-center pt-20 space-y-10">
    <form @submit="searchMovie">
      <input
        v-model="search"
        class="bg-primary border border-1 border-white rounded-full p-2 w-96 outline-none text-gray-400"
        type="text"
        placeholder="What are you looking?"
      />
      <button
        class="ml-4 bg-white text-primary rounded-full p-2 font-semibold w-56"
      >
        Search
      </button>
    </form>
  </div>
  <div class="pt-8 ml-12 mr-12">
    <h2 class="text-white uppercase underline">Movies and series</h2>
  </div>
</template>
