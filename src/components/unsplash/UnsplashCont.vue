<template>
  <div class="unsplash__cont container mb50">
    <ul>
      <li v-for="(unsplash, index) in unsplashs" :key="index">
        <a :href="`https://unsplash.com/photos/${unsplash.id}`" target="_blank">
          <img :src="unsplash.urls.regular" :alt="unsplash.alt_description" />
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: {
    unsplashs: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style lang="scss">
.unsplash__cont {
  ul {
    display: block;
    column-count: 4;
    li {
      margin-bottom: 20px;
    }
  }
}
</style>
