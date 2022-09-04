<!-- Para correr el codigo, debes usar npm run dev -->
<!-- Para cambiar el color del background debes ir a la carpeta assets y en base.css -->

<template>
  <h1> {{customTitle}} </h1>
  <!-- <h2> {{start}}</h2> -->
  <!-- <input type="text" v-model="newMessage" @keypress.enter="addQuote()"/>
    {{newMessage}} -->
    <input type="text" v-model="newMessage" @keypress.enter="addQuote()"/>
    <button id="a" class="xy" @click="calculate">Calcular segundos, minutos, horas!</button>
      <!-- {{newMessage}} -->
    <ul>
      <li v-for="(items2,index) in items2">
      {{index+1}}. Segundos: {{items2.segundos}}, minutos: {{items2.minutos}}, horas: {{items2.horas}}
      </li>
    </ul><br>
    
    <input type="text" v-model="hora" @keypress.enter="addQuote()"/>
    <button id="a" class="xy" @click="toPay">Cuanto cuesta mi llamada?</button>
    <ul>
      <li v-for="(items3,index) in items3">
      {{index+1}}. A pagar: {{items3.pago}}, minutos: {{items3.minuto_llamada}}
      </li>
    </ul><br>

    <!-- <input type="text" v-model="buenos_" @keypress.enter="addQuote()"/>
    <button id="a" class="xy" @click="toPay">Cuanto cuesta mi llamada?</button>
    <ul>
      <li v-for="(items4,index) in items4">
      {{index+1}}. {{items4.momento_dia}} {{items4.nombre}}, {{items4.hora}} 
      </li>
    </ul>
 -->
  <input type="text" v-model="newMessage" @keypress.enter="addQuote()"/>
    {{newMessage}}
  <ul>   
    <!-- Esto es una lista desordenada, lo que va a hacer es que por renglones
    va a generarme como una lista y va a separar cada item con un punto (Cada item es lo qeu significa el <li></li>) -->
    <!-- las listas no ordenadas son <ol></ol> -->
     <li v-for="(item, index) in items">
      <span>{{index+1}}. {{item.mensaje}}, por {{item.autor}}</span>
      <span v-if="item.autor"> Por {{item.autor}}</span>
      <span v-else>No author</span>
    
    </li>
  </ul>


  <!-- <button id="a" class="xy" @click="addQuote()">Enter quote</button> -->
  <!-- <span> {{counterNumber}}*{{counterNumber}}= {{getMultiplication}} </span> -->
  <!-- <button id="a" class="xy" @click="increase">+2</button><br/> -->


  <!-- Los ids son los keys que no se pueden repetir
  Las clases son los ids que relacionan unas cosas con otras  -->


  <!-- <button id="b" class="xy" @click="decrease">-1</button>
  <button id="c" class="xy" @click="reset">reset</button> -->
</template>

<script>
  export default {
    // las props son propiedades que vienen del app, se usan asi:
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
      },
      calculate(){
        return this.items2.unshift({
          segundos: this.newMessage,
          minutos: this.newMessage/60,
          horas: this.newMessage/3600});
      },
      toPay(){
        if (this.hora <=3)
          return this.items3.unshift({
            pago: 100,
            minuto_llamada: this.hora,
            })
        else
          return this.items3.unshift({
            pago: 100+(50*(this.hora-3)),
            minuto_llamada: this.hora,
            })
            },
        
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
  /* button {
  background-color: #4CAF50; 
  border: none;
  color: rgb(17, 0, 255);
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
} */

  /* y asi se puede cambiar una clase entera, con el punto antes del nombre*/
  
  .xy{background-color: #4c9baf; 
  border: none;
  color: rgb(255, 230, 0);
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  }
  /* asi se puede cambiar un id en especifico, con el numeral # antes del nomnbre*/

  #a{background-color: #0ce84a; 
  border: none;
  color: rgb(249, 48, 48);
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  }

  /* se van a aplicar los cambios de forma descendente. Por ende, lee de arriba hacia abajo */
</style>
