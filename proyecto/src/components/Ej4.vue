<template>
  <h1>Ejercicio 4: A continuacion Digite 3 numeros</h1>
  <br>
  <input type="num1" v-model="num1" placeholder="Nr1" @keyup.enter="process">
  <br>
  <input type="num2" v-model="num2" placeholder="Nr2" @keyup.enter="process">
  <br>
  <input type="num3" v-model="num3" placeholder="Nr3" @keyup.enter="process">
  <br>
  <h2>{{respuesta}}</h2>
</template>
<script>
export default{
  name: 'Numeros',
  data(){
    return {
      num1: '',
      num2: '',
      num3:'',
      respuesta:''
    }
  },
  methods:{
    process(){
      if (this.num1== this.num2 && this.num2 == this.num3){
        this.respuesta = 'El numero 1, 2 y el numero 3 son iguales'
      }
      else if (this.num1== this.num2){
        this.respuesta = 'El numero 1 y el numero 2 son iguales'
      }
      else if (this.num1 == this.num3){
        this.respuesta = 'El numero 1 y el numero 3 son iguales'
      }
      else if (this.num2 == this.num3){
        this.respuesta = 'El numero 2 y el numero 3 son iguales'
      }
      else{
        this.respuesta = 'Ninguno de los numeros son iguales'
      }
    }
  }
}
</script>

<style scoped>

</style>
