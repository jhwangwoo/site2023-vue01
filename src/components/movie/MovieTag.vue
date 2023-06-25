<template>
  <div class="movie__tag jamsil container">
    <div>
      <button
        v-for="(tag, index) in movieTag"
        :key="index"
        @click="btnClick(tag.name)"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      movieTag: [
        {
          name: "높은 평점",
          url: "https://api.themoviedb.org/3/movie/top_rated",
        },
        {
          name: "인기 영화",
          url: "https://api.themoviedb.org/3/movie/popular",
        },
        {
          name: "상영중인 영화",
          url: "https://api.themoviedb.org/3/movie/now_playing",
        },
        {
          name: "상영예정작",
          url: "https://api.themoviedb.org/3/movie/upcoming",
        },
      ],
    };
  },
  methods: {
    btnClick(tagName) {
      const clickedTag = this.movieTag.find((tag) => tag.name === tagName);
      if (clickedTag) {
        this.$emit("tags", clickedTag.url);
      }
    },
  },
};
</script>

<style lang="scss">
.movie__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100;
    margin-bottom: 50px;
    button {
      border: 1px solid #0d2c04;
      padding: 10px 20px;
      margin: 0 10px;
      color: #0d2c04;
      background-color: #fff;
      transition: all 0.3s;
      &:hover {
        background-color: #0d2c04;
        color: #fff;
      }
    }
  }
}
</style>
