<script>
  import PokemonImage from '@/components/PokemonImage.vue';
  import PokemonOptions from '@/components/PokemonOptions.vue';

  export default{
    name: 'App',
    components: {
      PokemonImage,PokemonOptions
    }
}
</script>



<template>
  <h1 class="animate_animated animate_bounce"> Who's That Pokémon? </h1>
  <br>
  <PokemonImage 
    pokemon-id="1" 
    show-pokemon="true" 
  ></PokemonImage>


  <Pokemon-options></Pokemon-options>
</template>



<style scoped>
  h1{
    color: black
  }
.fade-in {
  animation: fadeIn;
  animation-duration:.5s;

}
</style>