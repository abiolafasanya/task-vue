<template>
    <div :class="[task.completed ? 'complete' : '', 'task']">
        <h3>
            {{task.title}}
            <span @click="$emit('delete-task', task.id)" class="delete">&times;</span>
        </h3>
        <p>{{task.day}}</p>
        <span class="check">
            <input type="checkbox" 
                @change="$emit('task-completed', task.id)" 
                :value="task.completed"
                :v-if="task.completed"
                :checked="task.completed"
            />

            {{task.completed ? 'complete' : 'Not completed'}}
            
        </span>
    </div>
</template>

<script>

export default {
    name: 'Task',
    props: {
        task: Object
    },
}
</script>

<style scoped>
    .delete {
        color: red;
        font-size: 2rem;
        cursor: pointer;
    }
    h3 {
        display: flex;
        justify-content: space-between;
    }
        .task {
        padding: 10px 30px;
        background: #dadada;
        margin: 15px;
        border-radius: 5px;
    }
    .complete {
       border-left: 15px solid green;
    }

</style>