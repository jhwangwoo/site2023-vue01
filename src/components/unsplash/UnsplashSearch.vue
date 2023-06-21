<template>
  <div className="unsplash__search container">
    <h2 className="blind">검색하기</h2>
    <input
      ref="inputRef"
      type="search"
      @keypress="onKeyPress"
      placeholder="이미지를 검색하세요!"
    />
    <button type="submit" onClick="{onClick}">검색하기</button>
  </div>
</template>
<script>
export default {
  props: {
    setImages: {
      type: Array,
      required: true,
    },
  },
  methods: {
    handleSearch() {
      const value = this.$refs.inputRef.value;
      this.onSearch(value);
    },
    onKeyPress(event) {
      if (event.key === "Enter") {
        this.handleSearch();
      }
    },
    onClick() {
      this.handleSearch();
    },
  },
};
</script>
