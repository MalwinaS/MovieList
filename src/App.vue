<template>
  <TheHeader title="List of movies" />
  <MovieList :movies="movies" />
</template>

<script>
import TheHeader from '@/components/layouts/TheHeader.vue';
import MovieList from '@/components/movies/MovieList.vue';
export default {
  components: {
    TheHeader,
    MovieList,
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
    };
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
