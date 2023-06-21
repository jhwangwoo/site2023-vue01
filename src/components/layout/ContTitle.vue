<template>
  <div class="cont__Title">
    <h2>{{ title }}</h2>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>
.cont__Title {
  h2 {
    text-align: center;
    font-size: 5vw;
    text-transform: uppercase;
    font-weight: bold;
    padding: 5%;
  }
}
</style>
