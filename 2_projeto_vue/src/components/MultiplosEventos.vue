<template>
    <div>
        <button @click="primeiro($e), segundo(), terceiro()" >Ativar Multiplos Eventos</button>
        <p>{{multiplos_eventos}}</p>
    </div>
</template>

<script>
    export default{
        name:"MultiplosEventos",
        data(){
            return{
                multiplos_eventos:""
            }
        },
        methods:{
            primeiro(){
                this.multiplos_eventos = "Primeiro evento ativado"
            },
            segundo(){
                setTimeout(()=> this.multiplos_eventos = "Segundo Evento!",500)
            },
            terceiro(){
                setTimeout(()=> this.multiplos_eventos = "",1500)
            }
        }
    }
</script>

<style scoped>
    div{
        margin: 100px;
    }
</style>