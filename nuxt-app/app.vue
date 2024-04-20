<template>
  <div>
    <header class="container">
      <nav>
        <ul>
          <li><NuxtLink to="/">Home</NuxtLink></li>
          <li><NuxtLink to="/movielist">Movies</NuxtLink></li>
        </ul>
      </nav>
    </header>

      <NuxtPage class="container">

      </NuxtPage>

    <footer class="container">

    </footer>
  </div>
</template>

<script setup>


</script>

<style scoped>
  header{
    background-color: rgb(218, 218, 218);
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
  }
  header nav li{
    margin-left: 2rem;
  }

</style>