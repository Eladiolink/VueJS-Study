<template>
    <div>
      <PrimeiroComponenteVue/>
      <LifeCycle/>
    </div>
</template>

<script>
import PrimeiroComponenteVue from './components/PrimeiroComponente.vue'
import LifeCycle from './components/LifeCycle.vue';
  export default{
    name: "app",
    components:{
      PrimeiroComponenteVue,
      LifeCycle
    }
  }
</script>