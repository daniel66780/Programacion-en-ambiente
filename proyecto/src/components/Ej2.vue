<template>
  <h1>Ejercicio 2: Calculadora de minutos</h1>
  <br>
  <input type="Minutos" v-model="minus" placeholder="Minutos" @keyup.enter='hora'>
  <br>
  <h2>Minutos Consumidos: {{a}} Coste: ${{coste}}</h2>
</template>
<script>

export default{
  name: 'Minutos',
  data(){
    return {
      minus:'',
      coste:'',
      minimo: 3,
      def:'',
      a:''
    }
  },  
  methods: {
    hora(){
      if (Math.floor(this.minus <= 3)){
        this.coste = 100
        this.a = this.minus
      }
      else if (Math.floor(this.minus > 3)){
        this.def = (Math.floor(this.minus-this.minimo)*50)
        this.coste = (Math.floor(this.def+100))
        this.a = this.minus
      }
    }
    
  }
}
</script>

<style scoped>

</style>
