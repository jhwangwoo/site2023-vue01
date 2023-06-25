<template>
  <div class="unsplash__tag jamsil container">
    <div>
      <button
        v-for="(tag, index) in unsplashTag"
        :key="index"
        @click="btnClick(tag.name)"
      >
        {{ tag.name }}
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      unsplashTag: [
        { name: "Physics" },
        { name: "Chemistry" },
        { name: "Biology" },
        { name: "Astronomy" },
      ],
    };
  },
  methods: {
    btnClick(tagName) {
      this.$emit("tags", tagName);
    },
  },
};
</script>

<style lang="scss">
.unsplash__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100;
    margin-bottom: 50px;
    button {
      border: 1px solid #35a4e4;
      padding: 10px 20px;
      margin: 0 10px;
      color: #35a4e4;
      background-color: #fff;
      transition: all 0.3s;
      &:hover {
        background-color: #35a4e4;
        color: #fff;
      }
    }
  }
}
</style>
