<template>
  <button @click="changeDisplay" class="btn">{{ text }}</button>
</template>

<script>
export default {
  props: ['text'],
  methods: {
    changeDisplay() {
      this.$emit('clicked');
    },
  },
};
</script>

<style lang="scss" scoped>
// .btn {
//   padding: 5px 15px;
//   background: rgb(0, 185, 169);
//   outline: 1px solid rgb(0, 52, 54);
//   border: none;
//   border-radius: 5px;
//   cursor: pointer;
// }
//
</style>
