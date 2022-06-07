<template>
  <div class="costs__display">
    <div
      class="costs__item"
      v-for="cost in costs.slice(pageNum * 5 - 5, pageNum * 5)"
      :key="cost.id"
    >
      <div>{{ cost.id }}</div>
      <div>{{ cost.date }}</div>
      <div>{{ cost.category }}</div>
      <div>{{ cost.amount }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['costs', 'pageNum'],
};
</script>

<style lang="scss" scoped>
.costs__display {
  margin-top: 30px;
  max-width: 500px;
}
.costs__item {
  margin-bottom: 10px;
  padding: 10px 15px;
  display: flex;
  justify-content: space-between;
  text-align: center;
  outline: 1px solid rgb(196, 196, 196);
  box-shadow: 1px 1px 5px rgb(115, 115, 115);
  border-radius: 5px;
}
</style>
