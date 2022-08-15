<template>
  <div>
    <input type="text" v-model.lazy="firstName" placeholder="First Name">
    <input type="text" v-model.lazy="lastName" placeholder="Last Name">
    <h2>Full Name: {{ fullName }}</h2>
  </div>
  <div>
    <h2>Total: {{ total }}</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      items:[
        {
          id: 1,
          title: 'IV',
          price: 100
        },
        {
          id: 2,
          title: 'Phone',
          price: 300
        },
        {
          id: 3,
          title: 'Laptop',
          price: 300
        }
      ]
    }
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`
    },
    total() {
      return this.items.reduce((total, curr) => (total = total + curr.price), 0)
    }
  }
}
</script>

<style scoped>
</style>
