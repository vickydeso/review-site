<template>
    <div class="container">
      <header>
        <input type="text" v-model="searchQuery" placeholder="Search movies...">
      </header>
  
      <main>
        <Suspense>
          <MovieList v-if="filteredMovies.length > 0" :movies="filteredMovies" />
          <h1 v-else>No movies found</h1>
        </Suspense>
      </main>
    </div>
  </template>
  
  <script setup>
    import { ref, computed } from 'vue';
  
    const { data } = await useFetch('https://review-site-txzr.onrender.com/api/movies?populate=imgURL');
  
    const searchQuery = ref('');
  
    const filteredMovies = computed(() => {
      return data ? data.filter(movie => {
        return movie.attributes.title.toLowerCase().includes(searchQuery.value.toLowerCase());
      }) : [];
    });
  </script>
  
  <style scoped>
  </style>

Home.vue