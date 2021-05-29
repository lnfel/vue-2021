<template>
    <div class="flex items-center">
        <img :src="pokemon.sprites.front_default" :alt="pokemon.species.name">
        <h3 class="capitalize">{{ pokemon.species.name }}</h3>
    </div>
    <button class="bg-red-600 text-white px-2 py-1 rounded hover:bg-red-700 focus:outline-none focus:bg-red-600 focus:ring-2 focus:ring-offset-2 focus:ring-red-600 shadow transition duration-700" @click="onDelete(pokemon.game_indices[0].game_index, pokemon.species.name)"><i class="fas fa-trash fa-fw"></i></button>
</template>

<script>
export default {
    name: 'Pokemon',
    props: {
        pokemon: Object
    },
    methods: {
        onDelete(id, name) {
            this.$emit('release-pokemon', {id, name})
        }
    }
}
</script>