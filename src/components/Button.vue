<template>
    <button @click="onClick()" :style="{background: color}">
        {{text}}
    </button>
</template>
<script>
export default {
    name: 'Button',
    props: {
        text: String,
        color: String,
    },
    methods: {
        onClick () {
            console.log('button clicked')
        }
    }
}
</script>
<style>
    button {
        padding: 10px 15px;
        background: rgb(0, 0, 0);
        color: #fff;
        border-radius: 5px;
        border: none;
        outline: none;
        font-weight: bold;
    }
</style>