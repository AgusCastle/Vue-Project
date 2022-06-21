<template>
 <Menu />
 <Car />
</template>

<script>
import Car from "./components/Car"
import Menu from "./components/Menu"
export default {
  components: {
    Car,
    Menu,
  },

  setup() {
    let agencia = "Iztacalco";

    return{
      agencia,
    };
  },
}
</script>

<style>

</style>