<template>
    <div>
        <h2>This is person description</h2>

        <p v-if="is_working" >I have a job :)</p>
        <p v-else>I need a job :(</p>
        <p>Person name is: {{name}}</p>
        <p>I'm working right now, end using few techs allso:</p>
        <ul>
            <li>Java</li>
            <li>PHP</li>
            <li>Vue</li>
            <li>Docker</li>
            <li>Git</li>
            <li>CI/CD</li>
        </ul>

        <p v-show="show_email">Mande uma mensagem para {{email}}</p>
    </div>
</template>

<script>
    export default{
        name: "InfoVue",
        data(){
            return{
                name : "Pepe",
                is_working : true,
                show_email: false,
                email:"Eladiolink@gmailcom"
            }
        },
    }
</script>