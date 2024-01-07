<template>
    <div>
        <img :src="avatar" :alt="description">
        <MudarImagem @mudar-imagem="mudarImagem"/>
    </div>
</template>

<script>
import MudarImagem from './MudarImagem.vue';
    export default{
        name:'PictureVue',
        data(){
            return{
                avatar:"/img/user.jpg",
                description:"user image"
            }
        },
        components:{
            MudarImagem
        },
        methods:{
            mudarImagem(){
                if(this.avatar == "/img/user.jpg")
                    this.avatar = "/img/Hobbit.jpg"
                else
                    this.avatar = "/img/user.jpg"
            }
        }
    }
</script>