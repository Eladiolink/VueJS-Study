<template>
    <div>
        <h2>This is person description</h2>
        <p>Person name is: {{name}}</p>
        <p>I'm working right now, end using few techs also PHP, JS, Python 
            and Java,, with Vue and React by Frontend.
        </p>
    </div>
</template>

<script>
    export default{
        name: "InfoVue",
        data(){
            return{
                name : "Pepe"
            }
        }
    }
</script>