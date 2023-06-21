<template>
  <main>
    <SliderSection attr="slider__wrap section" />
    <IntroSection attr="intro__wrap section bg-blue jamsil" />
    <PortSection attr="port__wrap section center jamsil" />
    <YoutubeSection attr="youtube__wrap section bg-blue" />
    <UnsplashSection attr="unsplash__wrap section jamsil" />
    <MovieSection attr="movie__wrap section jamsil" />
  </main>
</template>

<script>
// @ is an alias to /src
import SliderSection from "@/components/section/SliderSection.vue";
import IntroSection from "@/components/section/IntroSection.vue";
import PortSection from "@/components/section/PortSection.vue";
import YoutubeSection from "@/components/section/YoutubeSection.vue";
import UnsplashSection from "@/components/section/UnsplashSection.vue";
import MovieSection from "@/components/section/MovieSection.vue";

export default {
  components: {
    SliderSection,
    IntroSection,
    PortSection,
    YoutubeSection,
    UnsplashSection,
    MovieSection,
  },
};
</script>
