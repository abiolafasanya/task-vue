<template>
        <header>
            <h1>{{title}}</h1>
            <Button text="Add Activity" color="green" />
        </header>
</template>

<script>
import Button from './Button'

export default {
    name: 'Header',
    props: {
        title: {
            String,
            default: 'Gym tracker'
        }
    },
    components: {
        Button,
    }
}
</script>

<style>
    header {
        background: rgb(167, 167, 167);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 2px 15px;
    }
</style>