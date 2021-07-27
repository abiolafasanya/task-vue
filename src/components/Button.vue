<template>
    <button  @click="onClick()" :style="{background: color}">
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
            this.$emit('toggle-add')
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
    .open {
        background: hsla(108, 96%, 25%, 0.89);
        color: hsla(115, 28%, 83%, 0.89);
        transition: ease-in-out .3s
    }
    .open:active {
        background: hsla(123, 97%, 54%, 0.562);
        color: hsla(137, 82%, 4%, 0.89);
    }
    .close {
        background: hsla(12, 96%, 39%, 0.89);
        color: hsla(12, 28%, 83%, 0.89);
        transition: ease-in-out .3s
    }
    .close:active {
        background: hsla(12, 98%, 56%, 0.692);
        color: hsla(11, 22%, 90%, 0.89);
    }
</style>