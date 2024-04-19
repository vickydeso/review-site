<template>
  <MovieList :movies="data" />
</template>

<script setup>
  // import MovieList from './components/MovieList.vue'
  const { data } = await useFetch('https://review-site-txzr.onrender.com/api/movies?populate=imgURL')



</script>


