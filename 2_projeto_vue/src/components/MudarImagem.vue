<template>
    <div>
        <div>
            <button @click="$emit('mudarImagem')">Torcar Img</button>
        </div>
    </div>
</template>
<script>
    export default{
        name:"MudarImagem",
        emits:['mudarImagem'],
        data(){
            return{

            }
        }
    }
</script>