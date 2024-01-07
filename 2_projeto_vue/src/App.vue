<template>
    <div>
      <Header/>
      <PrimeiroComponenteVue/>
      <hr>
      <LifeCycle/>
      <hr>
      <PessoaVue/>
      <hr>
      <FormVue/>
      <hr>
    </div>
</template>

<script>
import PrimeiroComponenteVue from './components/PrimeiroComponente.vue'
import LifeCycle from './components/LifeCycle.vue';
import PessoaVue from './components/PessoaCompoment.vue';
import FormVue from './components/FormVue.vue';
import Header from './components/Header.vue';
  export default{
    name: "app",
    components:{
      PrimeiroComponenteVue,
      LifeCycle,
      PessoaVue,
      FormVue,
      Header
    }
  }
</script>

<style>
  body{
    background-color: #333;
    color: #FFF
  }

  button{
    border-radius: 0%;
    border: 0px;
  }

  a{
    color:red;
    font-weight: bold;
  }
</style>