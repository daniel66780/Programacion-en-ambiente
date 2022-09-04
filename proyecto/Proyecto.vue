<!-- Para correr el codigo, debes usar npm run dev -->

<!-- debo de abrir el app y el clos componentes que estan en src para poder editarlo -->



<!-- <script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
</script>

<template>
<HelloWorld/>
<hello-world></hello-world>
</template>

<script>
  import HelloWorld from '@/components/HelloWorld.vue'
  export default {
    name: 'App',
    components :{
      HelloWorld
    }
  }
</script> -->

<template>
  <h1> Counter </h1>
  <span> {{counterNumber}}*{{counterNumber}}= {{getMultiplication}} </span>
  <button @click="increase">+1</button>
  <button @click="decrease">-1</button>
  <button @click="reset">reset</button>
</template>

<script>
  export default {
    name: 'Counter',
    data(){
      return {
        counterNumber: 5
      }
    }, 
    methods:{
      increase(){
        this.counterNumber++;
      },
      decrease(){
        this.counterNumber--;
      },
      reset(){
        this.counterNumber=5;
      }
    },
    computed:{
      getMultiplication(){
        console.log('calling method')
        return this.counterNumber * this.counterNumber
      }
    }
  }; 
</script>

<style scoped>
</style>