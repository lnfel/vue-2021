<template>
  <div class="container py-8 mx-auto">
    <Header title="Pokédex"/>
    <Pokemons :pokemons="pokemons" />
  </div>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header'
import Pokemons from './components/Pokemons'

export default {
  name: 'App',
  components: {
    //HelloWorld
    Header,
    Pokemons
  },
  data() {
    return {
      pokemons: []
    }
  },
  created() {
    this.pokemons = [
      {
        species: {
          name: "pikachu"
        },
        sprites: {
          back_default: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/back/25.png",
          front_default: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/25.png"
        }
      },
      {
        species: {
          name: "eevee"
        },
        sprites: {
          back_default: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/back/133.png",
          front_default: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/133.png"
        }
      },
    ]
  }
}
</script>

<style>
#app {

}
</style>
