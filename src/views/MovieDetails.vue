<script setup>
import { ref, onBeforeMount } from 'vue';
import { useRoute } from 'vue-router';
import api from '../api';

const movie = ref({})
const route = useRoute()

onBeforeMount(() => {
    fetch(`https://www.omdbapi.com/?apiKey=${api.apiKey}&i=${route.params.id}&plot=full`)
})
</script>
<template>
    <div>
        <h2>Movie title</h2>
    </div>
</template>