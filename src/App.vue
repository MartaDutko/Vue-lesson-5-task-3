<template>
<product-card-list :card-dataList="notebooksList"/>
</template>

<script>
import ProductCardList from "./components/ProductCardList.vue";
import { notebooksList } from "./constants/3_data_notebooks";
export default {
  name: 'App',

components: {
  ProductCardList,
},

data() {
  return {
    notebooksList
  }
},
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
