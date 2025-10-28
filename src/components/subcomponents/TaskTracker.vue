<script>

    // TODO: Complete the code
    export default { 

        data() {
            return {
                
            }
        },
        // Hint: insert properties task (Object) and idx (Number)
        emits: ["done"],
        props: ["task", "idx"],
        mounted() {
        console.log("Task received:", this.task)
        }
    }
</script>

<template>
    <!-- TODO: add your template code here -->
     <div class="card" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title">Deadline: {{task.deadline}}</h5>
            <p class="card-text">{{task.desc}}</p>
             <button @click="$emit('done', idx)" class="btn btn-primary">Done</button>
        </div>
    </div> 
   
</template>


