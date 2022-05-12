<template>
    <div class="conversor">
        <h2>{{ moedaA }} Para {{ moedaB }}</h2>
        <input type="text" :placeholder="moedaA" v-model="moedaA_value">
        <input type="button" value="Converter" v-on:click="converter">
        <h2>{{ moedaB_value }}</h2>
    </div>    
</template>

<script>
export default {
    name: 'Conversor',
    props: [
        'moedaA',
        'moedaB'
    ],
    data() {
        return {
            moedaA_value: '',
            moedaB_value: 0
        }
    },
    methods: {
        converter() {
            let de_para = this.moedaA + "_" + this.moedaB;
            let url = "https://free.currconv.com/api/v7/convert?q=" + de_para + "&compact=ultra&apiKey=a6f98962807910b11324";
        fetch(url)
            .then(response => {
                console.log(url)
                return response.json();
            })
            .then(json => {
                console.log(json[de_para])
                let cotacao = json[de_para];
                this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(2);
            });
        }
    },
}
</script>

<style scoped>
.conversor {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    padding: 20px;
    max-width: 300px;
}
</style>