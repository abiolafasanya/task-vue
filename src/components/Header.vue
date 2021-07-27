<template>
        <header>
            <h1>{{title}}</h1>
            <Button 
                @toggle-add="$emit('toggle-add')" 
                :text="btnToggle ? 'Close' : 'Add Task'" 
                :class="btnToggle ? 'close' : 'open'" 
            />
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
        },
        btnToggle: Boolean,
    },
    components: {
        Button,
    },
    // emits: ['toggle-add']
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

// :text="btnToggle ? 'Close' : 'Add Task' " color="green"