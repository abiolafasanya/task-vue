<template>
    <form @submit="onSubmit">
        <label for=""> Add Task</label>
        <input v-model="title" type="text" placeholder="Type task here" />
        <input v-model="day" type="date" >
        <div class="checkboxThree">
            <input v-model="completed" type="checkbox" value="1" id="checkboxThreeInput" name="" />
            <label for="checkboxThreeInput"></label>
        </div>
        <Btn  class="btn" text="Save" />
    </form>
</template>
<script>
import Btn from './Button'

export default {
    name: 'AddTask',
    components: {
        Btn,
    },
    data() {
        return {
            title: '',
            day: '',
            completed: false
        }
    },
    methods: {
        onSubmit(e){
            e.preventDefault()

            if(this.title === null || this.title === ''){
                alert('Please add a task')
                return
            }

            else {
                const newTask = {
                    id: Math.floor(Math.random() * 100000),
                    title: this.title,
                    day: this.day,
                    completed: this.completed
                }
                console.log(newTask)
                this.$emit('add-task', newTask)
                }

            }
    }
}
</script>
<style scoped>
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
    input[type=checkbox] {
    visibility: hidden;
    }
    .checkboxThree {
        width: 120px;
        height: 40px;
        background: #333;
        margin: 20px 0px;
        border-radius: 50px;
        position: relative;
    }
    .checkboxThree:before {
    content: 'On';
    position: absolute;
    top: 12px;
    left: 13px;
    height: 2px;
    color: #26ca28;
    font-size: 16px;
    }
    .checkboxThree:after {
    content: 'Off';
    position: absolute;
    top: 12px;
    left: 84px;
    height: 2px;
    color: #111;
    font-size: 16px;
    }
    .checkboxThree label {
    display: block;
    width: 52px;
    height: 22px;
    border-radius: 50px;

    transition: all .5s ease;
    cursor: pointer;
    position: absolute;
    top: 9px;
    z-index: 1;
    left: 12px;
    background: #ddd;
    }
    .checkboxThree input[type=checkbox]:checked + label {
    left: 60px;
    background: #26ca28;
}
</style>