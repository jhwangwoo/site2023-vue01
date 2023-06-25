<template>
  <section class="unsplash__slider container">
    <Swiper
      :effect="'cube'"
      :grabCursor="true"
      :autoplay="{
        delay: 3000,
        disableOnInteraction: false,
      }"
      :cubeEffect="{
        shadow: true,
        slideShadows: true,
        shadowOffset: 20,
        shadowScale: 0.94,
      }"
      :modules="modules"
      class="mySwiper"
    >
      <SwiperSlide v-for="(unsplash, index) in unsplashs" :key="index">
        <a :href="`https://unsplash.com/photos/${unsplash.id}`" target="_blank">
          <img :src="unsplash.urls.regular" :alt="unsplash.alt_description" />
        </a>
      </SwiperSlide>
    </Swiper>
  </section>
</template>
<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { EffectCube, Pagination, Autoplay } from "swiper";

import "swiper/scss";
import "swiper/scss/navigation";
import "swiper/css/effect-cube";
import "swiper/css/pagination";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  props: {
    unsplashs: {
      type: Array,
      required: true,
    },
  },
  setup() {
    return {
      modules: [EffectCube, Pagination, Autoplay],
    };
  },
};
</script>
<style lang="scss">
.unsplash__slider {
  margin-top: 50px;
  .swiper {
    width: 400px;
    height: 350px;
    margin-bottom: 100px;
  }

  .swiper-slide {
    background-position: center;
    background-size: cover;
  }

  .swiper-slide img {
    display: block;
    width: 100%;
    height: 100%;
  }
}
</style>
