<template>
  <Suspense>
      <MovieList v-if="data" :movies="data" />
      <h1 v-else id="null-data">Hello World</h1>
  </Suspense>
</template>

<script setup>
  const { data } = await useFetch('https://review-site-txzr.onrender.com/api/movies?populate=imgURL')
</script>
