<template>
    <button
        @click="onCLick()"
        :class="[
            color ? `px-4 py-2 rounded text-white tracking-wide bg-${this.color}-600 hover:bg-${this.color}-700 focus:outline-none focus:bg-${this.color}-600 focus:ring-2 focus:ring-offset-2 focus:ring-${this.color}-600 shadow transition duration-700` : `px-4 py-2 rounded text-white tracking-wide bg-blue-600 hover:bg-blue-700 focus:outline-none focus:bg-blue-600 focus:ring-2 focus:ring-offset-2 focus:ring-blue-600 shadow transition duration-700`
        ]"
    >
        {{ text }}
    </button>
</template>

<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String
    },
    methods: {
        onClick() {
            console.log('Hey')
        }
    }
}
</script>