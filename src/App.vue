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
import MovieCard from '@/components/MovieCard.vue';
export default {
  components: {
    MovieCard,
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

