<template>
  <div id="app">
    <add-payment-form v-if="isShowForm" @addNewPayment="addNewPayment" />
    <costs-button
      @clicked="clicked"
      :text="isShowForm ? 'CLOSE FORM' : 'OPEN FORM'"
    />
    <costs-display :pageNum="pageNum" :costs="paymentsList" />
    <pagination-component
      @clickedPage="clickedPage"
      :costsNum="paymentsList.length"
    />
  </div>
</template>

<script>
import addPaymentForm from './components/addPaymentForm.vue';
import costsButton from './components/costsButton.vue';
import costsDisplay from './components/costsDisplay.vue';
import PaginationComponent from './components/paginationComponent.vue';
export default {
  components: {
    costsDisplay,
    addPaymentForm,
    costsButton,
    PaginationComponent,
  },
  data() {
    return {
      paymentsList: [],
      isShowForm: false,
      pageNum: 1,
    };
  },
  methods: {
    fetchData() {
      return [
        {
          id: 1,
          date: '28.03.2020',
          category: 'Food',
          amount: 169,
        },
        {
          id: 2,
          date: '24.03.2020',
          category: 'Transport',
          amount: 360,
        },
        {
          id: 3,
          date: '24.03.2020',
          category: 'Food',
          amount: 532,
        },
      ];
    },
    addNewPayment(data) {
      this.paymentsList = [...this.paymentsList, data];
    },
    clicked() {
      this.isShowForm = !this.isShowForm;
    },
    clickedPage(num) {
      this.pageNum = num;
    },
  },
  created() {
    this.paymentsList = this.fetchData();
    this.isShowForm = false;
  },
};
</script>

<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
// }

// nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
