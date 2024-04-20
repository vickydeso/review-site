<template>
  <div class="movie-list">

    <ul>
      <li v-for="movie in data.data" :key="movie.id" class="movie-item">
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
  const { data } = await useFetch('https://jolly-beauty-11c6c7b123.strapiapp.com/api/movies?populate=imgURL')

  const BASE_URL = 'https://jolly-beauty-11c6c7b123.strapiapp.com/';

  const getImgUrl = (movie) => {
    return movie.attributes.imgURL.data.attributes.formats.small.url;
  };


</script>

<style scoped>
    .movie-temp {
    margin: 20px;
    padding: 20px;
    border: 1px solid #ccc;
    border-radius: 5px;
    max-width: 500px;
  }
  h2{
    margin-bottom: 2rem;
    text-align: center;
  }

  ul{
    list-style: none;
  }
</style>