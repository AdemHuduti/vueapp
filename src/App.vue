<template>
  <div>
    <div class="container mt-3">
      <button @click="selectedComponent = 'orderCmp'" class="btn btn-outline-dark">Order Food</button>
      <button @click="selectedComponent = 'apiCmp'" class="btn btn-outline-primary">API Data</button>
      <button @click="selectedComponent = 'skillsCmp'" class="btn btn-outline-danger">Skills</button>
      <keep-alive>
        <component :is="selectedComponent">
          
        </component>
      </keep-alive>
    </div>
  </div>
</template>

<script>
import OrderFood from "./components/OrderFood";
import APIData from "./components/APIData";
import Skills from "./components/Skills";

export default {
  data() {
    return {
      selectedComponent: "skillsCmp"
    };
  },
  components: {
    orderCmp: OrderFood,
    apiCmp: APIData,
    skillsCmp: Skills
  }
};
</script>

<style>
  .btn:focus {
    outline: none;
  }
</style>
