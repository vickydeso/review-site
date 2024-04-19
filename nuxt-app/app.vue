<template>
  <div>
    <header class="container">
      <nav>
        <ul>
          <li><nuxt-link to="/">Home</nuxt-link></li>
          <li><nuxt-link to="/MoviesList">Movies</nuxt-link></li>
        </ul>
      </nav>
    </header>

    <main class="container">
      <Suspense>
          <MovieList v-if="data" :movies="data" />
          <h1 v-else>Null Data</h1>
      </Suspense>
    </main>

    <footer class="container">

    </footer>
  </div>
</template>

<script setup>
  const { data } = await useFetch('https://review-site-txzr.onrender.com/api/movies?populate=imgURL')
</script>
