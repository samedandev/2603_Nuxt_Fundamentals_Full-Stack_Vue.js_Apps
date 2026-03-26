<script setup>
const route = useRoute();
const { data } = useAsyncData(`/movies/${route.params.id}`, () => {
  return $fetch(`http://www.omdbapi.com/?apikey=dc846edc&i=${route.params.id}`);
});
</script>

<template>
  <div>
    <h1>{{ $route.params.id }}</h1>
    <pre>    {{ data }}</pre>
  </div>
</template>
