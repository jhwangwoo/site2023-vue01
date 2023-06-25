<template>
  <div class="youtube__tag jamsil container">
    <div>
      <button
        v-for="(tag, index) in youtubeTags"
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
      youtubeTags: [
        { name: "물리학" },
        { name: "화학" },
        { name: "생물학" },
        { name: "천문학" },
      ],
    };
  },
  methods: {
    btnClick(tagName) {
      this.$emit("onSearch", tagName);
    },
  },
};
</script>

<style lang="scss">
.youtube__tag {
  div {
    display: flex;
    justify-content: center;
    margin-top: 100;
    margin-bottom: 50px;
    button {
      border: 1px solid #f7100d;
      padding: 10px 20px;
      margin: 0 10px;
      color: #f7100d;
      background-color: #fff;
      transition: all 0.3s;
      &:hover {
        background-color: #f7100d;
        color: #fff;
      }
    }
  }
}
</style>
