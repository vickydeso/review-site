<template>
  <div class="movie-list">

    <div class="movie-temp">
      <h2>The Godfather</h2>

      <p>Directed by Francis Ford Coppola, this crime film follows the powerful Italian-American crime family of Don Vito Corleone as they transfer control of their clandestine empire to his reluctant son, Michael. It's known for its deep portrayal of Mafia life and the complex dynamics within the Corleone family.</p>
    </div>

    <ul>
      <li v-for="movie in movies" :key="movie.id" class="movie-item">
        <div class="movie-item-info">
          <!-- <h2>{{ movie.attributes.title }}</h2>
          <p>{{ movie.attributes.description }}</p> -->

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
</style>


