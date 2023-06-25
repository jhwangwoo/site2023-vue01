<template>
  <div>
    <ContTitle title="unsplash" />
    <UnsplashSlider :unsplashs="unsplashs" />
    <UnsplashSearch @search="search" />
    <UnsplashTag @tags="tags" />
    <UnsplashCont :unsplashs="unsplashs" />
  </div>
</template>
<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },
  data() {
    return {
      unsplashs: [],
    };
  },
  methods: {
    async tags(query) {
      try {
        const response = await fetch(
          `https://api.unsplash.com/search/photos?client_id=q_Cs549hvK1mONfcPtht4An0-5wms_SlpsGWUO0nCtA&per_page=30&query=${query}`
        );
        const result = await response.json();
        this.unsplashs = result.results;
      } catch (error) {
        console.log(error);
      }
    },
    async search(query) {
      try {
        const response = await fetch(
          `https://api.unsplash.com/search/photos?client_id=q_Cs549hvK1mONfcPtht4An0-5wms_SlpsGWUO0nCtA&per_page=30&query=${query}`
        );
        const result = await response.json();
        this.unsplashs = result.results;
      } catch (error) {
        console.log("error", error);
      }
    },
    async fetchUnsplash() {
      try {
        const response = await fetch(
          "https://api.unsplash.com/photos?client_id=q_Cs549hvK1mONfcPtht4An0-5wms_SlpsGWUO0nCtA&per_page=30"
        );
        const result = await response.json();
        this.unsplashs = result;
      } catch (error) {
        console.log("error", error);
      }
    },
  },
  created() {
    this.fetchUnsplash();
  },
};
</script>
