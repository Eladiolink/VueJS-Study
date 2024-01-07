<template>
    <div>
        <InfoVue compEmail="eladiolink1@gmail.com" :email="email"/>
    </div>
</template>
 
<script>
    import InfoVue from './InfoVue.vue';

    export default{
        name: "PessoaCompoment",
        data(){
            return{
                name: "Pepe",
                email:"Eladiolink@hotmail.com"
            }
        },
        components:{
            InfoVue
        }
    }
</script>