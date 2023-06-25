<template>
  <div class="youtube__search container">
    <h2 class="blind">검색하기</h2>
    <input
      ref="inputRef"
      type="search"
      @keypress="onKeyPress"
      placeholder="이미지를 검색하세요!"
    />
    <button type="submit" @click="onClick">검색하기</button>
  </div>
</template>

<script>
export default {
  mounted() {
    this.$refs.inputRef.focus();
  },
  methods: {
    onKeyPress(event) {
      if (event.key === "Enter") {
        this.handleSearch();
      }
    },
    onClick() {
      this.handleSearch();
    },
    handleSearch() {
      const value = this.$refs.inputRef.value;
      this.$emit("onSearch", value);
    },
  },
};
</script>
