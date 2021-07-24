<template>
    <form>
        <label for=""> Add Task</label>
        <input type="text" placeholder="Type task her" id="">
        <Btn  class="btn" text="Save" />
    </form>
</template>
<script>
import Btn from './Button'

export default {
    name: 'AddTask',
    components: {
        Btn,
    }
}
</script>
<style>
    form {
        display: flex;
        flex-direction: column;
        width: 80%;
        margin: 40px auto;
    }
    label {
        color: #fff;
        text-align: center;
        font-size: 24px;
    }
    input {
        padding: 15px 10px;
        margin: 10px 0px 20px 0px;
        border-radius: 5px;
        border: none;
        outline: none;
        font-size: 18px;
    }
    .btn {
        background: rgb(39, 189, 39);
        padding: 15px;
        font-size: 18px;
    }
    .btn:hover {
        background-color: rgb(35, 97, 35);
    }
    .btn:active {
        background-color: rgb(76, 128, 76);
    }
</style>