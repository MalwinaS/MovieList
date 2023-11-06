<template>
  <ul>
    <MovieCard
      v-for="movie in movies"
      :key="movie.id"
      :title="movie.title"
      :description="movie.description"
      :link="movie.link"
    />
  </ul>
</template>

<script>
import MovieCard from '@/components/movies/MovieCard.vue';
export default {
  components: {
    MovieCard,
  },
  inject: ["movies"],
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
