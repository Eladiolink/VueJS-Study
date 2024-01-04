<template>
    <div>
        <h1>Hello Vue!!</h1>
        <P>My name is {{ name }}</P>
        <p>I work witrh {{proffission}}</p>
    </div>
</template>

<script>
  export default{
    name: "PrimeiroComponente",
    data(){
        return {
            name: "Eladio",
            proffission:"Programmer"
        }
    }
  }
</script>