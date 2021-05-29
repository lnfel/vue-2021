<template>
    <div v-for="pokemon in pokemons">
        <div class="flex items-center space-x-2">
            <img :src="pokemon.sprites.front_default" :alt="pokemon.species.name">
            <h3 class="">{{ pokemon.species.name }}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Pokemons',
    props: {
        pokemons: Array
    }
}
</script>