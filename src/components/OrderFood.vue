<template>
  <div>
    <div class="container">
      <h1 class="display-3 mt-4"> {{ title }} </h1> 
      <div class="row">
        <div class="col-md-6">
          <input type="checkbox" id="Name" value="Name" v-model="checkedNames" @click="toggleMe">
          <label for="Name">Name</label>
        </div>
        <div class="col-md-6">
          <div v-if="showInput">
            <input type="text" placeholder="Add your order.." v-model="orderName">
            <button type="submit" @click="addOrder" :disabled="orderName.length === 0">Add order</button>
            <h2>Your order is:</h2>
            <div v-for="(o, index) in orders" :key="index">
              <li>{{ o.orderName }}  </li>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
    <!-- <input type="checkbox" id="john" value="John" v-model="checkedNames">
    <label for="john">John</label>
    <input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
    <label for="mike">Mike</label> 
    
    <p>Ljudi koji narucuju:</p>
    <span v-for="(name, i) in checkedNames" :key="i"> {{ name + ', ' }}</span> -->
</template>

<script>
export default {
  data() {
    return {
      title: "Order food",
      checkedNames: [],
      orderName: "",
      orders: [],
      showInput: false,
    }
  },
  methods: {
    addOrder() {
      this.orders.push({ orderName: this.orderName });
      this.orderName = "";
    },
    toggleMe() {
      this.showInput = !this.showInput;
    }
  }
};
</script>

<style>
</style>
