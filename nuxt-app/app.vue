<template>
  <header class="container">

  </header>

  <main class="container">
    <Suspense>
        <MovieList v-if="data" :movies="data.data" />
        <!-- <p v-if="data"> {{ data }} </p> -->
        <h1 v-else>Null Data</h1>
    </Suspense>
  </main>

  <footer class="container">

  </footer>
</template>

<script setup>
  const { data } = await useFetch('https://strapi-v2-wjlk.onrender.com/api/movies?populate=imgURL')
</script>
