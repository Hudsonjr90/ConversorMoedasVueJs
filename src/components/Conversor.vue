<template>
    <div class="conversor">
<h2>{{moedaA}} para {{moedaB}}</h2>
<input type="text" v-model="moedaA_value" v-bind:Placeholder="moedaA">
<input type="button" value="Converter" v-on:click="converter" >
<h2></h2>
    </div>
</template>

<script>
 export default {
     name: "conversor",
     props: ["moedaA", "moedaB"],
      data(){
          return {
              moedaA_value : "",
              moedaB_value : 0
          };
      },
      methods: {
          converter(){
              let de_para = this.moedaA + "_" + this.moedaB;

              let url = "http://economia.awesomeapi.com.br/json/last/"+
                de_para
              

              fetch(url)
               .then(res=>{
                   return res.json();
                   })
                        .then(json=>{
                            let cotacao = json[de_para].val;
                            this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(
                                2
                            );
                        });
          }
      }
 };
</script>

<style scoped>

.conversor{
    padding: 20px;
    max-width: 300px;
    box-shadow: 0 4px 8px 0 rgba(0,0,0, 0.2);
};

</style>