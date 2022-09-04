<template>
  <div>
    <h1>Hola :D</h1>
    <span>9</span>
  </div>
  <div>
    <h1> {{customTitle}} </h1>
  </div>
  <div>
    <input type="text" v-model="newMessage" @keypress.enter="addQuote()"/>
    {{newMessage}}
  </div>
  <div>
    <span> {{counterNumber}}*{{counterNumber}}= {{getMultiplication}} </span> 
    <button id="a" class="xy" @click="increase">+2</button><br/>
    <button id="b" class="xy" @click="decrease">-1</button>
    <button id="c" class="xy" @click="reset">reset</button>
  </div>
  <div>
    <ul>   
     <li v-for="(item, index) in items">
      <span>{{index+1}}. {{item.mensaje}}, por {{item.autor}}</span>
      <span v-if="item.autor"> Por {{item.autor}}</span>
      <span v-else>No author</span>
    </li>
  </ul>
  </div>
</template>
<script>
export default {
  props: {
      title: String,
      start:{
        type: Number,
        default: 10,
        required: false,
        validator: (value) => {
          return value>=0
        }

      }
    },
    name: 'Counter',
    data(){
      return {
        counterNumber: 5,
        newMessage: [
          
        ],
        hora: [
          
        ],
        buenos_: [
          
        ],
        items:[
          {mensaje:'foo', autor: 'Juan'},
          {mensaje:'bar', autor: 'Roberto'}
        ],
        items2: [
          {segundos: 'Segundos', minutos:'minutos', horas:'horas'}
        ],
        items3: [
          {pago: 'Total a pagar', minuto_llamada:'minutos'}
        ],
        items4: [
          {nombre: 'Nombre', hora:'hora', momento_dia:'tiempo'}
        ]
      }
    }, 
    methods:{
      increase(){
        this.counterNumber+=2;
      },
      decrease(){
        this.counterNumber--;
      },
      reset(){
        this.counterNumber=5;
      },
      addQuote(){
        return this.items.unshift({
          mensaje:this.newMessage});
          // Para probar el v-if y v-else quitar el autor
      }
    },
    computed:{
      getMultiplication(){
        console.log('calling method')
        return this.counterNumber * this.counterNumber
      },
      customTitle(){
        return this.title|| 'Transformar segundos!'
      },
    }
  }; 
</script>
<style scoped>
  
</style>