<template>
  <form action="" @submit="enviarForm($event)">
    <InputTextVue/>
    <InputTextVue/>

    <div><input type="text" placeholder="name" v-model="name"></div>
    <div><input type="email" placeholder="email" v-model="email"></div>
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
                name: "",
                email:""
            }
        },
        components:{
            InputTextVue,
            SubmitVue
        },
        methods:{
            enviarForm(e){
                e.preventDefault();
                const name = this.name
                const email = this.email
                console.log("ENVIADO!!!",name,email)
                // Ajax
            }
        }
    }
</script>