<template>
  <div class="movie-list">
    <ul>
      <li v-for="movie in movies" :key="movie.id" class="movie-item">
        <div class="movie-item-info">
          <h2>{{ movie.attributes.title }}</h2>
          <p>{{ movie.attributes.description }}</p>
        </div>
        <div class="movie-item-img">
            <img :src="getImgUrl(movie)" :alt="movie.attributes.title">
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup>
const props = defineProps({
  movies: Object 
});

const BASE_URL = 'https://review-site-txzr.onrender.com';

const getImgUrl = (movie) => {
  return `${BASE_URL}${movie.attributes.imgURL.data.attributes.formats.small.url}`;
};
</script>

<style scoped>
  
</style>

