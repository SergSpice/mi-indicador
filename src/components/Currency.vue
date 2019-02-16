<template>
  <div class="component">
    <h1>Cambios de moneda</h1>
    <p>Esta App permite visualizar el valor actual (En tiempo real) de distintos tipos de cambio para monedas.</p>

    <div class="row">
      <app-moneda :key="moneda.valor" v-for="moneda in info.slice(3)" :moneda="moneda"></app-moneda>
    </div>
  </div>
</template>
<script>
import axios from "axios";
import Moneda from "./Moneda.vue";
export default {
  data() {
    return {
      info: []
    };
  },
  mounted() {
    axios
      .get("https://mindicador.cl/api")
      .then(resp => {
        let listaDeObjetos = Object.keys(resp.data).map(key => {
          return resp.data[key];
        });
        this.info = listaDeObjetos;
      })
  },
  components: {
    appMoneda: Moneda
  }
};
</script>
<style scoped>
div {
  background-color: lightblue;
}
</style>


