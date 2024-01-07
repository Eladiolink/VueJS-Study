<template>
    <div>
        <button @click="ativar()">click here</button>
        <span v-show="ativou">Ativado!</span>
    </div>
</template>

<script>
    export default{
        name:"ReutilizacaoVue",
        data(){
            return{
                ativou:false
            }
        },
        methods:{
            ativar(){
                this.ativou = !this.ativou
            }
        }
    }
</script>