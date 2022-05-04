<template>
  <div class="wrapper">
    <header>
      <div class="tittle">My personal costs</div>
    </header>
  
    <main>
      <AddPaymentForm @addNewPayment="addNewPayment" />
      <PaymentsDisplay :items="paymentsList" />
    </main>
  </div>
</template>

<script>
import PaymentsDisplay from './components/PaymentsDisplay'
import AddPaymentForm from './components/AddPaymentForm'

export default {

  components: {
    PaymentsDisplay,
    AddPaymentForm,
  },

  data() {
    return {
      paymentsList: [],
    }
  },

  methods: {
    fetchData() {
      return [
        {
          date: '28.03.2020',
          category: 'Food',
          value: 169,
          },
          {
          date: '24.03.2020',
          category: 'Transport',
          value: 360,
          },
          {
          date: '24.03.2020',
          category: 'Food',
          value: 532,
          },
      ]
    },

  addNewPayment (data) {
    this.paymentsList.push(data);
  },

},

  created() {
    this.paymentsList = this.fetchData()
  },
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
