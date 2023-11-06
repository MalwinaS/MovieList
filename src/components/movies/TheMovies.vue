<template>
  <base-card>
    <base-button
      @click="currentComponent = 'movie-list'"
      :mode="listMovieButton"
      >List of movie</base-button
    >
    <base-button @click="currentComponent = 'new-movie'" :mode="newMovieButton"
      >Add new movie</base-button
    >
  </base-card>
  <keep-alive>
  <component :is="currentComponent"></component>
</keep-alive>
</template>

<script>
import MovieList from '@/components/movies/MovieList.vue';
import NewMovie from '@/components/movies/NewMovie.vue';

export default {
  components: {
    MovieList,
    NewMovie,
  },
  data() {
    return {
      movies: [
        {
          id: '1',
          title: 'Rzeź',
          description:
            'Dwie nowojorskie pary spotykają się, by porozmawiać o bójce, do jakiej doszło między ich synami. Na pozór niewinne spotkanie zamieni się w lawinę potyczek i wzajemnych złośliwości.',
          link: 'https://www.filmweb.pl/film/Rze%C5%BA-2011-599742',
        },
        {
          id: '2',
          title: 'Mężczyzna imieniem Otto',
          description:
            'Po śmierci ukochanej żony, zgorzkniały Otto postanawia popełnić samobójstwo. Wszelkie próby są niweczone przez jego nowych sąsiadów.',
          link: 'https://www.filmweb.pl/film/Rze%C5%BA-2011-599742',
        },
      ],
      currentComponent: 'movie-list',
    };
  },
  computed: {
    listMovieButton() {
      return this.currentComponent === 'movie-list' ? null : 'flat';
    },
    newMovieButton() {
      return this.currentComponent === 'new-movie' ? null : 'flat';
    },
  },
  methods: {
    addMovie(title, description, link) {
      const newMovie = {
        id: new Date().toISOString(),
        title: title,
        description: description,
        link: link
      };
      this.movies.unshift(newMovie)
      this.currentComponent = 'movie-list'
    }
  },
  provide() {
    return {
      movies: this.movies,
      addMovie: this.addMovie
    };
  },
};
</script>
