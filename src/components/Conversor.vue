<template>
    <div class="conversor" v-on="getCotacao">

        <h2 class="title">{{moedaA}} para {{moedaB}}</h2>
        <input type="text" class="search-bar" v-model="moedaA_value" :placeholder="moedaA">
        <button class="button" v-on:click="converter">Converter</button>
        <h2 class="valor">{{moedaB_value}}</h2>
        <p v-if="moedaA != 'BRL'">{{moedaA}}: {{cotacao}}</p>
    </div>
</template>

<script>
    export default {
        name : "Conversor",
        props: ["moedaA","moedaB"],
        data(){
            return {
                moedaA_value: "",
                moedaB_value: 0,
                cotacao: 0
            };
        },
        beforeMount() {
            this.getCotacao()
        },
        methods:{
            converter() {
                let de_para = this.moedaA + "_" + this.moedaB;
                let url = "http://free.currencyconverterapi.com/api/v5/convert?q=" + de_para + "&compact=y&apiKey=515ce8836bb3907a90fe";
                fetch(url).then(res => {
                    return res.json();
                }).then(json => {
                    let cotacao = json[de_para].val;
                    this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
                })
            },

            getCotacao() {
                let de_para = this.moedaA + "_" + this.moedaB;
                let url = "http://free.currencyconverterapi.com/api/v5/convert?q=" + de_para + "&compact=y&apiKey=515ce8836bb3907a90fe";
                fetch(url).then(res => {
                    return res.json();
                }).then(json => {
                    if (this.moedaA != 'BRL') {
                        this.cotacao = parseFloat(json[de_para].val).toFixed(2);
                    }
                })
            }
        }
    };
</script>

<style scoped>
.conversor{
    max-width: 300px;
    padding: 20px;
    box-shadow: 0px 4px 8px 0px rgba(0,0,0,0.2);
    margin: 5px;
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