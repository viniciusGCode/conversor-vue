<template>
  <div id="app">
    <div class="escolher-moeda">
      
    </div>


    <Conversor
    :moeda1="moeda1"
    :moeda2="moeda2"
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
      moeda1: 'USD',
      moeda2: 'BRL'

    }
  }
}
</script>

<style>

</style>
