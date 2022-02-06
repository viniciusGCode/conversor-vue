<template>
  <div id="app">
      <h1 class="title">Conversor de Moedas</h1>

    <Conversor
    moeda1="BRL"
    moeda2="USD"
    />
    <Conversor
    moeda1="BRL"
    moeda2="EUR"
    />
    <Conversor
    moeda1="BRL"
    moeda2="JPY"
    />


  </div>
</template>

<script>
import Conversor from './components/Conversor';
import './assets/css/_global.css';


export default {
  name: 'App',
  components: {
    Conversor
  },
  data(){
    return{

    }
  }
}
</script>

<style>

</style>
