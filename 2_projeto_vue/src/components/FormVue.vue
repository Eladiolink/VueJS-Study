<template>
  <form action="">
    <InputTextVue/>
    <InputTextVue/>
    <SubmitVue/>
  </form>
</template>

<script>
import InputTextVue from './form/InputText.vue'
import SubmitVue from './form/SubmitVue.vue'
    export default{
        name: "FormVue",
        data(){
            return{
                name: "Pepe"
            }
        },
        components:{
            InputTextVue,
            SubmitVue
        }
    }
</script>