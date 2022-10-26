<template>
    <div class="task-grid">
        <!--Define que caso o tamanho de tasks for verdadeiro, ou seja, >0 será plotada a lista-->
        <template v-if="tasks.length">
            <Task v-for="(task,i) in tasks" :key="task.name"
            @taskDeleted="$emit('taskDeleted', i)"
            @taskComplete="$emit('taskComplete',i)"
            :task="task"></Task>
        </template>
            <p v-else class="no-task">All tasks done!!! </p>
    </div>
</template>

<script>
import Task from './Task.vue'
export default {
    components:{Task},
    props: {
        tasks:{ type:Array, required: true}
    },
}
</script>

<style>
    .task-grid{
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .no-task{
        color: #aaa;
        font-size: 1.7rem;
    }
</style>