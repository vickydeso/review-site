<script setup>
  import { ref, computed } from 'vue';

  let data = [];
  let error = null;

  const fetchData = async () => {
    const response = await useFetch('https://review-site-txzr.onrender.com/api/movies?populate=imgURL');
    if (response instanceof Error) {
      error = response;
      console.error('Error fetching data:', error);
    } else {
      data = response.data;
    }
  };

  fetchData(); // Call the fetchData function to initiate data fetching

  console.log('Data:', data); // Log data to inspect its structure

  const searchQuery = ref('');

  const filteredMovies = computed(() => {
    return data ? data.filter(movie => {
      return movie.attributes.title.toLowerCase().includes(searchQuery.value.toLowerCase());
    }) : [];
  });
</script>



Home.vue