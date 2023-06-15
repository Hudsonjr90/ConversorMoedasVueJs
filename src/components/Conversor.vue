<template>
  <div class="conversor">
        <div class="col-sm-12 ">
            <div class="card ">
                <div class="card-header">
                    {{nome_moeda1}} / {{nome_moeda2}}
                </div>
                <div class="card-body">
                    <label for="">{{nome_moeda1}}:</label>
                    <input v-model="value" type="number" class="form-control">
                    <label for="">{{nome_moeda2}}:</label>
                    <input disabled v-bind:value="valor_moeda2" type="string" class="form-control">
                    <h1 class="text-center" >{{multipliedValue.toFixed(2)}}</h1>
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
    valor_moeda2:String
    
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
.conversor .card {
    max-width: 300px;
    padding: 20px;
    box-shadow: 0px 4px 8px 0px rgba(214, 26, 26, 0.884);
    margin-left: 40px;
    display: flex;
    justify-content: center;
}

.card-header {
    color: #313131;
}

.conversor .valor {
    background: linear-gradient(to top right,#ff2a00 0,#ffb600 100%);
    background-clip: text;
    -webkit-text-fill-color: transparent;
}


</style>
