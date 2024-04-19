<template>
  <div>
    <header>
      <nav>
        <ul>
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/movielist">Movies</NuxtLink></li>
        </ul>
      </nav>
    </header>

      <NuxtPage>
        <main class="container">
          <!-- <MovieList v-if="data" :movies="data" />
          <h1 v-else>Null Data</h1> -->
        </main>
      </NuxtPage>

    <footer class="container">

    </footer>
  </div>
</template>

<script setup>
  const { data } = await useFetch('https://review-site-txzr.onrender.com/api/movies?populate=imgURL')

</script>

<style scoped>
  header{
    background-color: rgb(218, 218, 218);
    /* box shadow below */
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
  }
  header nav li{
    margin-left: 2rem;
  }

</style>