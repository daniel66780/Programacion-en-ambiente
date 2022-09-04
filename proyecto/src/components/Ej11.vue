<template>
  <h1>Ejercicio 11: Calcular nota semestre</h1>
  <br>
  <h1>Inserte sus notas</h1>
  <br>
  <input type="text" v-model="notas.nombre" placeholder="Nombre" @keyup.enter="process">
  <br>
  <input type="number" v-model="notas.nota1" placeholder="Nota 1" @keyup.enter="process">
  <br>
  <input type="number" v-model="notas.nota2" placeholder="Nota 2" @keyup.enter="process">
  <br>
  <input type="number" v-model="notas.nota3" placeholder="Nota 3" @keyup.enter="process">
  <br>
  <h1>{{notas.nombre}} {{notas.respuesta}}</h1>
</template>
<script>
export default{
  name: 'Numeros',
  data(){
    return {
      notas: {
        nombre: '',
        nota1: '',
        nota2: '',
        nota3: '',
        prom: '',
        respuesta: ''
      }

    }
  },
  methods:{
    process(){
      this.notas.prom = (parseFloat(this.notas.nota1)+parseFloat(this.notas.nota2)+parseFloat(this.notas.nota3))/3;
      if(this.notas.prom >= 3){
        this.notas.respuesta = 'Usted gano la materia'
      }
      else if(parseFloat(this.notas.prom) < 3, parseFloat(this.notas.prom) >= 0) {
        this.notas.respuesta = 'Usted perdio la materia mi sogh'
      }
    }
  }
}

</script>

<style scoped>

</style>
