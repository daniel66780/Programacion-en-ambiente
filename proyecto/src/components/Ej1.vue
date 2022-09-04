<template>
  <h1>Ejercicio 1: Calcular sus segundos a hh:mm:ss</h1>
  <br>
  <input type="Digite los segundos" v-model="sec" placeholder="Segundos" @keyup.enter='hora'>
  <br>
  <h2> Hora: {{horas}} Minutos: {{minutos}} Segundos: {{segundos}}</h2>
</template>
<script>

export default{
  name: 'segundos',
  data(){
    return {
      horas: '',
      minutos:'',
      sec:'',
      segundos:''
    }
  },  
  methods: {
    hora(){
          this.segundos= Math.floor(this.sec);
          this.minutos= Math.floor(this.sec/60);
          this.horas= Math.floor(this.sec/3600);
    }
  },
}
</script>

<style scoped>

</style>
