<template>
  <div class="conversor">
        <div class="col-sm-12 ">
            <div class="card ">
                <div class="card-header">
                    {{nome_moeda1}} / {{nome_moeda2}}
                </div>
                <div class="card-body">
                    <label for="">{{nome_moeda1}}:</label>
                    <input v-model="value"  type="number" class="form-control">
                    <label for="">{{nome_moeda2}}:</label>
                    <input disabled v-bind:value="valor_moeda2"   type="number" class="form-control">
                    <h1 class="text-center">{{multipliedValue}}</h1>
                </div>
            </div>
        </div>
  </div>
</template>

<script>
export default {
  name: 'Conversor',
  props: {
    nome_moeda1:String,
    nome_moeda2:String,
    valor_moeda2:Number
    
  },
  data:function(){
      return{
          value:1,
        //   valor_moeda2,
      }
  },
  computed:{
        multipliedValue () {
        return (this.value * this.valor_moeda2);
   }
  },
  methods:{
    //   converte(valor_moeda1 , valor_moeda2){
    //     //   const convertido = (parseFloat(valor_moeda) * parseFloat(valor_moeda2));
    //     //   this.valor_moeda.push(convertido);
          
    //   },
  }
}
</script>

<style scoped>
.conversor{
    max-width: 300px;
    padding: 20px;
    box-shadow: 0px 4px 8px 0px rgba(0,0,0,0.2);
    margin-left: 40px;
    display: flex;
    justify-content: center;
}

.conversor .title {
    color: #313131;
}

.conversor .valor {
    background: linear-gradient(to top right,#ff2a00 0,#ffb600 100%);
    background-clip: text;
    -webkit-text-fill-color: transparent;
}

.conversor .search-bar {
  padding: 5px 10px 5px 0px;
  color: #313131;
  font-size: 15px;
  appearance: none;
  border:none;
  outline: none;
  background: none;
  background-color: rgba(255, 255, 255, 0.5);
  transition: 0.4s;
  border-bottom: 1px solid black
}

.conversor .search-bar:focus {
    background-color: rgba(255, 255, 255, 0.75);
}

.conversor .button {
    appearance: none;
    border:none;
    outline: none;
    background: none;
    cursor: pointer;

    margin-left: 5px;

    border: 1px solid black;

    padding: 5px 7px;

    transition: 0.3s;
}

.conversor .button:hover {
    border: 1px solid orangered;
}

.conversor p {
    margin: 0;
    padding: 0;
    text-align: start;
    font-weight: bold;
}

</style>
