<template>
  <v-app id="app">
      <PokemonPage />
  </v-app>
</template>

<script>
import PokemonPage from './components/PokemonPage.vue';

export default {
  components: {
    PokemonPage
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Changa:wght@400;700&family=MedievalSharp&family=Paytone+One&family=Staatliches&display=swap');

*{
  box-sizing: border-box;
  font-family: 'Changa', sans-serif;
  margin:0;
  padding: 0;
}

#app{
  background: url(../public/assets/img/poke-bg.jpg) center / cover;
}

</style>
