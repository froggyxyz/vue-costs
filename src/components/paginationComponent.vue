<template>
  <div v-if="costsNum > 5" class="pagination">
    <button
      v-for="num in Math.ceil(costsNum / 5)"
      :key="num"
      @click="changePage(num)"
    >
      {{ num }}
    </button>
  </div>
</template>

<script>
export default {
  props: ['costsNum'],
  methods: {
    changePage(num) {
      this.$emit('clickedPage', num);
    },
  },
};
</script>

<style scoped>
.pagination {
  max-width: 500px;
  display: flex;
  justify-content: space-between;
  padding: 10px 15px;
  outline: 1px solid rgb(196, 196, 196);
  box-shadow: 1px 1px 5px rgb(115, 115, 115);
  border-radius: 5px;
}
</style>
