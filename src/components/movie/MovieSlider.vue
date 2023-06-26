<template>
  <section class="movie__slider container">
    <swiper
      :effect="'coverflow'"
      :grabCursor="true"
      :centeredSlides="true"
      :slidesPerView="'2'"
      :autoplay="{
        delay: 3000,
        disableOnInteraction: false,
      }"
      :coverflowEffect="{
        rotate: 100,
        stretch: 0,
        depth: 100,
        modifier: 2,
        slideShadows: true,
      }"
      :pagination="true"
      :modules="modules"
      class="mySwiper"
    >
      <swiper-slide v-for="(movie, index) in movies" :key="index">
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
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { EffectCoverflow, Pagination, Autoplay } from "swiper";
import "swiper/scss";
import "swiper/scss/navigation";
import "swiper/scss/pagination";
import "swiper/css/effect-coverflow";
import "swiper/css/bundle";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [EffectCoverflow, Pagination, Autoplay],
    };
  },
  props: {
    movies: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.movie__slider {
  .swiper {
    width: 40%;
    padding-top: 50px;
    padding-bottom: 50px;
  }

  .swiper-slide {
    background-position: center;
    background-size: cover;
  }

  .swiper-slide img {
    display: block;
    width: 100%;
  }
}
</style>
