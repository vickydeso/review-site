<template>
  <MovieList :movies="data" />
</template>

<script setup>
const { data } = await useFetch('http://localhost:1337/api/movies?populate=imgURL')
</script>
