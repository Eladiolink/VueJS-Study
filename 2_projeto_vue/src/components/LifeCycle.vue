<template>
    <div>
        <h1>My name is: {{name}}</h1>
    </div>
</template>

<script>
    export default{
        name: "LifeCycle",
        data(){
            return {
                name : "sla kekw"
            }
        },
        created(){
            setTimeout(()=>{
                this.name = "Eladio"
            }, 1000)
           
        },
        mounted(){
            setTimeout(()=>{
                this.name =  'Pepe'
            }, 2000)  
        }
    }
</script>

