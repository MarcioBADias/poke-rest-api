<template>
  <v-app>
    <Pokemon />
  </v-app>
</template>

<script>
import Pokemon from './components/Pokemon.vue'

export default {
  comments: {
    Pokemon
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
</style>
