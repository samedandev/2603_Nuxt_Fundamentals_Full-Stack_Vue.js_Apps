<script setup>
const query = ref("");
const movies = ref([]);
async function search() {
  const { Search } = await $fetch(
    `http://www.omdbapi.com/?i=tt3896198&apikey=dc846edc&s=${query.value}`,
  );
  movies.value = Search;
}
</script>

<template>
  <form @submit.prevent="search">
    <input type="search" v-model="query" />
    <button>Search</button>
  </form>
  <ul style="display: flex; flex-wrap: wrap; gap: 10px; list-style: none">
    <li v-for="movie in movies" :key="movie.imdbID">
      <NuxtLink :to="{ name: 'movies-id', params: { id: movie.imdbID } }">
        <img :src="movie.Poster" :alt="movie.title" />
      </NuxtLink>
    </li>
  </ul>
</template>

<style scoped></style>
