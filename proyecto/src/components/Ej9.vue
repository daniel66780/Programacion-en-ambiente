<template>
  <h1>Ejercicio 9: Tablas (No supe como hacer este ni el 10 profe :c )</h1>
  <br>
  <p>Use los botones para elegir el numero de filas y columnas que quiere que tenga la tabla</p>
  <br>
  <input type="button" value="Add Bottom" @click="addRow()"/>
  <br>
  <input type="button" value="Add Top" @click="addRow(1)"/>
  <br>
  <div id="a">
    <tabla id ="b">

    </tabla>
  </div>
</template>

<script>
export default {
  name: "Salary",
  data(){
      return{
          filas:'',
          column:''
          
      }
  },
  methods: {
      addRow (top) {
  var table = document.getElementById("b");

  if (top) { var row = table.insertRow(0); }
  else { var row = table.insertRow(); }

  var cell = row.insertCell();
  cell.innerHTML = "AA";
  cell = row.insertCell();
  cell.innerHTML = "BB";
  }
    }
    }
    
  

</script>

<style scoped>
        table{
            border-collapse: collapse;
            border-spacing: 0;
        }
        th, td{
            padding: 10px 20px;
            border: 1px solid #000;
        }
</style>
