<template>
  <div class="card">
    <div class="card__content">
        <div class="Title">{{ Drink.strDrink }}</div>
        <img class="image" :src="Drink.strDrinkThumb" alt="Imagem do Drink" />
    </div>
  </div>
</template>
<script>
export default{
    name:'CardComponent',
    props:{
        Drink:Object
    }
}
</script>
<style scoped>
.card {
  width: 190px;
  height: 254px;
  border-radius: 20px;
  padding: 5px;
  box-shadow: rgba(151, 65, 252, 0.2) 0 15px 30px -5px;
  color: aliceblue;
  margin: 10px;
}

.card:hover{
  transform: scale(1.1);
}
.card__content {
  background: rgb(5, 6, 45);
  border-radius: 17px;
  width: 100%;
  height: 100%;
  padding: 20px;
}

.image{
  width:100%;
  border-radius: 20px;
}
</style>