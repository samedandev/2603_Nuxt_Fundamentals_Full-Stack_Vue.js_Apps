<script setup>
const route = useRoute();

const { data } = useFetch(
  `http://www.omdbapi.com/?apikey=dc846edc&i=${route.params.id}`,
  // to test 500 error for onResponseError
  // `https://httpbin.org/status/500`,
  {
    pick: ["Plot", "Title"],
    key: `/movies/${route.params.id}`,
    onResponse({ request, response }) {
      console.log(response);
      if (response._data.Error === "Incorrect IMDb ID.") {
        showError({ statusCode: 404, statusMessage: "Page not found" });
      }
    },
    // onResponseError() {
    //   showError({ statusCode: 500, statusMessage: "Oh; nO! Status 500 Error" });
    // },
  },
);
</script>

<template>
  <div>
    <h1>{{ $route.params.id }}</h1>
    <pre>    {{ data }}</pre>
  </div>
</template>
