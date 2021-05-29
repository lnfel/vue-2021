<template>
    <div v-for="pokemon in pokemons">
        <div :key="pokemon.game_indices[0].game_index" class="flex items-center justify-between space-x-2">
            <Pokemon @release-pokemon="$emit('release-pokemon', {id: pokemon.game_indices[0].game_index, name: pokemon.species.name})" :pokemon="pokemon" />
        </div>
    </div>
</template>

<script>
import Pokemon from './Pokemon'

export default {
    name: 'Pokemons',
    props: {
        pokemons: Array
    },
    components: {
        Pokemon
    },
    emits: ['release-pokemon'],
}
</script>