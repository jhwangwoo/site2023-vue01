<template>
  <ContTitle title="movies" />
  <MovieSlider />
  <MovieSearch />
  <MovieTag />
  <MovieCont :movies="movies" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import MovieSlider from "@/components/movie/MovieSlider.vue";
import MovieSearch from "@/components/movie/MovieSearch.vue";
import MovieTag from "@/components/movie/MovieTag.vue";
import MovieCont from "@/components/movie/MovieCont.vue";

import { ref } from "vue"; //useEffect같은개념

export default {
  components: {
    ContTitle,
    MovieSlider,
    MovieSearch,
    MovieTag,
    MovieCont,
  },

  setup() {
    //setup()으로 넣어야함
    const movies = ref([]);
    const searchs = ref([]);
    const search = ref([]);

    const TopMovies = async () => {
      await fetch(
        `https://api.themoviedb.org/3/movie/popular?api_key=d318289536044275f4abc5923f180d7f&query=${search.value}`
      )
        .then((response) => response.json())
        .then((result) => {
          movies.value = result.results;
          searchs.value = result.results;
        })
        .catch((error) => console.log("error", error));
    };
    TopMovies();
    return {
      movies,
      searchs,
      TopMovies,
    };
  },
};
</script>
