<template>
  <TheHeader title="List of movies" />
  <TheMovies />
</template>

<script>
import TheHeader from '@/components/layouts/TheHeader.vue';
import TheMovies from '@/components/movies/TheMovies.vue';
export default {
  components: {
    TheHeader,
    TheMovies,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Roboto', sans-serif;
}

body {
  margin: 0;
}
</style>
