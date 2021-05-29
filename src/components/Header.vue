<template>
    <header class="flex flex-wrap items-center justify-between mb-6">
        <div class="flex mb-2">
            <img class="mr-2" width="48" height="48" alt="Vue logo" src="../assets/logo.png">
            <h1 class="text-4xl text-green-600 tracking-wide font-semibold pb-2" style="border-bottom: 2px solid green;">{{ title }}</h1>
        </div>
        <Button text="Register Pokémon" color="green" />
    </header>
</template>

<script>
import Button from './button/Button'

export default {
    name: 'Header',
    props: {
        title: String
    },
    components: {
        Button
    }
}
</script>
