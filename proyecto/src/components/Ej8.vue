<template>
  <h1>Ejercicio 8: Numeros Aleatorios</h1>
  <br>
  <div> 
      <br>
      <input type="text" v-model="index" placeholder="Posición del Arreglo" @keyup="create()">
      <br>
      <p v-if="index<10">
          <h2>
              Arreglo: {{arr}}
          </h2>
          <br>
          <button @click="divide"> Dividir </button>
          <br>
          <h2>
              Division: {{div}}
          </h2>
      </p>

      <p v-else> Esa Posición no se encuentra en el arreglo</p>
  </div>
</template>

<script>
export default {
  name: 'Aleatorio',
  data(){
      return{
          arr: undefined,
          index: '',
          div:undefined

      }
  },
  methods: {
      create(){
          this.arr = new Array(10);
          for (let i = 0; i < this.arr.length; i++) {
              this.arr[i] = Math.floor(Math.random()*100);
          }
      },
      divide(){
          this.div = new Array(10);
          for (let i = 0; i < this.arr.length; i++) {
              this.div[i] = parseFloat((this.arr[i]/this.arr[this.index]).toFixed(2));
          }

      }
  },
}
</script>

<style scoped>
</style>