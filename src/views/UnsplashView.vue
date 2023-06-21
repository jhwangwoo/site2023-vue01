<template>
  <ContTitle title="unsplash" />
  <UnsplashSlider />
  <UnsplashSearch :onSearch="setImages" />
  <UnsplashTag />
  <UnsplashCont :unsplashs="unsplashs" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import UnsplashSlider from "@/components/unsplash/UnsplashSlider.vue";
import UnsplashSearch from "@/components/unsplash/UnsplashSearch.vue";
import UnsplashTag from "@/components/unsplash/UnsplashTag.vue";
import UnsplashCont from "@/components/unsplash/UnsplashCont.vue";

import { ref } from "vue"; //useEffect같은개념

export default {
  components: {
    ContTitle,
    UnsplashSlider,
    UnsplashSearch,
    UnsplashTag,
    UnsplashCont,
  },
  setup() {
    //setup()으로 넣어야함
    const unsplashs = ref([]);
    // const search = async (query) => {
    //   await fetch(
    //     //async await비동기 처리
    //     `https://api.unsplash.com/search/photos?client_id=q_Cs549hvK1mONfcPtht4An0-5wms_SlpsGWUO0nCtA&per_page=30&query=${query}`
    //   )
    //     .then((response) => response.json())
    //     .then((result) => setImages(result.results))
    //     .catch((error) => console.log("error", error));
    // };

    const Unsplash = async () => {
      await fetch(
        "https://api.unsplash.com/photos?client_id=q_Cs549hvK1mONfcPtht4An0-5wms_SlpsGWUO0nCtA&per_page=30"
      )
        .then((response) => response.json())
        .then((result) => {
          // setImages(result);
          unsplashs.value = result;
        })
        .catch((error) => console.log("error", error));
    };
    Unsplash();
    return {
      unsplashs,
      Unsplash,
      // search,
    };
  },
};
</script>
