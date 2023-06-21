<template>
  <div class="movie__cont container mb50">
    <ul>
      <li v-for="(movie, index) in movies" v-bind:key="index">
        <a
          :href="`https://www.themoviedb.org/movie/${movie.id}`"
          target="_blank"
        >
          <img
            :src="`https://image.tmdb.org/t/p/w500/${movie.poster_path}`"
            :alt="movie.title"
          />
          <em>
            <span class="title">{{ movie.title }}</span>
            <span class="star">{{ movie.vote_average }}</span>
          </em>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
@import url(../../assets/scss/setting/mixins.scss);
.movie__cont {
  ul {
    columns: 4;
    column-gap: 20px;
    li {
      margin-bottom: 4%;
      position: relative;
      overflow: hidden;
      white-space: nowrap;
      text-overflow: ellipsis;
      -webkit-line-clamp: 1; /* 라인수 */
      -webkit-box-orient: vertical;
      word-wrap: break-word;
      .title {
        font-size: 20px;
      }
      .star {
        position: absolute;
        right: 20px;
        top: 20px;
        width: 30px;
        height: 30px;
        background-color: #fff;
        font-size: 12px;
        text-align: center;
        line-height: 30px;
        border-radius: 50%;
        color: #000;
      }
      img {
        width: 100%;
        transition: all 0.3s;
        border-radius: 5px;
        &:hover {
          transform: scale(110%);
          cursor: pointer;
        }
      }
    }
  }
}
</style>
