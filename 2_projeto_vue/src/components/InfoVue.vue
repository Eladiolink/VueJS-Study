<template>
    <div>
        <h2>This is person description</h2>

        <p>{{ compEmail }} - {{ email }}</p>

        <p v-if="is_working" >I have a job :)</p>
        <p v-else>I need a job :(</p>
        <p>Person name is: {{name}}</p>
        <p>I'm working right now, end using few techs allso:</p>
        <ul>
            <li v-for="(stack,index) in stacks" :key="index">{{stack}}</li>
        </ul>
        <ul>
            <li v-for="like in likes" :key="like.id">{{like.attr}}</li>
        </ul>
 
        <div>
            <button @click="is_show_email">{{ text_botton }}</button>
        </div>
        <p v-show="show_email">Mande uma mensagem para {{email}}</p>
        <p>Para acessar meu portfolio <a v-bind:href="my_link">clique aqui</a></p>
        <PictureVue/>
    </div>
</template>

<script>
import PictureVue from './Picture.vue';
    export default{
        name: "InfoVue",
        props:{
            compEmail: String,
            email: String
        },
        data(){
            return{
                name : "Pepe",
                is_working : false,
                show_email: false,
                my_link:'https://google.com',
                text_botton: "Mostrar E-mail",
                stacks:["Java",'PHP','Vue','Docker','Git','CI/CD'],
                likes: [
                    {id:1, attr:'Hambuerger'},
                    {id:2, attr:'Pizza'},
                    {id:3, attr:'Doce de leite'}
                ]
            }
        },
        components:{
            PictureVue
        },
        methods:{
            is_show_email(){
                this.show_email = !this.show_email

                if(this.show_email)
                    this.text_botton = "Ocultar E-mail"
                else
                    this.text_botton = "Mostrar E-mail"
            }
        }
    }
</script>