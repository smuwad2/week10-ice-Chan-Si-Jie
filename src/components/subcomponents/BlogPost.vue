<script>
    export default {
        // Add code if/as necessary
        // Hint: Add properties subject, entry and mood
        props: ['subject', 'entry', 'mood']
    }
</script>


<template>
    <!-- TODO: add your template code here. Use boostrap card --> 
     <div class="card" style="width: 18rem;">
        <img class="card-img-top" :src="`/assets/${mood.toLowerCase()}.png`" alt="Card image cap">
        <div class="card-body">
            <h5 class="card-title">{{subject}}</h5>
            <p class="card-text">{{entry}}</p>
        </div>
    </div>
    

</template>

