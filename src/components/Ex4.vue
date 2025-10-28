<script>
import TaskTracker from './subcomponents/TaskTracker.vue';

    export default {
        components: {TaskTracker},
        data() {
            return {
                idx: 0,
                desc: '',
                deadline: '',
                taskList: []
            }
        },
        methods: {
            add() {
                this.taskList.push( {'idx': this.idx, 'desc': this.desc, 'deadline': this.deadline } )
                this.desc = ''
                this.deadline = ''
                this.idx++
            },
            // TODO: Add a new method, to delete a task completed
            done(idx) {
                this.taskList = this.taskList.filter(task => task.idx !== idx);
            },
            
        }
    }

</script>

<template>
    <div class="mb-3">
        <label for="desc" class="form-label">Task</label>
        <input type="text" class="form-control" id="desc" v-model='desc' placeholder="task">
    </div>
    <div class="mb-3">
        <label for="deadline" class="form-label">Deadline</label>
        <input type="date" class="form-control" id="deadline" v-model='deadline' placeholder="deadline">
    </div>

    <button type="button" @click="add" class="btn btn-primary">Add New Task</button>
    <hr>

    <!-- TODO: Modify following code -->
    <task-tracker v-for="task in taskList" v-bind:key="task.idx" v-bind:task="task" v-bind:idx="task.idx" v-on:done="done"></task-tracker>

</template>

<style scoped>
   
</style>
