<script setup>

const BASE_URL = 'https://review-site-txzr.onrender.com'

defineProps({
  movies: Object
})
</script>

<template>
  <div class="movie-list">
    <ul>
      <li :key="movie.id" v-for="movie in movies.data" class="movie-item">
        <div class="movie-item-info">
          <h2>{{ movie.attributes.title }}</h2>
          <p>{{ movie.attributes.description }}</p>
        </div>
        <div class="movie-item-img">
            <img :src="BASE_URL + movie.attributes.imgURL.data.attributes.formats.small.url" :alt="movie.attributes.title">
        </div>
      </li>
    </ul>
  </div>
</template>

<style scoped>

</style>