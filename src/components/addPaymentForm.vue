<template>
  <div class="costs__form">
    <input placeholder="Amount" v-model="amount" />
    <input placeholder="Category" v-model="category" />
    <input placeholder="Date" v-model="date" />
    <button @click="onSaveClick">ADD</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      id: 4,
      amount: '',
      category: '',
      date: '',
    };
  },
  computed: {
    getCurrentDate() {
      const today = new Date();
      const d = today.getDate();
      const m = today.getMonth() + 1;
      const y = today.getFullYear();
      return `${d}.${m}.${y}`;
    },
  },
  methods: {
    onSaveClick() {
      const data = {
        id: this.id,
        date: this.date || this.getCurrentDate,
        category: this.category,
        amount: +this.amount,
      };
      this.id++;
      this.$emit('addNewPayment', data);
    },
  },
};
</script>

<style lang="scss" scoped>
.costs__form {
  margin-bottom: 10px;
  padding: 10px 15px;
  display: flex;
  flex-wrap: wrap;
  max-width: 500px;
  outline: 1px solid rgb(196, 196, 196);
  box-shadow: 1px 1px 5px rgb(115, 115, 115);
  border-radius: 5px;
  & > input {
    padding: 5px 10px;
    margin-bottom: 10px;
    width: 100%;
  }
}
</style>
