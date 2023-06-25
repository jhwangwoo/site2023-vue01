<template>
  <div>
    <ContTitle title="youtube" />
    <YoutubeSearch @onSearch="search" />
    <YoutubeTag @onSearch="search" />
    <YoutubeCont :youtubes="youtubes" />
  </div>
</template>

<script>
import ContTitle from "@/components/layout/ContTitle.vue";
import YoutubeSearch from "@/components/youtube/YoutubeSearch.vue";
import YoutubeTag from "@/components/youtube/YoutubeTag.vue";
import YoutubeCont from "@/components/youtube/YoutubeCont.vue";

export default {
  components: {
    ContTitle,
    YoutubeSearch,
    YoutubeTag,
    YoutubeCont,
  },
  data() {
    return {
      youtubes: [],
    };
  },
  methods: {
    async search(query) {
      try {
        const response = await fetch(
          `https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=${query}&type=video&key=AIzaSyA574D8uxBhHYpAp6Xu760fh7tV3Fitgh8`
        );
        const result = await response.json();
        this.youtubes = result.items;
      } catch (error) {
        console.log("error", error);
      }
    },
    async fetchYoutubes() {
      try {
        const response = await fetch(
          "https://youtube.googleapis.com/youtube/v3/search?part=snippet&maxResults=30&q=science&type=video&key=AIzaSyA574D8uxBhHYpAp6Xu760fh7tV3Fitgh8"
        );
        const result = await response.json();
        this.youtubes = result.items;
      } catch (error) {
        console.log(error);
      }
    },
  },
  mounted() {
    this.fetchYoutubes();
  },
};
</script>
