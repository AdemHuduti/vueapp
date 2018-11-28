<template>
  <div>
    <h1 class="display-4 mt-4"> {{ title }} </h1>
    <div>
      <ul v-for="arr in arryz" :key="arr.companyId" class="list-group">
        <li class="list-group-item"> 
          {{ arr.name }}
          <span class="float-right"> {{ arr.email }} </span>
        </li>
      </ul>
    </div>
  </div>  
</template>

<script>
export default {
  data() {
    return {
      title: 'API Data',
      arryz: []
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/users')
      .then(data => data.json())
      .then(res => (this.arryz = res))
  }
}
</script>

<style scoped>
  
</style>
