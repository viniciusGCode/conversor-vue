<template>

    <div class="conversor">
        <h2 class="conversor-title"> {{moeda1}} to {{moeda2}} </h2>

        <div class="conversor-input">
            <input type="text" class="text" v-model="moeda1_value" v-bind:placeholder="moeda1">
            <button class="submit" v-on:click="mounted()">Enviar</button>
            <h2 class="moeda2-number">{{moeda2_value}}</h2>
        </div>

    </div>

</template>

<script>
const axios = require('axios').default;


export default {
    name: 'Conversor',
    props: ["moeda1", "moeda2"],
    data(){
        return{
            moeda1_value: '',
            moeda2_value: 0,
            result: [],
            cotacao: ''
        }
    },
    methods:{
        mounted(){
            this.getConverter();
        },
        async getConverter () {
            let from_to = this.moeda1 + "_" + this.moeda2;
            let url = "https://free.currconv.com/api/v7/convert?q="+
                from_to
            +"&compact=ultra&apiKey=5e2f07ccc54c6d2f0f58";
            const response = await axios.get(url);
            this.result = response.data;
            JSON.stringify(this.result);
            this.cotacao = Object.values(this.result);
            this.moeda2_value = (this.cotacao * parseFloat(this.moeda1_value)).toFixed(2);
        }
    }
    
}
</script>

<style scoped>

.conversor{
    margin: 15px;
    justify-content: column;
}

.text{
    margin-top: 5px;
    width: 200px;
    height: 30px;
    color: var(--color-text-dark);
}

.submit{
    display: flex;
    height: 35px;
    margin-top: 10px;
    margin-bottom: 10px;
    padding: 7px 10px;
    background-color: var(--color-background-button);
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: 0.2s opacity;
}

.submit:hover{
    opacity: 0.8;
}


</style>