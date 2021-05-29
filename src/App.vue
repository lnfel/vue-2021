<template>
  <div class="container py-8 px-2 mx-auto">
    <Header title="Pokédex"/>
    <Pokemons @release-pokemon="releasePokemon" :pokemons="pokemons" />
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
  methods: {
    releasePokemon({id, name}) {
      // simulate soft delete by filtering data not equal to deleted pokemon
      if(confirm(`Release ${this.titleCase(name)}?`))
      this.pokemons = this.pokemons.filter((pokemon) => pokemon.game_indices[0].game_index != id)
    },
    titleCase(str) {
      return str.toLowerCase().replace(/\b(\w)/g, s => s.toUpperCase())
    }
  },
  emits: ['release-pokemon'],
  created() {
    this.pokemons = [
      {
        game_indices: [
          {
            game_index: 25,
            version: {
              name: "emerald",
              url: "https://pokeapi.co/api/v2/version/9/"
            }
          }
        ],
        species: {
          name: "pikachu"
        },
        sprites: {
          back_default: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/back/25.png",
          front_default: "https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/25.png"
        }
      },
      {
        game_indices: [
          {
            game_index: 133,
            version: {
              name: "emerald",
              url: "https://pokeapi.co/api/v2/version/9/"
            }
          }
        ],
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
