<template>
    <div>
      <label for="drinkSelect">Escolha uma bebida:</label>
      <select
        id="drinkSelect"
        v-model="selectedDrink"
        @change="emitirItem"
      >
        <option value="" disabled>Selecione uma opção</option>
        <option v-for="(drink, key) in drinksInput" :key="key" :value="key">
          {{ drink }}
        </option>
      </select>
    </div>
  </template>
  
  <script>
  export default {
    name: "SelectDrink",
    data() {
      return {
        drinksInput: {
          Rum: "Rum",
          Gin: "Gin",
          Vodka: "Vodka",
          Whiskey: "Whiskey",
        },
        selectedDrink: "",
      };
    },
    methods: {
      emitirItem() {
        this.$emit("item", this.selectedDrink);
      },
    },
  };
  </script>
  