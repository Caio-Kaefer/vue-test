<template>
    <div class="list">
      <div v-for="item in apiData" :key="item.id">
        <CardComponent :Drink="item" />
      </div>
    </div>
  </template>
  
  <script>
  import CardComponent from "./CardComponent.vue";
  import axios from "axios";
  
  export default {
    name: "CardListComponent",
    props: {
      ingredient: String
    },
    data() {
      return {
        apiData: []
      };
    },
    components: {
      CardComponent
    },
    mounted() {
      this.fetchData();
    },
    watch: {
      ingredient: "fetchData" 
    },
    methods: {
      fetchData() {
        axios
          .get(`https://www.thecocktaildb.com/api/json/v1/1/filter.php?i=${this.ingredient}`)
          .then((response) => {
            this.apiData = response.data.drinks;
          })
          .catch((error) => {
            console.error("Erro ao buscar dados da API:", error);
          });
      }
    }
  };
  </script>
  
  <style scoped>
  .list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 20px;
    width: 1000px;
  }
  </style>
  