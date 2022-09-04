<template>
    <img src="https://pbs.twimg.com/profile_images/1540810647604183046/OhYhwdAi_400x400.jpg"/>
    <div class="bg-dark"></div>
    <div class="indecision-container">
        <input type="text" placeholder="Ask a question..." v-model="question"/>
        <p> Recuerda finalizar con el signo de interrogacion (?)</p>
    </div>
    <div>
        <h2>{{question}}</h2>
        <h1> SI, no, ... Pensando... </h1>
    </div>
</template>
<script>
export default {
    data(){
      return {
        question: ""
      }
    },
    watch: {
        question(value, oldValue){
            console.log(value, oldValue)
        }
    }
    
}
</script>
<style scoped>
    
</style>


<!-- Un servicio web es  -->