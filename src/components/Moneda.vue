<template>
  <div class="col-xs-12 col-sm-6">
    <div class="component" :style="{backgroundColor: randomColor()}">
      <h3>{{ moneda.nombre }}</h3>
      <h5>Valor en {{ moneda.unidad_medida }}: {{moneda.valor}}</h5>
    </div>
  </div>
</template>
<script>
export default {
  props: ["moneda"],

  methods: {
    randomColor() {
      //function name
      var color = "#"; // hexadecimal starting symbol
      var letters = [
        "778899",
        "8470ff",
        "87cefa",
        "b0c4de",
        "20b2aa",
        "ffa07a",
        "ffb6c1",
        "d3d3d3"
      ]; //Set your colors here
      color += letters[Math.floor(Math.random() * letters.length)];
      return color;
    }
  }
};
</script>

<style scoped>
div.component {
  margin-top: 20px;
}
</style>

