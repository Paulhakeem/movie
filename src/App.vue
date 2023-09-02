<script setup>
import { ref } from "vue";
import {RouterLink, RouterView } from "vue-router";
const showMenu = ref(false)
</script>

<template>
  <div id="app" class="">
  <div class="justify-start">
    <div class="">
      <nav class="flex container px-5 py-5">
        <ul class=" justify-start flex flex-grow space-x-4">
          <li>
            <a
              href="/"
              class="flex space-x-3 md:mr-5"
              >
            <h1 class="text-4xl text-white font-semibold">Hakeem<span class="text-university">Movies</span></h1>
                
            </a>
          </li>
        </ul>
        <ul class="flex space-x-5">
          <li class="hidden sm:flex">
            <RouterLink to="/"
              class="text-gray-200 hover:text-university text font-semibold py-1 px-3"
              >Home
            </RouterLink>
              
          </li>
          <li class="hidden sm:flex">
            <RouterLink to=""
              class="text-gray-200 hover:text-university text font-semibold py-1 px-3"
              >Series
            </RouterLink>
              
          </li>
          <li class="hidden sm:flex">
            <RouterLink to=""
              class="text-gray-200 hover:text-university text font-semibold py-1 px-3"
              >Movies
            </RouterLink>
              
          </li>
           <li class="hidden sm:flex">
            <RouterLink to=""
              class="text-gray-200 hover:text-university text font-semibold py-1 px-3"
              >Sport
            </RouterLink>
          </li>
        </ul>
        <ul class="flex sm:hidden" @click="showMenu = !showMenu">
          <li>
            <a href="#" class="flex-none absolute right-0 px-5 z-30"
              >
              <p
                class="text-gray-200 font-semibold tracking-wide hover:bg-gray-900 hover:bg-opacity-30 rounded px-2 py-2"
                >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  fill="none"
                  viewBox="0 0 24 24"
                  stroke="currentColor"
                  class="h-6 w-6"
                  >
                  <path
                    stroke-linecap="round"
                    stroke-linejoin="round"
                    stroke-width="2"
                    d="M4 6h16M4 12h16m-7 6h7"
                    ></path>
                </svg>
              </p
                >
            </a>
            <div
              class="absolute top-0 right-0 z-10 h-screen w-full bg-black transition"
              :class="{
              'invisible opacity-0': !showMenu,
              'visible opacity-40': showMenu,
              }"
              ></div>
            <div
              class="absolute right-0 z-20 w-full px-5 mt-16 transition"
              :class="{
              'invisible opacity-0': !showMenu,
              'visible opacity-100': showMenu,
              }"
              >
              <ul
                class="flex flex-col bg-gray-100 w-full rounded shadow-md overflow-hidden"
                >
                <li class="flex">
                  <h3 class="flex flex-1 text-gray-600  font-semibold px-5 py-4">
                    Menu
                  </h3>
                </li>
                <li class="flex border-t">
                 <RouterLink to="/"
                    class="flex flex-1 text-lg text-gray-700 hover:bg-university hover:text-white font-semibold px-8 py-4"
                    >Home
                    </RouterLink>
                </li>
                <li class="flex">
                  <RouterLink to=""
                    class="flex flex-1 text-lg text-gray-700 hover:bg-university hover:text-white font-semibold px-8 py-4"
                    >Series
                    </RouterLink>
                </li>
                <li class="flex">
                  <RouterLink to=""
                    class="flex flex-1 text-lg text-gray-700 hover:bg-university hover:text-white font-semibold px-8 py-4"
                    >Movies
                    </RouterLink>
                </li>
                <li class="flex">
                  <RouterLink to=""
                    class="flex flex-1 text-lg text-gray-700 hover:bg-university hover:text-white font-semibold px-8 py-4"
                    >Sport
                    </RouterLink>
                </li>
                <li class="flex">
                  <RouterLink to=""
                    class="flex flex-1 text-lg text-gray-700 hover:bg-university hover:text-white font-semibold px-8 py-4"
                    >My list
                    </RouterLink>
                </li>
              </ul>
            </div>
          </li>
        </ul>
      </nav>
    </div>
  </div>
</div>
  <RouterView />
</template>
