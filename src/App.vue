<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12">
        <app-currency></app-currency>
      </div>
    </div>
  </div>
</template>

<script>
import Currency from './components/Currency.vue'

export default {
  components: {
    appCurrency: Currency
  }
}
</script>

<style>
div.component {
        border: 1px solid black;
        padding: 30px;
    }
</style>
