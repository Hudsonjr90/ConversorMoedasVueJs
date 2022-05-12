<template>
  <div id="app">  
    <h1>Conversor de moedas</h1>
    <div class="linha">
      <conversor moeda-a="USD" moedaB="BRL"></conversor>
      <conversor moeda-a="BRL" moedaB="USD"></conversor>
    </div>

    <div class="linha">
      <conversor moeda-a="CAD" moedaB="BRL"></conversor>
      <conversor moeda-a="BRL" moedaB="CAD"></conversor>
    </div>
    
    <div class="linha">
      <conversor moeda-a="EUR" moedaB="BRL"></conversor>
      <conversor moeda-a="BRL" moedaB="EUR"></conversor>
    </div>
  </div>
</template>

<script>
import Conversor from './components/Conversor.vue';
export default {
  name: 'App',
  components: {
    Conversor
  }
}
</script>

<style>
#app {
  margin: auto;
  max-width: 900px;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.linha {
  margin-top: 40px;
  display: flex;
  justify-content: space-around;
}
</style>