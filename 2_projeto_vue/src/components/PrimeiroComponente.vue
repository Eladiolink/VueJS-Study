<template>
    <div>
        <h1>Hello Vue!!</h1>
        <P>My name is {{ name }}</P>
        <p>I work witrh {{proffission}}</p>
        <MultiplosEventos/>
        <Reutilizacao/>
        <Reutilizacao/>
        <Reutilizacao/>
        <Reutilizacao/>
        <Reutilizacao/>

    </div>
</template>

<script>
import MultiplosEventos from './MultiplosEventos.vue';
import Reutilizacao from './Reutilizacao.vue';

  export default{
    name: "PrimeiroComponente",
    data(){
        return {
            name: "Eladio",
            proffission:"Programmer"
        }
    },
    components:{
      MultiplosEventos,
      Reutilizacao
    }
  }
</script>