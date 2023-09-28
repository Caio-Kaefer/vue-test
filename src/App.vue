<template>
  <div>
    <HeaderComponent title="Teste Vue" />
    <SelectDrink @item="handleSelectedItem" />
    <p>Você selecionou: {{ selectedDrink }}</p>
    <DrinkList :ingredient="selectedDrink"/>
  </div>
</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import SelectDrink from './components/SelectDrink.vue';
import DrinkList from './components/DrinkList.vue';

export default {
  name: 'App',
  components: {
    HeaderComponent,
    SelectDrink,
    DrinkList, 
  },
  data() {
    return {
      selectedDrink: '' // Inicialize a variável aqui
    };
  },
  methods: {
    handleSelectedItem(selectedItem) {
      // Captura o valor emitido pelo componente filho e faz um console.log
      this.selectedDrink = selectedItem;
      console.log('Drink selecionado:', selectedItem);
    }
  }
};
</script>
