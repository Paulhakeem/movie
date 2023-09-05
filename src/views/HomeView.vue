<script setup>
import { ref } from "vue";
import { useRoute, RouterLink } from "vue-router";
import api from "../api";

const search = ref("");
const movies = ref([]);


const searchMovie = () => {
  if (movies.value != " ") {
    fetch(`https://www.omdbapi.com/?apiKey=${api.apiKey}&s=${search.value}`)
      .then((response) => response.json())
      .then((data) => {
        movies.value = data.Search;
        search.value = "";
      });
  }
};

</script>

<template>
  <div class="grid md:grid-cols-2 ml-6 mr-6 pt-14 m-auto sm:grid-cols-2">
    <div>
      <img src="../assets/guardian.jpg" alt="Gardian Of Galaxy" class=""/>
    </div>

    <div class="ml-4 mr-4 mt-5">
      <h1 class="text-white text-3xl font-semibold tracking-wide pb-4">
        Guardians Of The Galaxy
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
      <div class="gap-6 flex flex-wrap">
        <div>
          <RouterLink to="">
            <button
              class="bg-university text-white p-2 rounded-full w-40 mt-8 font-semibold tracking-wider hover:bg-primary hover:border hover:border-1 hover:border-university"
            >
              Movie details
            </button>
          </RouterLink>
        </div>
        <div>
          <button
            class="hover:bg-university p-2 rounded-full w-40 mt-8 font-semibold tracking-wider text-white border border-1 border-university"
          >
            Play Now
          </button>
        </div>
      </div>
    </div>
  </div>
  <div class="pt-20">
    <form
      @submit.prevent="searchMovie"
      class="ml-2 mr-2 flex flex-wrap gap-4 text-center justify-center"
    >
      <input
        v-model="search"
        class="input bg-primary border border-1 border-white rounded-full p-2 w-96 outline-none text-gray-400 hover:border-university"
        type="text"
        placeholder="Looking for a movie?"
      />
      <button
        class="ml-4 bg-university text-white rounded-full p-2 font-semibold w-56"
      >
        Search
      </button>
    </form>
  </div>
  <div class="pt-8 ml-12 mr-12 text-center justify-center items-center">
    <h2
      class="text-white uppercase border-2 border-university p-1 w-full rounded-md"
    >
      Movies and series
    </h2>
  </div>
  <div class="flex flex-wrap ml-4 mr-4">
    <div
      class="max-w-md flex-1 basis-12 pt-10 pb-10 pl-4 pr-4"
      v-for="movie in movies"
      :key="movie.imdbID"
    >
      <RouterLink :to="'/movie/' + movie.imdbID" class="flex flex-col h-full">
        <div>
          <img :src="movie.Poster" alt="" />
        </div>
        <div
          class="bg-university text-white uppercase p-0.2 mt-6 text-center rounded-md"
        >
          {{ movie.Type }}
        </div>
        <div class="flex flex-wrap mt-4 gap-2 font-normal">
          <h3 class="text-gray-400 font-medium text-base">{{ movie.Title }}</h3>
        </div>
      </RouterLink>
    </div>
  </div>
</template>
