<template>
  <div>
      <h1> Ejercicio 6: Numeros impares</h1>
      <input @keypress.enter="odd()" type="number" v-model="num" id="a" placeholder="Inserta un número"><br/>
      <h1> Los números impares menores que {{num}} son: {{this.nums}}</h1>
  </div>
</template>

<script>
export default {
  name: "OddNumber",
  data(){
      return{
          nums: [],
          x:0
      }
  },
  methods: {
      odd(){
          while(this.x < this.num){
              if(this.x%2 != 0){
              this.nums.push(this.x)
              }
          this.x +=1
          }
      }
  }
}
</script>

<style scoped>

</style>
