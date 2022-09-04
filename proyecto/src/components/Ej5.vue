<template>
  <div>
      <h1>Ejercicio 5: Orenamiento de listas </h1>
      <p> Ingrese un numero y presione enter. </p>
      <input @keypress.enter="arrPush()" type="number" v-model="num" id="a"><br/>
      <ul>
      <li v-for="(item) in items">
          <span> {{item}} </span>
      </li>
      </ul>
      <p> (Presione el botón para ordenar los números)</p>
      <button @click="orderList()"> Ordenar </button> <br/>
  </div>

</template>
<script>
export default {
  name: "MinToMax",
  data(){
      return{
          num: 0,
          items:[
          ]
      }
  },
  methods: {
      orderList(){
          return this.items.sort((a,b)=>a-b);
      }
  },
  computed: {
      arrPush(){
          return this.items.push(this.num);
      },
  }
}
</script>

<style scoped>

</style>
