<template>
  <ContTitle title="movies" />
  <MovieSlider :movies="movies" />
  <MovieSearch @search="search" />
  <MovieTag @tags="tags" />
  <MovieCont :movies="movies" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import MovieSlider from "@/components/movie/MovieSlider.vue";
import MovieSearch from "@/components/movie/MovieSearch.vue";
import MovieTag from "@/components/movie/MovieTag.vue";
import MovieCont from "@/components/movie/MovieCont.vue";

// import { ref } from "vue"; //useEffect같은개념

export default {
  components: {
    ContTitle,
    MovieSlider,
    MovieSearch,
    MovieTag,
    MovieCont,
  },
  data() {
    return {
      movies: [],
    };
  },
  methods: {
    async tags(query) {
      try {
        const response = await fetch(
          `${query}?api_key=d318289536044275f4abc5923f180d7f`
        );
        const result = await response.json();
        this.movies = result.results;
      } catch (error) {
        console.log(error);
      }
    },
    async search(query) {
      try {
        const response = await fetch(
          `https://api.themoviedb.org/3/search/movie?api_key=d318289536044275f4abc5923f180d7f&query=${query}`
        );
        const result = await response.json();
        this.movies = result.results;
      } catch (error) {
        console.log("error", error);
      }
    },
    async fetchPopularMovies() {
      try {
        const response = await fetch(
          "https://api.themoviedb.org/3/movie/popular?api_key=d318289536044275f4abc5923f180d7f"
        );
        const result = await response.json();
        this.movies = result.results;
      } catch (error) {
        console.log("error", error);
      }
    },
  },
  created() {
    this.fetchPopularMovies();
  },
};
</script>
