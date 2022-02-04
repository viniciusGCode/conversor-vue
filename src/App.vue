<template>
  <div id="app">
    <Conversor
    moeda1="EUR"
    moeda2="BRL"

    />
  </div>
</template>

<script>
import Conversor from './components/Conversor';
import './css/_global.css';


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
