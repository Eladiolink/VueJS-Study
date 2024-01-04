<template>
    <div>
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
  export default{
    name: "app",
    components:{
      PrimeiroComponenteVue,
      LifeCycle,
      PessoaVue,
      FormVue
    }
  }
</script>