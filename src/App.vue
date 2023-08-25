<template>
  <div id="app">
   <h1 class="title-name">Conversor de Moedas</h1>
    <div class="rows">

      <Conversor nome_moeda1="Euro" nome_moeda2="Real " valor_moeda1="1" valor_moeda2="5.25"/>
      
      <Conversor nome_moeda1="Dolar" nome_moeda2="Real" valor_moeda1="1" valor_moeda2="4.86"/>

      <Conversor nome_moeda1="Euro" nome_moeda2="Dolar" valor_moeda1="1" valor_moeda2="1.08"/>
    
    </div>
    <div class="rows">
          <Conversor nome_moeda1="Real" nome_moeda2="Euro" valor_moeda1="1" valor_moeda2="0.19"/>

          <Conversor nome_moeda1="Real" nome_moeda2="Dolar" valor_moeda1="1" valor_moeda2="0.21"/>

          <Conversor nome_moeda1="Dolar" nome_moeda2="Euro" valor_moeda1="1" valor_moeda2="0.93"/>    
    </div>
    <Footer />
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Conversor from './components/Conversor.vue'
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Conversor,
    Footer
  }
}
</script>

<style>
@font-face {
    font-family: 'Saira Condensed';
    src: url('assets/fonts/SairaCondensed-Regular.ttf') format('truetype');
}

body{
    font-family: 'Saira Condensed', sans-serif;
    margin: 0;
    padding: 0;
}

 h1 {
  display: flex;
  justify-content: center;
  text-align: center;
  background: linear-gradient(to top right,#ff2a00 0,#ffb600 100%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.title-name{
  display: flex;
  justify-content: center;
  text-align: center;
  background: linear-gradient(to top right,#ff2a00 0,#ffb600 100%);
  background-clip: text;
  -webkit-text-fill-color: transparent;
  font-size: 6em;
  margin-left: 45px;
}

.rows {
  max-width: 1000px;
  margin: 0 auto;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
  display: flex;
  flex-wrap: wrap;
}
::-webkit-scrollbar{
  width: 15px ;
 
} 
::-webkit-scrollbar-thumb {
 background: linear-gradient(to top right,#ff2a00 0,#ffb600 100%);
 border-radius: 10px
} 
::-webkit-scrollbar-track {
  background: #f1f1f1; 
}

@media (max-width: 768px) {
  .title-name {
    font-size: 4em;
    margin-left: 0;
  }
  
  .rows {
    margin: 20px;
  }
  body {
    padding: 50px;
  }
}


</style>
