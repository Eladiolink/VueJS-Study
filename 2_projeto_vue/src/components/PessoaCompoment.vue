<template>
    <div>
        <InfoVue/>
    </div>
</template>

<script>
    import InfoVue from './InfoVue.vue';

    export default{
        name: "PessoaCompoment",
        data(){
            return{
                name: "Pepe"
            }
        },
        components:{
            InfoVue
        }
    }
</script>