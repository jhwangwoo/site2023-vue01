<template>
  <ContTitle title="youtube" />
  <YoutubeSlider />
  <YoutubeSearch />
  <YoutubeTag />
  <YoutubeCont :youtubes="youtubes" />
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSlider from "@/components/youtube/YoutubeSlider.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";

import { ref } from "vue"; //useEffect같은개념

export default {
  components: {
    ContTitle,
    YoutubeSlider,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },
  setup() {
    //setup()으로 넣어야함
    const youtubes = ref([]);

    const Youtube = async () => {
      await fetch(
        "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=science&type=video&key=AIzaSyA574D8uxBhHYpAp6Xu760fh7tV3Fitgh8"
      )
        .then((response) => response.json())
        .then((result) => {
          console.log(result.items);
          youtubes.value = result.items;
        })
        .catch((error) => console.log("error", error));
    };
    Youtube();
    return {
      youtubes,
      Youtube,
    };
  },
};
</script>
