<template>
  <h2>Soy un componente</h2>
  <p>Marca: {{brand}}</p>
  <p>Modelo: {{model}}</p>
  <p>Precio: ${{price}}</p>
  <p>Agencia: {{agencia}}</p>
  <button @click="upPrice">Aumentar precio</button>
  <button @click="downPrice">Disminuir precio </button>
  <p>Colores: 
    <!-- <span v-for="(color, index) in colors" v-bind:key="index">
        {{ index }} . {{ color }} -
    </span> -->
  </p>
  <p>Potencia menor a 50:</p>
  <ul>
    <template v-for="(power, index) in powers" v-bind:key="index">
        <li v-if="power < 50">{{power}}</li>
    </template>
  </ul>

</template>

<script>

import { ref } from "vue";

export default {
    props:{
        agencia:{
            type: String,
            default: "Sin agencias", 
        } ,
    },
    setup(){
        const brand = "Audi";
        const model = "A4";
        const colors = ["Rojo", "Azul", "Gris"];
        let price = ref(500000)
        const powers = [10 ,20 ,40 ,50 ,60 ,100 ,120]

        const upPrice = () => {
            price.value++;
        };

        const downPrice = () => {
            price.value--;
        };

        return {
            brand,
            model,
            colors,
            price,
            powers,
            upPrice,
            downPrice
        };
    }
};
</script>

<style>

</style>